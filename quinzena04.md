MONADS
Monads são extensões naturais de applicative functors.
A função principal do Monad é dada por:
(>>=) :: (Monad m) => m a -> (a -> m b) -> m b 
Essa função captura o padrão de ‘case of’, sendo conhecida também como ‘bind’

MONOID DE MONADS
Assim como functors tem o tipo de classe Functor e applicative functors tem o tipo de classe Applicative, os monads tem tipo de classe Monad.
Em teoria das categorias um Monad pode ser visto como um Monoid das categorias dos Functors, onde o elemento identidade é o ‘return’ e o operador associativo é uma variação de (>>=) com a assinatura:
(>=>) ::Monad m=> (a -> m b) -> (b -> m c) -> (a -> m c)
O operador (>=>) garante que se uma computação falhar, ela para imediatamente e reporta a falha.

MONADS E EFEITOS
Mesmo que o Haskell seja considerada uma linguagem puramente funcional, existe uma limite do quão puro o programa pode ser. 
As funções impuras são importantes para diversas situações:
- Parcialidade: como quando temos uma função que pode não terminar 
- Não-determinismo: como quando uma função pode retornar diferentes saídas dependendo de certas condições 
- Exceções (função Either): como quando lidamos com funções parciais ou que geram exceções e queremos identificar qual foi o problema
- Efeitos colaterais: Read only, Write only, Read/Write
- Entrada e saída iterativa: pois alteram o estado atual do sistema.

FUNÇÕES DE ALTA ORDEM PARA MONADS
As funções de alta ordem possuem versões para Monads na biblioteca específica Control.Monad
Temos funções como map (mapM) e filter (filterM), onde a principal diferença é: 
- filter seleciona elementos de uma lista
- filterM seleciona possíveis eventos de uma sequência de computações

FUNÇÕES DE READ E WRITE
Um exemplo de função read e write pode ser escrito a seguir:
t -> (a -> (b, a))
t -> Reader a (Writer a b)
onde o tipo Reader é a -> b, o tipo Writer é (a, b)

FUNÇÕES DE ENTRADA E SAÍDA
Funções de entrada e saída de dados são impuras pois alteram o estado atual do sistema.
A função getChar captura um caracter do teclado. Se eu executar tal função duas vezes, o valor da função não necessariamente será igual.
A função putChar escreve um caracter na saída padarão (ex.: monitor). Se eu executar duas vezes seguidas com a mesma entrada, a saída será diferente.
Basicamente, as funções de entrada e saída alteram estado
No Haskell chamamos as funções de entrada e saída como ações de IO ( IO actions ).
As funções básicas são implementadas internamente de acordo com o Sistema Operacional, sendo essas: getChar, putChar e return
