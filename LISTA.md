# LISTA DE EXERCÍCIOS

Essa lista de exercícios é dividida em seções que abrangem números, strings, parâmetros mistos e estruturas de dados. Cada seção é subdividida em níveis de dificuldade crescente: Nível 1 (básico), Nível 2 (intermediário) e Nível 3 (avançado). Cada exercício inclui exemplos de entrada e saída, bem como casos especiais para garantir uma compreensão completa do problema.

## Números

### Nível 1

#### Soma de Dois Números

Considere dois números, escreva uma função para realizar a soma.

```js
var res = soma(45.23, 87.23);

console.log(res); // 132.46
```

Casos especiais:

```js
console.log(soma(2, "3")); // NaN
console.log(soma("2")); // NaN
console.log(soma(3)); // 3
```

Desafio:

```js
console.log(soma(3, 4, 5, 6)); // 18
console.log(soma(3, 4, 5, 6, 7)); // 25
console.log(soma(3, 4, 5, NaN, 7)); // NaN
```

#### Média Aritmética

Considere dois números, escreva uma função para realizar a média aritmética.

```js
var res = media(45.23, 87.23);

console.log(res); // 66.33
```

Casos especiais:

```js
console.log(media(2, "3")); // NaN
console.log(media("2")); // NaN
console.log(media(3)); // 3
```

Desafio:

```js
console.log(media(3, 4, 5, 6)); // 184.5
console.log(media(3, 4, 5, 6, 7)); // 5
console.log(media(3, 4, 5, NaN, 7)); // NaN
```

#### Maior de Dois Valores

Mesma mecânica dos problemas anteriores.

#### Menor de Três Valores

Mesma mecânica dos problemas anteriores.

#### Verificar Número Par

```js
var res = ehPar(8);
console.log(res); // true

console.log(ehPar(3)) // false
console.log(ehPar(4)) // true
console.log(ehPar(-4)) // true

console.log(ehPar("-4")) // NaN
console.log(ehPar("asd")) // NaN
console.log(ehPar()) // null
```

#### Verificar Número Positivo, Negativo ou Zero

```js
var res = sinal(8);
console.log(res); // 1

console.log(sinal(3)) // 1
console.log(sinal(4)) // 1
console.log(sinal(-4)) // -1

console.log(sinal(0)) // 0
console.log(sinal("4")) // NaN
console.log(sinal("asd")) // NaN
console.log(sinal()) // null
```

#### Conversão Fahrenheit para Celsius

C = (F−32) × 5/9

Todos os casos de teste abaixo devem imprimir `true`.

```js
console.log(fahrenheitCelsius(32) === 0);
console.log(fahrenheitCelsius(212) === 100);
console.log(fahrenheitCelsius(68) === 20);
console.log(fahrenheitCelsius(-40) === -40);
```

#### Conversão Celsius para Fahrenheit

Mesmo que anterior, mas invertido.

### Nível 2

#### Potência de um Número

Dado um número, calcular a potência sem usar  o `Math.pow` ou o operador potência `**`.

```js
var res = potencia(2, 8); // 256
console.log(res);

console.log(potencia(4, 3)); // 64
console.log(potencia(-4, 3)); // -64

console.log(potencia(4)) // 4
console.log(potencia(4, 0)) // 1
console.log(potencia(-4, 0)) // 1

console.log(potencia("4", 3)) // NaN
console.log(potencia(4, "3")) // NaN
console.log(potencia("4")) // NaN
console.log(potencia("asd")) // NaN
console.log(potencia()) // null
// números decimais não suportados
console.log(potencia(4.5, 4)) // undefined
console.log(potencia(4, 4.5)) // undefined
console.log(potencia(4, -2)) // undefined
```

Desafio, aceitar decimais e negativos:

```js
console.log(potencia(4.5, 4)) // 410.0625
console.log(potencia(4, 4.5)) // 512
console.log(potencia(4, -2)) // 0.0625
```

#### Soma dos Dígitos de um Número

Considere um número inteiro positivo, some seus digítos, sem convertê-lo para `string`.

```js
var res = somaDigitos(1234);
console.log(res); // 10
console.log(somaDigitos(559933)); // 34

console.log(somaDigitos("559933")); // NaN
console.log(somaDigitos([])); // NaN
console.log(somaDigitos()); // 0

console.log(somaDigitos(1.234)); // undefined
console.log(somaDigitos(123.4)); // undefined
console.log(somaDigitos(-1234)); // undefined
```

#### Inverter Número Inteiro

Considere um número inteiro positivo, inverta seus digítos, sem convertê-lo para `string`.

```js
var res = inverter(1234);
console.log(res); // 4321
console.log(inverter(559933)); // 339955

console.log(inverter("559933")); // NaN
console.log(inverter([])); // NaN
console.log(inverter()); // 0

console.log(inverter(1.234)); // undefined
console.log(inverter(123.4)); // undefined
console.log(inverter(-1234)); // undefined
```

Desafio, aceitar decimais e negativos:

```js
console.log(inverter(1.234)); // 432.1
console.log(inverter(123.4)); // 4.321
console.log(inverter(-1234)); // -4321
```

#### Contar Dígitos de um Número

Dado um número inteiro, retornar quanto dígitos ele tem:

```js
var res = digitos(1234);
console.log(res); // 4
console.log(digitos(559933)); // 6

console.log(digitos("559933")); // NaN
console.log(digitos([])); // NaN
console.log(digitos()); // 0

console.log(digitos(1.234)); // undefined
console.log(digitos(123.4)); // undefined
console.log(digitos(-1234)); // undefined
```

Desafio, aceitar negativos e contar apenas a parte inteira de decimais:

```js
console.log(digitos(1.234)); // 1
console.log(digitos(123.4)); // 3
console.log(digitos(-1234)); // 4
```

#### Soma de Números Pares em um Intervalo

Considere um intervalo de dois números inteiros, somar os pares:

```js
var res = somaParesEntre(5, 17); // 6 + 8 + 10 + 12 + 14 + 16
console.log(res); // 66

console.log(somaParesEnter(4, 18)); // 88

console.log(somaParesEnter(18, 4)); // 0
console.log(somaParesEnter(-4, 4)); // -4 + -2 + 0 + 2 + 4 + 6 = 6

console.log(somaParesEnter(4.33, 8)); // null
console.log(somaParesEnter(4, 8)); // null
```

#### Soma de Números Ímpares em um Intervalo

Mesmo que anterior, mas com ímpares.


### Nível 3

#### Verificar Número Primo

Considere um número inteiro, retornar se é ou não um número primo:

```js
var res = primo(7);
console.log(res); // true

console.log(primo(8)); // false
console.log(primo(33333331)); // true
console.log(primo(333333331)); // false

console.log(primo("a")); // NaN
console.log(primo("1")); // NaN
console.log(primo(-8)); // undefined
console.log(primo(1)); // undefined 
console.log(primo(0)); // undefined 

```

#### Máximo Divisor Comum (MDC)

Considere dois números inteiros positivos, retornar o MDC.

```js
var res = mdc(132, 8);
console.log(res);; // 4

console.log(mdc(10, 5));    // 5
console.log(mdc(18, 12));  // 6
console.log(mdc(48, 18));  // 6
console.log(mdc(7, 3));    // 1
console.log(mdc(21, 14));  // 7
console.log(mdc(9, 28));   // 1
console.log(mdc(100, 10)); // 10
console.log(mdc(1, 1));    // 1
console.log(mdc(0, 5));    // 5
console.log(mdc(0, 10));   // 10

console.log(mdc("1", 10));   // NaN
console.log(mdc(1, "10"));   // NaN
console.log(mdc(5)); // 5
console.log(mdc(-5, 3)); // undefined
console.log(mdc(5, -3)); // undefined
```

Desafio, suportar mais de dois números:

```js
console.log(mdc(12, 18, 24)); // 6
console.log(mdc(8, 16, 32)); // 8
console.log(mdc(6, 10, 15)); // 1
console.log(mdc(24, 36, 60, 12, 48, 72)); // 12
console.log(mdc(7, 14, 21, 28, 35, 42)); // 7
```

#### Mínimo Múltiplo Comum (MMC)

Mesmo que acima, mas MMC.

#### Verificar Número Perfeito

Um número perfeito é aquele que a soma de seus divisores é ele mesmo:

```js
console.log(ehPerfeito(6)); // true
console.log(ehPerfeito(28)); // true
console.log(ehPerfeito(496)); // true
console.log(ehPerfeito(8128)); // true

console.log(ehPerfeito(1)); // false
console.log(ehPerfeito(2)); // false
console.log(ehPerfeito(10)); // false
console.log(ehPerfeito(12)); // false
console.log(ehPerfeito(100)); // false

console.log(ehPerfeito("100")); // NaN
console.log(ehPerfeito()); // null
console.log(ehPerfeito(-3)); // null
console.log(ehPerfeito(4.2)); // null
```

#### Verificar Número Palíndromo

Considere um número inteiro zero ou positivo, retornar se é palíndromo, isto é, se escrito de trás para frente terá o mesmo valor.

```js
console.log(ehPalindromo(0)); // true
console.log(ehPalindromo(1)); // true
console.log(ehPalindromo(7)); // true
console.log(ehPalindromo(11)); // true
console.log(ehPalindromo(121)); // true
console.log(ehPalindromo(1331)); // true
console.log(ehPalindromo(12321)); // true

console.log(ehPalindromo(10)); // false
console.log(ehPalindromo(12)); // false
console.log(ehPalindromo(123)); // false
console.log(ehPalindromo(2023)); // false

console.log(ehPalindromo("2023")); // NaN
console.log(ehPalindromo(-4)); // undefined
console.log(ehPalindromo(4.5)); // undefined
console.log(ehPalindromo()); // true
```

#### Calcular Raiz Quadrada Inteira

Considere um número inteiro positivo, retornar a raiz quadrada inteira (sem casas decimais). Se não for um quadrado perfeito, retornar o maior inteiro menor que a raiz quadrada.

```js
console.log(raizInteira(0)); // 0
console.log(raizInteira(1)); // 1
console.log(raizInteira(4)); // 2
console.log(raizInteira(9)); // 3
console.log(raizInteira(16)); // 4
console.log(raizInteira(25)); // 5
console.log(raizInteira(26)); // 5
console.log(raizInteira(15)); // 3
console.log(raizInteira(20)); // 4
console.log(raizInteira(30)); // 5

// casos especiais
console.log(raizInteira("25")); // NaN
console.log(raizInteira(-4)); // undefined
console.log(raizInteira(4.5)); // undefined
console.log(raizInteira()); // 0
```

#### Converter Número Decimal para Binário

Considere um número inteiro positivo, retornar a representação binária como uma string.

```js
console.log(decimalBinario(0)); // "0"
console.log(decimalBinario(1)); // "1"
console.log(decimalBinario(2)); // "10"
console.log(decimalBinario(5)); // "101"
console.log(decimalBinario(10)); // "1010"
console.log(decimalBinario(255)); // "11111111"
console.log(decimalBinario(1023)); // "1111111111"

// casos especiais
console.log(decimalBinario("10")); // NaN
console.log(decimalBinario(-4)); // undefined
console.log(decimalBinario(4.5)); // undefined
console.log(decimalBinario()); // "0"
```

#### Converter Número Binário para Decimal

Considere uma string representando um número binário, retornar o valor decimal.

```js
console.log(binarioDecimal("0")); // 0
console.log(binarioDecimal("1")); // 1
console.log(binarioDecimal("10")); // 2
console.log(binarioDecimal("101")); // 5
console.log(binarioDecimal("1010")); // 10
console.log(binarioDecimal("11111111")); // 255

// casos especiais
console.log(binarioDecimal("102")); // Error ("Número binário inválido")
console.log(binarioDecimal("abc")); // Error ("Número binário inválido")
console.log(binarioDecimal("")); // 0
console.log(binarioDecimal()); // null
```

#### Calcular Juros Simples

Considere um valor principal, uma taxa de juros e um período de tempo, retornar o valor total com juros simples.

```js
console.log(jurosSimples(1000, 0.05, 1)); // 1050
console.log(jurosSimples(1000, 0.05, 2)); // 1100
console.log(jurosSimples(1500, 0.03, 4)); // 1680
console.log(jurosSimples(2000, 0.04, 3)); // 2240

// casos especiais
console.log(jurosSimples("1000", 0.05, 2)); // NaN
console.log(jurosSimples(1000, "0.05", 2)); // NaN
console.log(jurosSimples(1000, 0.05, "2")); // NaN
console.log(jurosSimples(1000, 0.05)); // 1050
console.log(jurosSimples(1000)); // 1000
console.log(jurosSimples()); // 0
```

#### Calcular Juros Compostos

Considere a fórmula de juros compostos `A = P (1 + r/n)^(nt)` onde `A` é o valor futuro do investimento/ empréstimo, incluindo juros, `P` é o valor principal (o valor inicial), `r` é a taxa anual de juros (decimal), `n` é o número de vezes que os juros são compostos por ano e `t` é o número de anos que o dinheiro é investido ou emprestado. Por exemplo, `P = 1000`, `r = 0.05`, `n = 12`, `t = 10`, calcular `A`, seria:

```plain
A = 1000 (1 + 0.05/12)^(12*10) = 1647.01
```

Retornar o valor total com juros compostos com JavaScript em duas casas decimais.

```js
console.log(jurosCompostos(1000, 0.05, 12, 1)); // 1051.16
console.log(jurosCompostos(1000, 0.05, 12, 2)); // 1104.94
console.log(jurosCompostos(1500, 0.03, 4, 4)); // 1789.39
console.log(jurosCompostos(2000, 0.04, 365, 3)); // 2262.87

// casos especiais
console.log(jurosCompostos("1000", 0.05, 12, 2)); // NaN
console.log(jurosCompostos(1000, "0.05", 12, 2)); // NaN
console.log(jurosCompostos(1000, 0.05, "12", 2)); // NaN
// sempre devem vir os quatro parâmetros, caso contrário retorna undefined
console.log(jurosCompostos(1000, 0.05, 12)); // undefined
console.log(jurosCompostos(1000, 0.05)); // undefined
console.log(jurosCompostos(1000)); // undefined
console.log(jurosCompostos()); // undefined
```

## Strings

### Nível 1

Contar Caracteres de uma String

Converter String para Maiúsculas

Converter String para Minúsculas

Verificar String Vazia

Concatenar Duas Strings

Retornar Primeiro Caractere

Retornar Último Caractere

Comparar Duas Strings

Verificar se Contém Substring

Remover Espaços das Extremidades

### Nível 2

Contar Vogais em uma String

Contar Consoantes em uma String

Inverter uma String

Verificar Palíndromo (String)

Contar Ocorrências de um Caractere

Remover Caracteres Repetidos

Substituir Caracteres

Contar Palavras em uma String

Capitalizar Primeira Letra de Cada Palavra

Remover Caracteres Especiais

### Nível 3

Verificar Anagrama

Encontrar a Palavra Mais Longa

Encontrar a Palavra Mais Curta

Contar Frequência de Cada Caractere

Verificar se String Possui Apenas Dígitos

Validar Endereço de E-mail

Validar CPF (Formato)

Comprimir String (Run-Length Encoding)

Encontrar Substring Mais Frequente

Normalizar String (Remover Acentos e Padronizar)


## Parâmetros Mistos

### Nível 1

Comparar Tamanho de String e Número

Verificar String Tem Comprimento Mínimmo

Repetir String N Vezes

Preencher String

Limitar String por Tamanho Máximo

### Nível 2

Contar Ocorrências de Caractere com Limite

Repetir String até Alcançar Comprimento

Formatar Telefone com Prefixo e DDI

Gerar Código com Texto e Número

Truncar Texto com Sufixo
Truncar Texto com Prefixo
Truncar Texto com Infixo

Truncar Texto

### Nível 3

Validar Senha com Tamanho e Regras

Gerar Identificador Formatado

Validar Texto com Expressão

Formatar Texto com Máscara Numérica

Validar Entrada Mista com Regras Compostas


## Estruturas de Dados

### Com Arrays
### Com Objetos
### Com Sets
### Com Maps
### Com Estruturas Compostas
