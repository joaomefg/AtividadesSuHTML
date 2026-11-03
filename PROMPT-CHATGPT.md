# Instruções para o ChatGPT

O jeito mais fácil é usar o botão **Gerar com ChatGPT** no site: ele monta este texto já com os dados do cabeçalho.
Para usar à mão, troque o que está entre colchetes, cole no ChatGPT e importe a resposta pelo mesmo botão (colando o texto ou escolhendo o arquivo `atividade.json`).

```text
Você é um(a) professor(a) experiente do Ensino Fundamental I. Crie uma atividade escolar e me devolva no formato JSON descrito abaixo, para eu importar no meu sistema de atividades.

DADOS DA ATIVIDADE
- Componente curricular: [Língua Portuguesa ou Matemática]
- Ano/série: [4º ANO]
- Conteúdo/tema: [tema da atividade]
- Quantidade de questões: [10]
- Observações: [nenhuma]

REGRAS PEDAGÓGICAS
- Linguagem simples e adequada a alunos do ano/série informado, alinhada à BNCC.
- Varie os tipos de questão: completar lacunas, marcar alternativa, ligar colunas, completar tabela e resposta escrita.
- Comece cada enunciado com um comando claro (Leia, Complete, Marque, Ligue, Responda, Escreva...).
- Não coloque gabarito nem respostas.
- Não use imagens nem emojis.

FORMATO (JSON válido, UTF-8, sem comentários)
Campos de cada item de "questoes":
- "texto": o enunciado. Use \n para quebrar linha. Itens a), b), c) ficam dentro do texto, um por linha. Para lacunas, use ____________.
- "tipo": o espaço de resposta que aparece abaixo do enunciado:
  - "linhas": linhas para o aluno escrever. Informe "qtd" com o número de linhas (1 a 10).
  - "espaco": espaço em branco para cálculo ou desenho. Informe "qtd" com a altura em linhas.
  - "alternativas": opções para marcar. Preencha "alternativas" com 3 a 5 opções, SEM letras (o sistema coloca a), b), c)).
  - "nenhum": sem espaço extra (quando a resposta fica nas lacunas do texto ou na tabela).
- "alternativas": lista de textos (use [] quando o tipo não for "alternativas").
- "tabela": null ou {"cab": [títulos das colunas], "linhas": [[células da linha], ...], "ligar": false}.
  - No máximo 6 colunas; cada linha com o mesmo número de células de "cab". Use "" nas células que o aluno vai preencher.
  - Para atividade de LIGAR: tabela com 2 colunas, "ligar": true e a segunda coluna embaralhada.
Mantenha "titulo", "ano", "componente", "data", "professor" e "valor" exatamente como no exemplo.

EXEMPLO DO FORMATO (o conteúdo é só ilustrativo):
{
  "titulo": "LISTA DE EXERCÍCIOS",
  "ano": "[4º ANO]",
  "componente": "[Língua Portuguesa]",
  "data": "[AAAA-MM-DD]",
  "professor": "[nome]",
  "valor": "",
  "questoes": [
    {"texto":"Complete as frases com um verbo adequado.\n\na) Eu ____________ todos os dias.\nb) Nós ____________ na escola.","tipo":"nenhum","qtd":0,"alternativas":[],"tabela":null},
    {"texto":"Marque a alternativa correta.\n\nNa frase “Nós fazemos a tarefa.”, o verbo está na:","tipo":"alternativas","qtd":0,"alternativas":["1ª pessoa do singular","1ª pessoa do plural","3ª pessoa do singular"],"tabela":null},
    {"texto":"Ligue cada pronome à pessoa correta.","tipo":"nenhum","qtd":0,"alternativas":[],"tabela":{"cab":["Pronome","Pessoa"],"linhas":[["Eu","3ª pessoa do plural"],["Eles","1ª pessoa do singular"]],"ligar":true}},
    {"texto":"Complete a tabela.","tipo":"nenhum","qtd":0,"alternativas":[],"tabela":{"cab":["Frase","Pessoa","Número"],"linhas":[["Eu canto.","",""],["Elas dançam.","",""]],"ligar":false}},
    {"texto":"Escreva uma frase usando um verbo no plural.","tipo":"linhas","qtd":3,"alternativas":[],"tabela":null}
  ]
}

COMO RESPONDER
1. Gere um arquivo para download chamado atividade.json com a atividade completa.
2. Mostre também o mesmo JSON completo em um único bloco de código, para eu poder copiar.
3. Não escreva mais nada além disso.
```
