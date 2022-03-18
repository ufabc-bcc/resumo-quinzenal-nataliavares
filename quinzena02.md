QUICKCHECK
QuickCheck são testes baseados em propriedades, assim são complementares aos testes baseados em exemplos. 
Ao testar um algoritmo de ordenação, por exemplo, o QuickCheck espera que as seguintes propriedades sejam satisfeitas: 
- A lista de saída está ordenada
- A lista de saída tem o mesmo tamanho da lista de entrada
- A lista de saída contém os mesmos elementos da lista de entrada

FUNÇÕES DE ALTA ORDEM
No Haskell, funções podem ser utilizadas como argumento de entrada de outras funções, transformando as funções em um tipo de dado.
Funções de alta ordem são funções que recebem outras funções como argumento ou devolvem uma função em suas saídas.
Funções de alta ordem para listas:
- Função map: Uma função que transforma uma lista do tipo a para o tipo b utilizando uma função;
- Função filter: devolve uma lista de todos os valores cujo predicado p de x é verdadeiro;
Para os dois casos (map e filter) podem ser utilizadas funções parciais.
As funções map e filter podem ser utilizados em conjunto.
- Operador pipe ($): é utilizado para separar as aplicações das funções e remover os parênteses
- Outras funções: all (retorna verdadeiro se toda a lista satisfaz a função), any (retorna verdadeiro caso algum item satisfaça a função), takeWhile (mantem os elementos que satisfazem a função), dropWhile (remove os elementos que satisfazem a função)

FOLDING
Dobra a lista aplicando a função f em cada elemento da lista e um resultado parcial.
Função foldr:  percorre lista da direita para a esquerda, útil em listas infinitas
Função foldl:  percorre lista da esquerda para a direita, útil em listas finitas

COMPOSIÇÃO DE FUNÇÕES
No Haskell, podemos utilizar o conceito matemático de composição de funções, permitindo a aplicação de uma função sobre outra. Para isso é utilizado o operador (.)

CRIANDO NOVOS TIPOS
Utilizando a palavra-chave ‘type’ podemos criar um novo tipo de dado, porém cria apenas um apelido para um certo tipo ou combinação de tipos já existentes.

TIPOS DE DADOS ALGÉBRICOS 
São tipos completamente novos, que podem conter tipos primitivos. A partir da palavra-chave ‘data’ 
É possível utilizar também a função ‘newtype’, que define um novo tipo até ser compilado, depois ele é substituído como um sinônimo. Diferentemente da função ‘type’, que é um sinônimo.

TIPOS RECURSIVOS
Um bom exemplo para o tipo recursivo é a árvore binária, onde a tem algumas possibilidades, isto é, pode ser um nó folha, um nó com uma árvore à direita ou um nó com uma árvore à esquerda.

ÁLGEBRA DOS TIPOS
Os Tipos de Dados Algébricos apresentam algumas similaridades com a Álgebra matemática
É possível construir elementos algébricos utilizando ADTs, como por exemplo Zero e Um (conforme implementações vistas em aula).

ZIPPERS
No geral fazemos conversão de árvores para Zippers, uma vez que assim podemos criar uma separação da árvore em direita e esquerda, por exemplo

CLASSES DE TIPO
Para criar uma nova classe de tipos usamos a palavra-chave ‘class’
•	Instâncias da classe: utilizamos a palavra-chave ‘instance’. Apenas tipos definidos por ‘data’ e ‘newtype’ podem ser instâncias de uma classe, portanto ‘type’ não é possível.

Temos alguns tipos de classes pré-estabelecidas:
•	Eq: classe de igualdade (igualdade e desigualdade)
•	Ord: classe de ordem (maior e menor)
•	Show: classe imprimível
•	Read: classe legível (extrai conteúdo de strings)
•	Num: classe numérica
•	Integral: classe de números inteiros
•	Fractional: classe de números fracionais
•	Floating: classe de pontos flutuantes
Derivação de instâncias: o Haskell consegue inferir muitas vezes as instâncias das classes mais comuns, assim só precisamos utilizar a palavra-chave ‘deriving’ ao definir um novo tipo.
