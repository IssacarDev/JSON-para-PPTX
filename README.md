# Gerador de Apresentações de Músicas (JSON para PPTX)

## Descrição

Este script Python utiliza uma interface gráfica (GUI) construída com **CustomTkinter** para converter arquivos `.json` contendo letras de músicas em apresentações de PowerPoint (`.pptx`). A ferramenta foi projetada para criar slides minimalistas, ideais para apresentações de louvor ou eventos, onde cada parágrafo da letra é colocado em um slide separado sobre uma imagem de fundo definida pelo usuário.

## Funcionalidades

  * **Interface Gráfica Simples:** Permite ao usuário selecionar os arquivos e configurar as fontes facilmente.
  * **Processamento em Lote:** Selecione múltiplos arquivos `.json` de uma só vez e gere todas as apresentações automaticamente.
  * **Fundo Personalizado:** Escolha uma única imagem (`.jpg`, `.png`) que será usada como plano de fundo para todos os slides em todas as apresentações geradas.
  * **Design Minimalista:**
      * Cria um slide de título com o Título e o Artista da música.
      * Gera um slide individual para cada parágrafo da letra.
      * Todo o texto é formatado em branco (para fundos escuros), centralizado e em negrito.
  * **Tamanhos de Fonte Ajustáveis:** Permite ao usuário definir tamanhos de fonte (em Pts) específicos para o Título, o Artista e os parágrafos da Letra.
  * **Feedback de Progresso:** Informa ao usuário quais arquivos estão sendo processados e exibe um resumo dos sucessos e erros ao final.

## Estrutura do JSON Esperada

Para que o script funcione corretamente, seus arquivos `.json` devem seguir uma estrutura específica. O script tenta extrair os seguintes campos:

```json
{
  "title": "Título da Música",
  "artist": "Nome do Artista",
  "lyrics": {
    "paragraphs": [
      {
        "text": "Primeiro parágrafo da letra..."
      },
      {
        "text": "Segundo parágrafo da letra..."
      },
      {
        "text": "..."
      }
    ]
  }
}
```

  * `title` (String): O título da música (usado no primeiro slide).
  * `artist` (String): O artista ou banda (usado no primeiro slide).
  * `lyrics.paragraphs` (Lista de Objetos): Uma lista onde cada objeto representa um slide de letra.
  * `text` (String): O texto do parágrafo da letra (dentro de cada objeto em `paragraphs`).

## Tecnologias e Bibliotecas

O script utiliza as seguintes bibliotecas Python:

  * **CustomTkinter:** Para a criação da interface gráfica moderna.
  * **python-pptx:** Para criar e manipular os arquivos de apresentação do PowerPoint.
  * **Tkinter (embutido):** Usado para as caixas de diálogo de seleção de arquivos.
  * **json (embutido):** Para ler e processar os arquivos de entrada `.json`.
  * **os (embutido):** Para manipulação de caminhos e nomes de arquivos.

## Requisitos e Instalação

Antes de executar o script, você precisa instalar as bibliotecas necessárias.

1.  **Clone ou baixe** este repositório.

2.  **Instale as dependências** usando `pip`:

    ```bash
    pip install customtkinter
    pip install python-pptx
    ```

## Como Usar

1.  **Execute o script Python:**

    ```bash
    python jsonToPptx.py
    ```

2.  **Selecione os Arquivos JSON:**

      * Clique no botão "**1. Selecionar Arquivos JSON**".
      * Na janela que se abre, selecione um ou mais arquivos `.json` de músicas.

3.  **Selecione a Imagem de Fundo:**

      * Clique no botão "**2. Selecionar Imagem de Fundo**".
      * Selecione um único arquivo de imagem (`.jpg`, `.jpeg` ou `.png`) que será usado como fundo.

4.  **Ajuste as Fontes (Opcional):**

      * Os tamanhos de fonte padrão já estão definidos (Título: 88, Artista: 40, Letra: 96).
      * Você pode alterar esses valores nas caixas de entrada, se desejar.

5.  **Gere as Apresentações:**

      * Clique no botão "**✨ Gerar Apresentações**".
      * Aguarde o processamento. A barra de status mostrará o progresso.
      * Os novos arquivos `.pptx` serão salvos no mesmo diretório dos arquivos `.json` originais, com o sufixo `_Minimalista.pptx`.

6.  **Verifique o Resultado:**

      * Ao final, uma mensagem pop-up informará quantos arquivos foram gerados com sucesso e listará eventuais erros que possam ter ocorrido.