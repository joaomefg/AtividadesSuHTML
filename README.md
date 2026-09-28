# Atividades CEM

Página para montar listas de exercícios e atividades no modelo do **Centro de Ensino Multidisciplinar**, com pré-visualização da folha A4 em tempo real.

## Como usar

1. Abra a página (online ou dando dois cliques no `index.html`).
2. Preencha o **cabeçalho**: tipo de atividade, ano, componente, data, valor e professor(a).
3. Adicione as **questões**. Cada uma pode ter:
   - enunciado;
   - espaço para resposta (linhas, espaço em branco, alternativas ou nada);
   - tabela, inclusive no formato "ligue as colunas";
   - imagem.
4. Clique em **Imprimir ou PDF**.

O que é digitado fica guardado no próprio navegador. Para continuar em outro computador, use **Salvar para editar depois** e depois **Abrir salva**.

## Publicar no GitHub Pages

1. Envie este repositório para o GitHub.
2. Em **Settings → Pages**, escolha *Deploy from a branch*, branch `main`, pasta `/ (root)`.
3. Em cerca de 1 minuto a página fica disponível em `https://joaomefg.github.io/AtividadesSuHTML/`.

## Estrutura

- `index.html`: a aplicação inteira (HTML, CSS e JavaScript no mesmo arquivo, sem dependências para instalar).
- `.nojekyll`: faz o GitHub Pages servir os arquivos como estão.
