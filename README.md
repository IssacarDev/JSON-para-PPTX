# Gerador de Apresentações de Músicas (JSON para PPTX)

## Descrição

[cite\_start]Este script Python utiliza uma interface gráfica (GUI) construída com **CustomTkinter** para converter arquivos `.json` contendo letras de músicas em apresentações de PowerPoint (`.pptx`)[cite: 1]. [cite\_start]A ferramenta foi projetada para criar slides minimalistas, ideais para apresentações de louvor ou eventos, onde cada parágrafo da letra é colocado em um slide separado sobre uma imagem de fundo definida pelo usuário[cite: 1].

## Funcionalidades

  * [cite\_start]**Interface Gráfica Simples:** Permite ao usuário selecionar os arquivos e configurar as fontes facilmente[cite: 1].
  * [cite\_start]**Processamento em Lote:** Selecione múltiplos arquivos `.json` de uma só vez e gere todas as apresentações automaticamente[cite: 1].
  * [cite\_start]**Fundo Personalizado:** Escolha uma única imagem (`.jpg`, `.png`) que será usada como plano de fundo para todos os slides em todas as apresentações geradas[cite: 1].
  * **Design Minimalista:**
      * [cite\_start]Cria um slide de título com o Título e o Artista da música[cite: 1].
      * [cite\_start]Gera um slide individual para cada parágrafo da letra[cite: 1].
      * [cite\_start]Todo o texto é formatado em branco (para fundos escuros), centralizado e em negrito[cite: 1].
  * [cite\_start]**Tamanhos de Fonte Ajustáveis:** Permite ao usuário definir tamanhos de fonte (em Pts) específicos para o Título, o Artista e os parágrafos da Letra[cite: 1].
  * [cite\_start]**Feedback de Progresso:** Informa ao usuário quais arquivos estão sendo processados e exibe um resumo dos sucessos e erros ao final[cite: 1].

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

  * [cite\_start]`title` (String): O título da música (usado no primeiro slide)[cite: 1].
  * [cite\_start]`artist` (String): O artista ou banda (usado no primeiro slide)[cite: 1].
  * [cite\_start]`lyrics.paragraphs` (Lista de Objetos): Uma lista onde cada objeto representa um slide de letra[cite: 1].
  * [cite\_start]`text` (String): O texto do parágrafo da letra (dentro de cada objeto em `paragraphs`)[cite: 1].

## Tecnologias e Bibliotecas

O script utiliza as seguintes bibliotecas Python:

  * [cite\_start]**CustomTkinter:** Para a criação da interface gráfica moderna[cite: 1].
  * [cite\_start]**python-pptx:** Para criar e manipular os arquivos de apresentação do PowerPoint[cite: 1].
  * [cite\_start]**Tkinter (embutido):** Usado para as caixas de diálogo de seleção de arquivos[cite: 1].
  * [cite\_start]**json (embutido):** Para ler e processar os arquivos de entrada `.json`[cite: 1].
  * [cite\_start]**os (embutido):** Para manipulação de caminhos e nomes de arquivos[cite: 1].

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

      * [cite\_start]Clique no botão "**1. Selecionar Arquivos JSON**"[cite: 1].
      * [cite\_start]Na janela que se abre, selecione um ou mais arquivos `.json` de músicas[cite: 1].

3.  **Selecione a Imagem de Fundo:**

      * [cite\_start]Clique no botão "**2. Selecionar Imagem de Fundo**"[cite: 1].
      * [cite\_start]Selecione um único arquivo de imagem (`.jpg`, `.jpeg` ou `.png`) que será usado como fundo[cite: 1].

4.  **Ajuste as Fontes (Opcional):**

      * [cite\_start]Os tamanhos de fonte padrão já estão definidos (Título: 88, Artista: 40, Letra: 96)[cite: 1].
      * [cite\_start]Você pode alterar esses valores nas caixas de entrada, se desejar[cite: 1].

5.  **Gere as Apresentações:**

      * [cite\_start]Clique no botão "**✨ Gerar Apresentações**"[cite: 1].
      * Aguarde o processamento. [cite\_start]A barra de status mostrará o progresso[cite: 1].
      * [cite\_start]Os novos arquivos `.pptx` serão salvos no mesmo diretório dos arquivos `.json` originais, com o sufixo `_Minimalista.pptx`[cite: 1].

6.  **Verifique o Resultado:**

      * [cite\_start]Ao final, uma mensagem pop-up informará quantos arquivos foram gerados com sucesso e listará eventuais erros que possam ter ocorrido[cite: 1].