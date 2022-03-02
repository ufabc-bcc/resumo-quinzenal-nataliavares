**SEMANA 1**

Paradigma de programação pode ser definido como a forma que a solução de um problema computacional é descrita. É possível listar pelo menos 6 tipos de paradigmas, sendo eles:
- Imperativo: apresenta descrição, passo-a-passo, do que deve ser feito. Uma desvantagem é que mesmo chegando no resultado, pode ser difícil entender qual será esse resultado;
- Estruturado: semelhante à estrutura do paradigma imperativo, porém com implementação de blocos, permitindo utilização de procedimentos e funções.
- Orientado à objetos: aloca os dados em classes, que apresentam estados e métodos não compartilhados. Os objetos podem se comunicar com outros, evitando que seja necessário a utilização de variáveis globais. Uma desvantagem é que nem sempre é fácil ou possível modelar os problemas como objetos.
- Declarativo: o fluxo lógico para execução dos comandos desejados está implícito. Declara o que é desejado, mas sem detalhar como será possível chegar ao resultado. Uma desvantagem é que, para problemas mais complexos em que os comandos desejados não são suportados nativamente pela linguagem, pode haver um custo extra de desempenho.
- Lógico: necessário especificar apenas fatos e regras de inferência. O compilador constrói o programa baseado nos fatos lógicos. As desvantagens são que para algoritmos mais complexos, pode ser difícil expressar na forma lógica, além disso é mais lento para processar operações matemáticas.
- Funcional: é semelhante ao paradigma declarativo, porém não utiliza estados, que podem ser limitadores. Uma das dificuldades está em como fazer algo útil sem utilizar os estados.
O paradigma funcional tem como características: 
- Funções puras, onde não são apresentados efeitos colaterais, assim a mesma entrada sempre resulta na mesma saída
- Recursões, resultando em um código enxuto e declarativo
- Avaliação preguiçosa, quando uma expressão é gerada temos uma promessa de execução, que será executada apenas se for necessário.

**SEMANA 2**

Cálculo λ, inventado por Alonzo Church na década de 1930, pode ser definido como “a menor linguagem de programação do mundo”. A sintaxe do Cálculo λ é composta por 3 elementos: variáveis, definição de funções e aplicação de funções.
Com o Cálculo λ e o Combinador Y é possível definir diversas funcionalidades, como: booleanos, registros (tuplas, structs, ...), números, funções e recursão.

A programação em Haskell tem como características:
- Códigos concisos e declarativos: o programador declara o que ele quer ao invés de escrever um passo-a-passo.
- Imutabilidade: não existe um conceito de variável
- Funções recursivas 
- Funções de alta ordem: funções podem receber funções como parâmetros
- Tipos polimórficos
- Avaliação preguiçosa
No Haskell temos algumas convenções como:
- Obrigatoriedade de iniciar nomes de funções com letras minúsculas, 
- As listas são nomeadas acrescentando o caractere 's' ao nome do que ela representa,
- Os blocos lógicos são definidos por indentação tornando a preocupação com layout algo relevante, para auxiliar na indentação é importante utilizar espaço ao invés de tabs.
Os tipos de dados disponíveis no Haskell são: tipos básicos (Bool, Int, Float, String, ...), listas, tuplas e funções.
Um conceito importante do Haskell são as assinaturas de funções, responsáveis por definir o tipo de entrada e tipo de saída resultante da função.
Dentro de uma função, para definir nomes intermediários podemos usar a cláusula where. Além disso também é possível utilizar condicionantes, como if-then-else.
Para a estrutura de listas o Haskell conta com um conjunto de funções básicas para manipulação de listas já pré-estabelecido.
Para as listas implementadas em Haskell é possível utilizar os conceitos matemáticos quando falamos de conjuntos, por exemplo, {x2∣x∈{1..5}} pode ser definido como [x^2 | x <- [1..5]], o que facilita quando queremos criar uma lista com regras específicas
