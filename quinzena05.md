AVALIAÇÃO PREGUIÇOSA
Avaliação preguiçosa é a estratégia de avaliação padrão de várias linguagens funcionais.
Na avaliação preguiçosa, uma expressão será avaliada apenas quando o seu resultado por necessário. 
Quando esse resultado for calculado, ele será memorizado e sempre que for preciso ele será reutilizado, sem necessidade de um novo processamento.
No Haskell podemos usar a função sprint para analisarmos o estado atual da variável e assim podemos verificar a existência da avaliação preguiçosa nessa linguagem. 
A partir da função seq é possível avaliar uma variável e imprimir outra, durante a mesma execução, por exemplo:

Prelude> x = 1 + 1
Prelude> y = 2 * 3
Prelude> :sprint x
x = _
Prelude> :sprint y
y = _
Prelude> seq x y
6
Prelude> :sprint x
x = 2

STREAMS
Aproveitando o conceito de avaliação preguiçosa, temos a implementação das streams, que são listas parecidas com listas comuns, porém a avaliação de cada célula é feita de maneira preguiçosa. 
Na linguagem do Haskell todas as listas implementadas podem ser chamadas de streams.

PARALELISMO

- Eval Monad
No Haskell, a partir da biblioteca Control.Parallel.Strategies temos acesso à tipos e funções para criar paralelismo.
•	rpar indica que meu argumento pode ser executado em paralelo.
•	rseq diz meu argumento deve ser avaliado e o programa deve esperar pelo resultado.
•	runEval executa uma expressão (em paralelo ou não) e retorna o resultado dessa computação.

- Estratégias de avaliação
No Haskell a partir da biblioteca anterior, podemos definir o tipo:

type Strategies a = a -> Eval a

A ideia desse tipo é permitir a abstração de estratégias de paralelismo para tipos de dados.

- ThreadScope
É uma ferramenta para análise de desempenho de programas paralelos Haskell , podemos verificar se o trabalho está bem equilibrado entre os processadores disponíveis e identificar problemas de desempenho.

HASKELL CONCORRENTE
O objetivo da programação concorrente é definir explicitamente múltiplos caminhos de controle, geralmente para permitir múltiplas interações com usuário ou interfaces externas.

CONCEITOS PRINCIPAIS
- Uma thread é a menor sequência de computação que pode ser gerenciada de forma independente pelo gerenciador de tarefas.
- Um processo é um procedimento computacional completo que pode conter diversas threads de execução.
- Múltiplas threads de um mesmo processo compartilham a memória alocada, podendo utilizá-la para troca de mensagens.
- Múltiplos processos não compartilham memória alocada.
No Haskell criamos uma thread com a função forkIO

COMUNICAÇÃO ENTRE THREADS 
Para que as threads possam se comunicar é necessário a existência de um espaço de memória compartilhada.
No Haskell isso é implementado através do tipo MVar, que é um container para qualquer tipo de dado.
Os tipos do Haskell são imutáveis, mas o tipo MVar pode ajudar a simular um tipo mutável

OPERAÇÕES ASSÍNCRONAS
Uma operação assíncrona é uma operação que é feita em background enquanto eu posso fazer outras operações que não dependam dela, e permita que eu aguarde o final para realizar alguma operação sobre os resultados.
No Haskell:
•	A função async cria uma thread a ser executada assíncronamente com outras.
•	A função wait aguarda o final da execução de uma thread assíncrona.

ESTRUTURAS DE DADOS PERSISTENTES

Paradigma funcional x imperativo
- Em linguagens de programação funcional, estruturas de dados funcionais são sempre persistentes.
- Em linguagens imperativas, estruturas de dados são tipicamente efêmeras

Características
•	Atualizações em uma ED não destroem a versão antiga.
•	Elementos afetados são copiados.
•	Elementos não afetados são compartilhados (en: shared) entre as diversas versões da ED.

Zippers
Zipper é um idiom de linguagens funcionais muito utilizado para manipular estruturas de dados persistentes.
Zippers podem ser usados para auxiliar na modificação das estruturas de dados.
