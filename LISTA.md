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

console.log(somaParesEntre(4, 18)); // 88

console.log(somaParesEntre(18, 4)); // 0
console.log(somaParesEntre(-4, 4)); // -4 + -2 + 0 + 2 + 4 + 6 = 6

console.log(somaParesEntre(4.33, 8)); // null
console.log(somaParesEntre(4, 8)); // null
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

#### Contar Caracteres de uma String

Dada uma string, retornar a quantidade de caracteres nela sem usar o método `length`.

```js
const res = contarCaracteres("hello world");
console.log(res); // 11
console.log(contarCaracteres("JavaScript")); // 10
console.log(contarCaracteres("123abc!@#")); // 10

// casos especiais
console.log(contarCaracteres("")); // 0
console.log(contarCaracteres()); // undefined
console.log(contarCaracteres(12345)); // undefined
```

#### Converter String para Maiúsculas

Considere uma string, retornar a mesma string em letras maiúsculas. Não usar o método `toUpperCase`, ao invés, implementar a lógica manualmente com base na tabela ASCII, podendo usar os métodos `charCodeAt` e `fromCharCode`.

```js
const res = paraMaiusculas("hello world");
console.log(res); // "HELLO WORLD"  

console.log(paraMaiusculas("JavaScript")); // "JAVASCRIPT"
console.log(paraMaiusculas("123abc!@#")); // "123ABC!@#"

// casos especiais
console.log(paraMaiusculas("")); // ""
console.log(paraMaiusculas()); // undefined
```

#### Converter String para Minúsculas

Mesmo que anterior, mas para minúsculas.

#### Verificar String Vazia

Dada uma string, retornar se ela está vazia ou não, onde vazio é considerado uma string com comprimento zero ou composta apenas por espaços (' ', '\t', '\n', e '\r').

```js
const res = vazio("");
console.log(res); // true
console.log(vazio("hello")); // false
console.log(vazio(" ")); // true
console.log(vazio("   \t\n")); // true
console.log(vazio("  hello  ")); // false

// casos especiais
console.log(vazio()); // undefined
```

#### Retornar Primeiro Caractere

Dada uma string, retornar o primeiro caractere dela.

```js
const res = primeiroCaractere("hello");
console.log(res); // "h"
console.log(primeiroCaractere("world")); // "w"
console.log(primeiroCaractere("A")); // "A"
// casos especiais
console.log(primeiroCaractere("")); // ""
console.log(primeiroCaractere()); // undefined
console.log(primeiroCaractere(123)); // undefined
```

#### Retornar Último Caractere

Mesmo que anterior, mas o último caractere.

#### Verificar se Contém Substring

Dada uma string e uma substring, retornar se a string contém a substring.

```js
const res = contemSubstring("hello world", "world");
console.log(res); // true
console.log(contemSubstring("hello world", "hello")); // true
console.log(contemSubstring("hello world", "test")); // false
// casos especiais
console.log(contemSubstring("hello world", "")); // true
console.log(contemSubstring("", "test")); // false
console.log(contemSubstring("", "")); // true
console.log(contemSubstring()); // undefined
console.log(contemSubstring("hello world")); // undefined
console.log(contemSubstring(123, "23")); // undefined
console.log(contemSubstring(123)); // undefined
```

#### Remover Espaços das Extremidades (trim)

Considere uma string, retornar a mesma string sem espaços no início e no fim. Não usar o método `trim`, ao invés, implementar a lógica manualmente.

```js
const res = trim("   hello world   ");
console.log(res); // "hello world"
console.log(trim("   JavaScript   ")); // "JavaScript"
console.log(trim("   123abc!@#   ")); // "123abc!@#"

// casos especiais
console.log(trim("")); // ""
console.log(trim("      ")); // ""
console.log(trim()); // undefined
console.log(trim(123)); // undefined
```

### Nível 2

#### Contar Vogais em uma String

Dada uma string, retornar a quantidade de vogais nela.

```js
const res = contarVogais("hello world");
console.log(res); // 3
console.log(contarVogais("JavaScript")); // 3
console.log(contarVogais("AEIOU")); // 5
console.log(contarVogais("Aula")); // 3

// casos especiais
console.log(contarVogais("")); // 0
console.log(contarVogais("bcdfghjklmnpqrstvwxyz")); // 0
console.log(contarVogais()); // undefined
console.log(contarVogais(123)); // undefined
```

#### Contar Consoantes em uma String

Mesmo que anterior, mas para consoantes.

#### Inverter uma String

Dada uma string, retornar a mesma string invertida.

```js
const res = inverterString("hello");
console.log(res); // "olleh"
console.log(inverterString("JavaScript")); // "tpircSavaJ"
console.log(inverterString("123abc!@#")); // "#@!cba321"

// casos especiais
console.log(inverterString("")); // ""
console.log(inverterString()); // undefined
console.log(inverterString(123)); // undefined
```

#### Verificar Palíndromo (String)

Dada uma string, retornar se ela é um palíndromo, isto é, se lida de trás para frente resulta na mesma string. Os espaços e diferenças entre maiúsculas e minúsculas devem ser ignorados.

```js
const res = ehPalindromoString("racecar");
console.log(res); // true
console.log(ehPalindromoString("hello")); // false
console.log(ehPalindromoString("A man a plan a canal Panama")); // true
console.log(ehPalindromoString("12321")); // true

// casos especiais
console.log(ehPalindromoString("")); // true
console.log(ehPalindromoString()); // undefined
console.log(ehPalindromoString(12321)); // undefined
```

#### Remover Caracteres Repetidos

Dada uma string, retornar a mesma string sem caracteres repetidos. Lembrando que a ordem dos caracteres deve ser mantida e a primeira ocorrência de cada caractere deve ser preservada. Letras maiúsculas e minúsculas são consideradas diferentes.

```js
const res = removerRepetidos("hello world");
console.log(res); // "helo wrd"
console.log(removerRepetidos("JavaScript")); // "JavScript"
console.log(removerRepetidos("aaabbbccc")); // "abc"

// casos especiais
console.log(removerRepetidos("")); // ""
console.log(removerRepetidos()); // undefined
console.log(removerRepetidos(12345)); // undefined
```

#### Substituir Caracteres

Considere uma string, um caractere antigo e um novo caractere, retornar a string com todas as ocorrências do caractere antigo substituídas pelo novo caractere. Maiúsculas e minúsculas são consideradas diferentes.

```js
const res = substituirCaracteres("hello world", "o", "a");
console.log(res); // "hella warld"
console.log(substituirCaracteres("JavaScript", "a", "o")); // "JovoScript"
console.log(substituirCaracteres("123abc!@#", "a", "x")); // "123xbc!@#"

// casos especiais
console.log(substituirCaracteres("hello world", "z", "a")); // "hello world"
console.log(substituirCaracteres("", "a", "b")); // ""
console.log(substituirCaracteres()); // undefined
console.log(substituirCaracteres("hello world")); // undefined
console.log(substituirCaracteres(12345, "2", "9")); // undefined
const res = substituirCaracteres("hello world", "o", "ab"); // Error ("Novo caractere deve ser um único caractere")
```

#### Contar Palavras em uma String

Dada uma string, retornar a quantidade de palavras nela. Palavras são definidas como sequências de caracteres separadas por espaços. Espaços múltiplos devem ser tratados como um único separador, e espaços no início ou no fim da string não devem ser contados como palavras.

```js
const res = contarPalavras("hello world");
console.log(res); // 2
console.log(contarPalavras("JavaScript is awesome")); // 3
console.log(contarPalavras("  Leading and trailing spaces  ")); // 5

// casos especiais
console.log(contarPalavras("")); // 0
console.log(contarPalavras("     ")); // 0
console.log(contarPalavras()); // undefined
console.log(contarPalavras(12345)); // undefined
```

#### Capitalizar Primeira Letra de Cada Palavra

Dada uma string, retornar a mesma string com a primeira letra de cada palavra em maiúscula e o restante em minúscula. Não deve ser usado o método `toUpperCase` ou `toLowerCase`, ao invés, implementar a lógica manualmente com base na tabela ASCII, podendo usar os métodos `charCodeAt` e `fromCharCode`.

```js
const res = capitalizarPalavras("hello world");
console.log(res); // "Hello World"
console.log(capitalizarPalavras("javaSCRIPT is AWESOME")); // "Javascript Is Awesome"
console.log(capitalizarPalavras("  leading AND trailing SPACES  ")); // "  Leading And Trailing Spaces  "

// casos especiais
console.log(capitalizarPalavras("")); // ""
console.log(capitalizarPalavras("     ")); // "     "
console.log(capitalizarPalavras()); // undefined
console.log(capitalizarPalavras(12345)); // undefined
```

#### Remover Caracteres Especiais

Dada uma string, retornar a mesma string sem caracteres especiais, mantendo apenas letras (maiúsculas e minúsculas), números e espaços.

```js
const res = removerEspeciais("hello@world!");
console.log(res); // "hello world"
console.log(removerEspeciais("Java#Script$ is %awesome^")); // "JavaScript is awesome"
console.log(removerEspeciais("123abc!@#")); // "123abc"
// casos especiais
console.log(removerEspeciais("")); // ""
console.log(removerEspeciais("!@#$%^&*()")); // ""
console.log(removerEspeciais()); // undefined
console.log(removerEspeciais(12345)); // undefined
```

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
