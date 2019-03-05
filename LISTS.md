# Listas

[Documentação](http://hackage.haskell.org/package/base-4.12.0.0/docs/Data-List.html)

[Complexidade de algoritmos](https://www.ime.usp.br/~song/mac5710/slides/01complex.pdf)

## Adicionando itens à uma lista

Você pode adicionar itens a uma lista usando tanto o operador `++` quanto o operador `:`. O primeiro aceita uma outra lista como parâmetro e a concatena ao final da coleção original, e o segundo adiciona um valor ao início da lista.

## Diferenças

Além do comportamento inicial, há uma grande diferença de performance na execução dos dois métodos, já que no caso do `++`, é necessário percorrer todos os itens da lista, enquanto para `:` a operação somente adiciona um item no começo da lista. Isso pode gerar um grande impacto ao lidarmos com listas muito grandes.

Isso ocorre devido à implementação da lista no Haskell. Diferentemente de linguagens como C# ou Java, as listas no Haskell não são arrays, e sim listas ligadas simples. Dessa forma, os métodos `head` (recuperar o primeiro elemento), `tail` (recuperar tudo, exceto o primeiro element) e `:` têm complexidade O(1), enquanto os métodos `last `(recuperar último elemento) e `++` têm complexidade O(n), já que precisam percorrer toda a lista para encontrar o último item.