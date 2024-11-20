[
  {
    "id": 1,
    "titulo": "A Cor Púrpura",
    "ano": 1985,
    "diretor": "Steven Spielberg",
    "genero": "Drama",
    "sinopse": "A história de Celie, uma mulher afro-americana que luta contra o racismo, abuso e busca por sua própria liberdade e identidade.",
    "atores_principais": ["Whoopi Goldberg", "Danny Glover", "Oprah Winfrey"],
    "duracao": "154 min"
  }
]
import json

# Função para carregar os dados do catálogo de filmes do arquivo JSON
def carregar_filmes():
    try:
        with open('filmes.json', 'r', encoding='utf-8') as arquivo:
            filmes = json.load(arquivo)
            return filmes
    except FileNotFoundError:
        print("O arquivo de filmes não foi encontrado.")
        return []
    except json.JSONDecodeError:
        print("Erro ao decodificar o arquivo JSON.")
        return []

# Função para exibir as informações de um filme
def exibir_filme(filme):
    print(f"\nTítulo: {filme['titulo']}")
    print(f"Ano: {filme['ano']}")
    print(f"Diretor: {filme['diretor']}")
    print(f"Gênero: {filme['genero']}")
    print(f"Sinopse: {filme['sinopse']}")
    print(f"Atores principais: {', '.join(filme['atores_principais'])}")
    print(f"Duração: {filme['duracao']}")

# Função principal para exibir o catálogo de filmes
def exibir_catalogo():
    filmes = carregar_filmes()
    
    if filmes:
        for filme in filmes:
            exibir_filme(filme)
    else:
        print("Nenhum filme encontrado no catálogo.")

# Função principal do programa
def main():
    print("Catálogo de Filmes")
    print("===================")
    exibir_catalogo()

if __name__ == "__main__":
    main()
