# As Bases com JavaScript

As linguagens de programação servem para nós expressarmos o que queremos que o computador faça. Como os idiomas humanos, elas são diferentes na escrita (sintaxe) e até na forma de organizar o pensamento (paradigma de programação). Até usando a mesma linguagem podemos encontrar diversas maneiras de resolver um mesmo problema. No entanto, todas essas linguagens compartilham construtos comuns para guardar o estado do programa, decidir o que fazer dada uma condição, realizar um conjunto de tarefas um determinado número de vezes, obter e devolver informações, modularizar uma solução reutilizável, etc. Esse guia apresenta esses construtos usando a linguagem de programação JavaScript.

## Sumário

- [As Bases com JavaScript](#as-bases-com-javascript)
  - [Sumário](#sumário)
  - [Introdução](#introdução)
    - [História do JavaScript o/](#história-do-javascript-o)
    - [Linguagem interpretada o/](#linguagem-interpretada-o)
    - [Linguagem de Tipagem Dinâmica o/](#linguagem-de-tipagem-dinâmica-o)
    - [Linguagem de Tipagem Fraca o/](#linguagem-de-tipagem-fraca-o)
    - [Ambiente de Execução o/](#ambiente-de-execução-o)
    - [Instalando o Node.js o/](#instalando-o-nodejs-o)
  - [Estado e Computação](#estado-e-computação)
    - [Valores o/](#valores-o)
    - [Variáveis e Constantes o/](#variáveis-e-constantes-o)
    - [Operadores o/](#operadores-o)
    - [Expressões, Sentenças, Declarações e Blocos](#expressões-sentenças-declarações-e-blocos)
  - [Estruturas de Controle](#estruturas-de-controle)
    - [Estrtuturas Condicionais](#estrtuturas-condicionais)
    - [Estruturas de Repetição](#estruturas-de-repetição)
    - [Estruturas para o Tratamento de Exceções](#estruturas-para-o-tratamento-de-exceções)
  - [Funções](#funções)
    - [Declaração de Funções](#declaração-de-funções)
    - [Retorno de Funções](#retorno-de-funções)
    - [Composição de Funções](#composição-de-funções)
    - [Funções Anônimas e Arrow Functions](#funções-anônimas-e-arrow-functions)
  - [Programação Modular](#programação-modular)
    - [Projetos JavaScript](#projetos-javascript)
    - [Programação Modular em JavaScript](#programação-modular-em-javascript)
    - [Biblioteca Padrão do JavaScript](#biblioteca-padrão-do-javascript)
  - [Estruturas de Dados em JavaScript](#estruturas-de-dados-em-javascript)
    - [Estruturas de Dados Elementares](#estruturas-de-dados-elementares)
      - [Notação Literal de Objetos em JavaScript](#notação-literal-de-objetos-em-javascript)
      - [Classes e Objetos em JavaScript](#classes-e-objetos-em-javascript)
      - [Arrays (listas)](#arrays-listas)
      - [Conjuntos](#conjuntos)
      - [Mapas](#mapas)
    - [Estruturas de Dados Compostas](#estruturas-de-dados-compostas)
    - [Estruturas de Dados Inexistentes em JavaScript](#estruturas-de-dados-inexistentes-em-javascript)
  - [Considerações Finais](#considerações-finais)


## Introdução

### História do JavaScript o/

A história serve para compreender o presente através do passado.

Até meados dos ano 90 a web era estática. A empresa por trás do navegador (Netscape) mais popular da época, a Netscape Communications usava Java (Java Applets) para adicionar recursos dinâmicos nos web sites. No entanto, eles queriam uma linguagem nova, que fosse desenhada especificamente para a web e que se integrasse naturalmente ao browser -- diferente de Java. Assim, em abril de 1995 contrataram o programador Brendan Eich (hoje -2025- CEO da Brave Software) para desenvolver uma linguagem dinâmica, simples e adequada aos recursos da web e dos navegadores. Eich desenvolveu um protótipo funcional da linguagem (incluindo o runtime para execução) em incríveis 10 dias. pois a pressão por prazo era enorme. A linguagem foi chamada inicialmente de "Mocha" (havia até um loguinho de café), depois LiveScript, mas a Netscape queria pegar carona na popularidade da linguagem Java e renomeou a linguagem para JavaScript em dezembro de 95. O nome ajudou a impulsionar o marketing no hype em torno de Java à época, mas ao custo dos desenvolvedores ficaram confusos, até hoje, com as duas linguagens, pois a parte um pouco da sintaxe, as duas linguagens são bem diferentes. Brendan, em vez de tomar influencia apenas de Java (como pediram os empresários) para desenhar a linguagem, pegou emprestado características de programação orientada a objetos e funcional inspiradas nas linguagens Self (herança prototípica) e Scheme (programação funcional), fazendo dela uma linguagem um pouco "diferente" do tradicional em certo aspectos.

Nesta época acontecia a guerra dos navegadores: competiam o Netscape, Internet Explorer da Microsoft, Mosaic e outros, até o fim da década de 90 e início dos 2000. Com isso, a Microsoft criou sua própria implementação chamada JScript (uma versão customizada e em muitos aspectos, imcompatível), para o seu navegador da época, o Internet Explorer 3. Essa ausência de padrão era parte da "guerra dos navegadores", onde os desenvolvedores se viravam para escrever código JavaScript que executasse tanto no Internet Explorer (JScript) como nos outros. Isso levou a Netscape Communications a submeter o JavaScript à European Computer Manufacturers Association (ECMA) para documentar e padronizar, resultando na especificação ECMAScript (ECMA-262), publicada pela primeira vez em junho de 1997. Enquanto o JavaScript é a implementação usada nos navegadores, o ECMAScript é a especificação oficial e neutra em relação aos fornecedores. A versão atualizada do ECMA está disponível em https://tc39.es/ecma262/2025/

Por bastante tempo, JavaScript não foi considerada uma linguagem para projetos sérios, sendo tomada como uma "linguagem de brinquedo" para validar formulários -- e abrir pop-ups. Isso mudou por volta de 2005 com a popularização do uso de AJAX (Asynchronous JavaScript and XML) nas páginas, uma técnica que permitia que páginas da web atualizassem apenas parte do conteúdo,  dinamicamente e sem recarregar a página inteira (isso acontecia antes, acredite), como acontece no Gmail, Google Maps, Instagram e todas as aplicações web modernas.

JavaScript ainda veio a ter um segundo salto de popularidade quando quando Ryan Dahl introduziu o Node.js em 2009, extraindo o motor de execução do JavaScript do browser Chrome (o V8 Engine) e permitindo que o JavaScript fosse executado no lado do servidor, fora do navegador. Neste caso, fazendo o JavaScript ser usado tanto para desenvolvimento front-end quanto back-end, criando o "JavaScript omni-stack" e solidificando seu papel como uma linguagem séria, de uso abrangente e de propósito geral.

Nos dias atuais, JavaScript é amplamente utilizada¹, tornando-se uma linguagem de programação multipropósito, permitindo o desenvolvimento para Web, Desktop (para Windows, Mac OS, Linux, através do Electron, ex.: Discord e Slack), Server-Side (aplicações no servidor) e Mobile (celular, tablets e dispositvos móveis e geral).
rd, Slack, etc.

¹ _Most popular technologies_, em: https://survey.stackoverflow.co/2025/technology

### Linguagem interpretada o/

JavaScript é uma linguagem interpretada, assim como PHP, Python e Ruby, em oposição a uma linguagem compilada como C, Java e Rust. Por interpretada, entende-se que o código fonte é executado diretamente por um interpretador, sem a necessidade de um processo de compilação prévio para transformar o código fonte em código de máquina executável.

No navegador, o interpretador de JavaScript é parte do motor do navegador (como V8 no Google Chrome e Node.js, SpiderMonkey no Firefox, JavaScriptCore no Safari, etc.). Em ambientes fora do navegador, como o Node.js, o interpretador é parte do ambiente de execução.

Experimente o interpretador agora mesmo abrindo o console do seu navegador (geralmente com F12 ou Ctrl+Shift+J) e digite:

```javascript
alert(`Olá, ${prompt("Qual é o seu nome?")}!`);
```


### Linguagem de Tipagem Dinâmica o/

JavaScript é uma linguagem de tipagem dinâmica, assim como Python, Ruby e PHP, em oposição a linguagens de tipagem estática como C, C# e Java. Por tipagem dinâmica, entende-se que o tipo de uma variável é pós-determinado e conhecido em tempo de execução, permitindo maior flexibilidade na atribuição de valores. Isto é, o tipo não é declarado junto com a variável, permitindo que a variável assuma o tipo do valor que é atribuído a no momento e podendo mudar ao longo do tempo.

Experimente agora mesmo no console do seu navegador:

```javascript
var valor = 42; // valor é um número
console.log(typeof valor); // "number"
valor = "Olá, mundo!"; // agora valor é uma string
console.log(typeof valor); // "string"
valor = {};
console.log(typeof valor); // "object"
```

### Linguagem de Tipagem Fraca o/

JavaScript é uma linguagem de tipagem fraca (_weak typing_), assim como PHP e Perl, em oposição a linguagens de tipagem forte (_strong typing_) como Python, Ruby e Java. Por tipagem fraca, entende-se que o interpretador realiza conversões automáticas entre tipos de dados quando necessário. Também é possível realizar diversas operações com variáveis e literais de tipos diferentes, como subtrair uma string a um número, verificar se um número é maior que um array, comparar se um valor booleano é igual a uma string, etc. Essas conversões automáticas podem levar a resultados inesperados se o programador não for ciente dessas regras de coerção de tipos, que são complexas e implícitas.

Considere os seguintes exemplos:

```javascript
let x = '8';
console.log(typeof x); // "string"
let y = 3;
console.log(typeof y); // "number"

let z = x + y; // somar prioriza a conversão de y para string e concatenação
console.log(typeof z); // "string"
console.log(z); // "83" (concatenação de string)

let w = x - y; // subtrair prioriza a conversão de x para número e subtração
console.log(typeof w); // "number"
console.log(w); // 5 (subtração numérica)

if (x > y) { // comparação numérica, x é convertido para número
    console.log(`${x} é maior que ${y}`);
} else {
    console.log(`${x} não é maior que ${y}`);
} // "8 é maior que 3"

if (x == (y + 5)) { // comparação frouxa, y + 5 (8) é convertido para string
    console.log(`${x} é igual a ${y + 5}`);
} else {
    console.log(`${x} não é igual a ${y + 5}`);
} // "8 é igual a 8"

// para considerar o tipo na comparação, use o operador de igualdade estrita (===) --- três símbolos de igual
if (x === (y + 5)) {
    console.log(`${x} é estritamente igual a ${y + 5}`);
} else {
    console.log(`${x} não é estritamente igual a ${y + 5}`);
} // "8 não é estritamente igual a 8"
```

Ainda existe a questão dos valores especiais `null` e `undefined`, que podem causar confusão em certas situações:

```javascript
let a; // variável declarada, mas não inicializada
console.log(a); // undefined
console.log(typeof a); // "undefined"
let b = null; // variável inicializada com null
console.log(b); // null
console.log(typeof b); // "object" (isso é um bug histórico em JavaScript)
```

A tipagem fraca é normalmente usada para tirar vantagem na comparação booleana, com os conceitos de truthy e falsy values (valores verídicos e não verídicos em contexto booleano). Em JavaScript, os seguintes valores são considerados falsy (falsos) em um contexto booleano:

- `false`
- `0` (zero)
- `0n` (BigInt zero)
- `""` (string vazia)
- `null`
- `undefined`
- `NaN` (Not a Number)
- `0.0` (zero ponto flutuante)

Todos os outros valores são considerados truthy (verdadeiros) em um contexto booleano.

Considere as seguintes comparações:

```javascript
var valor;

if (valor) console.log("valor é verdadeiro"); // não é

valor = "";
if (valor) console.log("valor é verdadeiro"); // não é

valor = 0;
if (valor) console.log("valor é verdadeiro"); // não é

valor = "JavaScript";
if (valor) console.log("valor é verdadeiro"); // é
```


### Ambiente de Execução o/

JavaScript é executado em diversos ambientes e plataformas, desde que seja disponibilizado um JavaScript _engine_ (motor (interpretador) JavaScript). Os ambientes mais comuns são os navegadores web e a plataforma Node.js. Cada ambiente fornece APIs específicas que permitem interagir com o sistema onde o JavaScript está sendo executado. Por exemplo, em um navegador você pode pegar a localização geográfica do usuário através da API de Geolocalização, enquanto no Node.js você pode acessar o sistema de arquivos onde o código está rodando (isto não é possível no navegador, seria uma incrível falha de segurança).

Teste você mesmo no console do navegador:

```javascript
navigator.geolocation.getCurrentPosition(function(position) {
    console.log(`Eu estou em Latitude: ${position.coords.latitude} e Longitude: ${position.coords.longitude}`);
});
```

O objeto `navigator` é uma API específica do ambiente do navegador e não está disponível no Node.js, por exemplo.

Para executar JavaScript fora do navegador é necessário instalar o Node.js. Se já está instalado, o código a seguir lista os arquivos no diretório atual (semelhante ao comando `ls` no Linux/Mac ou `dir` no Windows):

```javascript
const fs = require('fs');
fs.readdir('.', (err, files) => {
    if (!err) {
        console.log('Arquivos no diretório atual:');
        files.forEach(console.log(file));
    } else {
        console.error('Erro ao ler o diretório:', err);
    }
});
```

Este código não funciona em navegadores, pois a API `fs` (_file system_) é específica do Node.js e não está disponível em ambientes web por razões de segurança.


### Instalando o Node.js o/

Para instalar o Node.js, siga os passos abaixo:

1. Acesse o site oficial do Node.js: [https://nodejs.org/](https://nodejs.org/);
2. Baixe o instalador adequado para o seu sistema operacional (Windows, macOS, Linux) -- de preferência a versão LTS (Long Term Support -- suporte de longo prazo);
3. Execute o instalador e siga as instruções no assistente de instalação;
4. Após a instalação, abra o terminal (Prompt de Comando no Windows, Terminal no macOS/Linux) e verifique se o Node.js foi instalado corretamente:


```bash
node -v
```

O comando anterior deve exibir a versão do Node.js instalada.

Há três maneiras para executar um código JavaScript usando o Node.js:

1. **REPL (Read-Eval-Print Loop)**: Abra o terminal e digite `node` para iniciar o REPL interativo. Você pode digitar comandos JavaScript diretamente e ver os resultados imediatamente, como: `console.log("Olá, mundo!");`;
2. **Arquivo JavaScript**: Crie um arquivo com a extensão `.js` (por exemplo, `programinha.js`) e escreva seu código JavaScript nele. Depois, execute o arquivo no terminal com o comando `node programinha.js`;
3. **Executar código diretamente no terminal**: Você pode executar um comando JavaScript diretamente no terminal usando o comando `node -e "console.log('Olá, mundo!');"`.

```js
// programinha.js
console.log("Um programinha JavaScript") // o ; é opcional, mas recomendado!
```

Recortes pequenos de código neste guia podem ser testados diretamente no console do navegador, no REPL do Node.js ou diretamente no terminal (3ra opção acima). Exemplos maiores podem ser salvos em arquivos `.js` e executados com o Node.js. Os projetos mais complexos serão criados usando o gerenciador de pacotes `npm` (Node Package Manager), que é instalado automaticamente junto com o Node.js (e que será explicado mais adiante nesse guia).


## Estado e Computação

Esta seção apresenta os conceitos básicos de valores, variáveis, operadores, expressões, sentenças, declarações e blocos em JavaScript.

### Valores o/

Em JavaScript e demais linguagens, as informações são valores declarados no código. Valores são as unidades básicas de dados que o programa manipula. Eles podem ser números, textos, objetos, funções, listas, entre outros. Tenha em consideração que **cada valor tem um tipo associado a ele**, que determina como o valor pode ser usado e quais operações podem ser realizadas sobre ele.

JavaScript possui duas categorias principais de valores: primitivos e objetos. Primeiramente, vamos explorar os primitivos, listados abaixo:

- `number`: representa números, tanto inteiros quanto de ponto flutuante (ex: `42`, `3.14`, `-7`, `2.8e3`) e também valores especiais como `Infinity`, `-Infinity` e `NaN` (_Not a Number_ -- não é um número);
- `string`: representa sequências de caracteres (ex: `"Olá, mundo!"`);
- `boolean`: representa valores lógicos, `true` ou `false`;
- `undefined`: representa uma variável que foi declarada, mas não inicializada;
- `null`: representa a ausência intencional de qualquer valor;
- `symbol`: representa um identificador único e imutável (introduzido no ECMAScript 6);
- `bigint`: representa números inteiros muito grandes (introduzido no ECMAScript 2020).

Experimente o seguinte código:

```javascript
// a seguir os tipos de diversos valores literais em JavaScript:
console.log(typeof 42); // "number"
console.log(typeof "Olá, mundo!"); // "string"
console.log(typeof true); // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null); // "object"
console.log(typeof Symbol("id")); // "symbol"
console.log(typeof 9007199254740991n); // "bigint"

// Os números especiais são resultados de operações matemáticas inválidas, tais como:
console.log(2 / 0); // Infinity
console.log("texto" / 2); // NaN
```

Números em JavaScript são representados usando o formato de ponto flutuante de 64 bits (IEEE 754). Isso significa que há limitações na precisão dos números, especialmente para números muito grandes ou muito pequenos. Além disso, operações aritméticas podem resultar em imprecisões devido à forma como os números são representados internamente. Por exemplo:

```javascript
console.log(0.1 + 0.2); // 0.300000000
```

Números gastam 64 bits, enquanto strings usam 16 bits por caractere (UTF-16). Portanto, manipular strings pode ser mais custoso em termos de memória do que manipular números. A seguinte string gasta 80 bits (5 caracteres x 16 bits):

```javascript
var saudacao = "Olá!";
console.log(saudacao.length); // 5 caracteres
```

Cada caractere em uma string pode ser acessado individualmente usando a notação de colchetes:

```javascript
//    índices: 0123456789
var palavra = "JavaScript";
console.log(palavra[0]); // "J"
console.log(palavra[4]); // "S"
console.log(palavra[10]); // undefined (índice fora do alcance)
```

Strings literais são definidas com aspas simples (`'`), aspas duplas (`"`) ou crases (`` ` ``). As crases permitem a interpolação de variáveis e expressões usando `${}`:

```javascript
var nome = "Alice";
var sobrenome = 'Silva';
var idade = 25;
// Usando concatenação tradicional:
console.log("Olá, " + nome + " " + sobrenome + "! Você tem " + idade + " anos."); // "Olá, Alice Silva! Você tem 25 anos."
// Usando template literals (crases) com interpolação:
console.log(`Olá, ${nome} ${sobrenome}! Você tem ${idade} anos.`); // "Olá, Alice Silva! Você tem 25 anos."
```

Cada caractere em uma string tem um código numérico associado a ele, conhecido como código Unicode. Você pode obter o código Unicode de um caractere usando o método `charCodeAt()`:

```javascript
var palavra = "JavaScript";
console.log(palavra.charCodeAt(0)); // 74 (código Unicode de "J")
console.log(palavra.charCodeAt(4)); // 83 (código Unicode de "S")
console.log("A".charCodeAt(0)); // 65
console.log("a".charCodeAt(0)); // 97
console.log("€".charCodeAt(0)); // 8364
```

Da mesma forma, é possível obter o caractere correspondente a um código Unicode usando o método `String.fromCharCode()`:

```javascript   
console.log(String.fromCharCode(74)); // "J"
console.log(String.fromCharCode(83)); // "S"
console.log(String.fromCharCode(65)); // "A"
```

### Variáveis e Constantes o/

Variáveis são usadas para armazenar valores que podem ser alterados durante a execução do programa. Em JavaScript, você pode declarar variáveis usando as palavras-chave `var`, `let` ou `const`, embora este último não possa ser redeclarada nem reatribuída (não é tanto uma variável ao pé da letra). A diferença entre elas está no escopo e na mutabilidade:

- `var`: tem escopo global ou de função e pode ser reatribuída e até redeclarada no mesmo escopo; 
- `let`: tem escopo de bloco e pode ser reatribuída, mas não pode ser redeclarada no mesmo escopo;
- `const`: tem escopo de bloco e não pode ser redeclarada nem reatribuída.

Exemplos de declaração e uso de variáveis e constantes:

```javascript
var idade = 30; // declaração com var
let nome = "João"; // declaração com let
const PI = 3.14; // declaração com const
console.log(`Nome: ${nome}, Idade: ${idade}, PI: ${PI}`);

// Reatribuição de variáveis:
idade = 31; // válido, idade agora é 31
nome = "Maria"; // válido, nome agora é "Maria"
PI = 3.14159; // inválido, gera um TypeError: Assignment to constant variable.

// Redeclaração:
var idade = 32; // válido com var
let nome = "Carlos"; // inválido, gera um SyntaxError: Identifier 'nome' has already been declared
const PI = 3.14159; // inválido, gera um SyntaxError: Identifier 'PI' has already been declared
```

Quanto ao escopo, veja os exemplos abaixo:

```javascript
function exemploVar() {
    if (true) {
        var x = 10; // x tem escopo de função
        let y = 20; // y tem escopo de bloco
    }
    console.log(x); // 10 (válido, x está no escopo da função e é visível aqui)
    console.log(y); // 20 (inválido, gera um ReferenceError: y is not defined, pois y está fora do escopo do bloco if)
}
```

A ordem de preferência para declarar variáveis em JavaScript é: 

1. `const` - para valores que não devem ser reatribuídos;
2. `let` - para valores que podem ser reatribuídos, mas não redeclarados no mesmo escopo;
3. `var` - apenas quando necessário, devido ao seu escopo mais amplo e comportamento legado.


### Operadores o/

Operadores são símbolos ou palavras-chave que realizam operações sobre valores, transformando-os em novos valores. Eles podem ser classificados nas seguintes categorias:

- Operadores **Aritméticos**: realizam operações matemáticas básicas, como adição (`+`), subtração `-`, multiplicação `*`, divisão `/`, potência `**`, e módulo `%` ou resto da divisão;
- Operadores de **Comparação**: comparam dois valores e retornam um valor booleano `true` ou `false`, sendo _igual a_ `==`, _estritamente igual a_ `===`, _diferente de_ `!=`, _maior que_ `>`, _menor que_ `<`, _maior ou igual a_ `>=`, e _menor ou igual a_ `<=`;
- Operadores **Lógicos**: combinam valores booleanos e retornam um valor booleano, como: _E_ `&&`, _OU_ `||`, e _NÃO_ `!`.
- Operadores de **Atribuição**: atribuem valores a variáveis. O operador mais comum é o igual `=`, mas existem também operadores compostos como adição e atribuição `+=`, subtração e atribuição `-=`, multiplicação e atribuição `*=`, e divisão e atribuição `/=`.
- Operadores de **Incremento e Decremento**: aumentam ou diminuem o valor de uma variável em 1. O operador de incremento é `++` e o de decremento é `--`. Ainda podem ser usados na forma prefixada (`++variavel`, `--variavel`) ou pós-fixada (`variavel++`, `variavel--`).
- Operadores **Ternários**: uma forma concisa de expressar uma condição. A sintaxe é `condição ? valorSeVerdadeiro : valorSeFalso`;
- Operadores de **Tipo**: retornam o tipo de um valor. O operador `typeof` retorna uma string indicando o tipo do operando, por exemplo, `typeof 42` retorna `"number"`;
- Operadores **Bit a Bit**: realizam operações a nível de bits em números. Exemplos incluem _E bit a bit_ `&`, _OU bit a bit_ `|`, _XOR bit a bit_ `^`, _deslocamento à esquerda_ `<<`, _deslocamento à direita com sinal_ `>>`, e _deslocamento à direita sem sinal_ `>>>`.

Os trechos a seguir são curtos e podem ser testados diretamente no console do navegador ou no REPL do Node.js.

Exemplos de uso dos operadores aritméticos:

```javascript
console.log(5 + 3); // 8
console.log(10 - 4); // 6
console.log(6 * 7); // 42
console.log(20 / 5); // 4
console.log(2 ** 3); // 8 (2 elevado à potência de 3)
console.log(10 % 3); // 1 (resto da divisão de 10 por 3)
```

Exemplos de uso dos operadores de comparação:

```javascript
console.log(5 == '5'); // true (igualdade frouxa)
console.log(5 === '5'); // false (igualdade estrita, tipos diferentes)
console.log(5 != 3); // true
console.log(5 > 3); // true
console.log(5 < 10); // true
console.log(5 >= 5); // true
console.log(3 <= 2); // false
// Cuidados com NaN (Not a Number):
console.log(5 > 'teste'); // false (comparação numérica, 'teste' é considerado NaN e nada é maior que NaN)
console.log(5 < 'teste'); // false (comparação numérica, 'teste' é considerado NaN e nada é menor que NaN)
console.log(5 == NaN); // false (NaN não é igual a nada, nem mesmo a ele mesmo)
console.log(NaN === NaN); // false (NaN não é estritamente igual a nada, nem mesmo a ele mesmo)
```

Exemplos de uso dos operadores lógicos:

```javascript
// com booleanos literais:
console.log(true && false); // false
console.log(true || false); // true
console.log(!true); // false
console.log(!false); // true
// com valores e expressões:
console.log((5 > 3) && (2 < 4)); // true
console.log((5 > 3) || (2 > 4)); // true
console.log(!(5 === 5)); // false
```

Exemplos de uso dos operadores de atribuição:

```javascript
let x = 10; // atribuição simples
x += 5; // equivalente a x = x + 5
console.log(x); // 15
x -= 3; // equivalente a x = x - 3
console.log(x); // 12
x *= 2; // equivalente a x = x * 2
console.log(x); // 24
x /= 4; // equivalente a x = x / 4
console.log(x); // 6
```

Exemplos de uso dos operadores de incremento e decremento:

```javascript
let y = 5;
console.log(y++); // 5 pós-incremento
console.log(y); // 6
console.log(++y); // 7 pré-incremento
console.log(y); // 7

console.log(y--); // 7 pós-decremento
console.log(y); // 6
console.log(--y); // 5 pré-decremento
console.log(y); // 5
```

Exemplo de uso do operador ternário:

```javascript
const idade = 20;
const podeDirigir = (idade >= 18) ? "Sim" : "Não";
console.log(podeDirigir); // "Sim" porque idade tem o valor 20 e o valor 20 é maior que o valor 18
```

Exemplo de uso do operador `typeof` para verificar o tipo de um valor:

```javascript
console.log(typeof 42); // "number"
console.log(typeof "Olá"); // "string"
console.log(typeof true); // "boolean"

// pode ser usado para verificar o tipo de variáveis também:
let valor = {};
console.log(typeof valor); // "object"

// pode ser chamado como uma função, entre parênteses:
console.log(typeof(valor)); // "object"
```

Exemplos de uso dos operadores bit a bit:

```javascript
console.log(5 & 3); // 1 (0101 & 0011 = 0001 = 1)
console.log(5 | 3); // 7 (0101 | 0011 = 0111 = 7)
console.log(5 ^ 3); // 6 (0101 ^ 0011 = 0110 = 6)
console.log(5 << 1); // 10 (0101 << 1 = 1010 = 10)
console.log(5 >> 1); // 2 (0101 >> 1 = 0010 = 2)
console.log(5 >>> 1); // 2 (0101 >>> 1 = 0010 = 2)
```

### Expressões, Sentenças, Declarações e Blocos

Em JavaScript, uma **expressão** é qualquer fragmento de código que produz um valor. Pode ser tão simples quanto um número ou uma string literal, ou tão complexo quanto uma chamada de função ou uma operação matemática. Por exemplo:

```javascript
5 + 3; // expressão que produz o valor 8
"Olá, " + "mundo!"; // expressão que produz a string "Olá, mundo!"
Math.max(5, 10); // expressão que produz o valor 10
```

Sentenças (ou instruções) são unidades completas de código que realizam uma ação. Elas podem incluir expressões, mas também podem conter palavras-chave e estruturas de controle. As sentenças geralmente terminam com um ponto e vírgula (`;`), embora em muitos casos o JavaScript permita omiti-lo. Exemplos de sentenças incluem:

```javascript
let x = 10; // declaração de variável (sentença)

console.log(x); // chamada de função (sentença)
if (x > 5) { // sentença condicional
    console.log("x é maior que 5");
}
```

As declarações são um tipo específico de sentença que introduz novas variáveis, funções ou outras entidades no escopo atual. Exemplos de declarações incluem:

```javascript
let y = 20; // declaração de variável

function dobro(n) { // declaração de função
    return n * 2;
}
```

Os blocos são conjuntos de sentenças agrupadas entre chaves `{}`. Eles são usados para definir o escopo de variáveis e para agrupar sentenças em estruturas de controle, como loops e condicionais. Por exemplo:

```javascript
let x = 10;

if (x > 5) { // o bloco começa aqui
    const mensagem = "x é maior que 5";
    console.log(mensagem);
} // o bloco termina aqui   
```

Blocos podem ser aninhados dentro de outros blocos, permitindo a criação de estruturas complexas de controle de fluxo, por exemplo:

```javascript
for (let i = 0; i < 3; i++) { // bloco do loop
    console.log(`Iteração ${i}`);
    if (i % 2 === 0) { // bloco aninhado do if
        console.log(`${i} é um número par`);
    } else { // bloco aninhado do else
        console.log(`${i} é um número ímpar`);
    } // fim do bloco do else
} // fim do bloco do loop
```

A indentação do código dentro dos blocos é uma prática recomendada para melhorar a legibilidade, embora o JavaScript não exija isso sintaticamente.


## Estruturas de Controle

Estruturas de controle são usadas para controlar o fluxo de execução do código com base em condições ou repetições. As principais estruturas de controle em JavaScript incluem:

- Estruturas condicionais: `if`, `else if`, `else`, `switch`
- Estruturas de repetição: `for`, `while`, `do...while`
- Controle de loop: `break`, `continue`
- Tratamento de exceções: `try`, `catch`, `finally`, `throw`
- Declarações de término: `return`

### Estrtuturas Condicionais

A estrutura condicional mais simples é o `if`, que executa um bloco de código se uma condição for verdadeira:

```javascript
let idade = 20;
if (idade >= 18) {
    console.log("Você é maior de idade.");
}

// ainda, o bloco pode ser omitido se houver apenas uma sentença:
if (idade >= 18) console.log("Você é maior de idade.");
```

Estruturas mais complexas podem ser criadas usando `else if` e `else`:

```javascript
let nota = 8.5;
if (nota >= 9) {
    console.log("A");
} else if (nota >= 8) {
    console.log("B");
} else if (nota >= 7) {
    console.log("C");
} else if (nota >= 6) {
    console.log("D");
} else if (nota >= 5) {
    console.log("E");
} else {
    console.log("F");
}
```

A seguir uma representação visual do fluxo de uma estrutura condicional com `if`, `else if` e `else`:

```
         +-------------------+
         |   Início          |
         +-------------------+
                  |
                  v
         +-------------------+
         |  Verifica nota >=9?|
         +-------------------+
          /        \
        Sim        Não
       /            \
      v              v
+-------------------+   +-------------------+
|  Imprime "A"     |   | Verifica nota >=8?|
+-------------------+   +-------------------+
                        /        \
                      Sim        Não
                     /            \
                    v              v
            +-------------------+   +-------------------+
            |  Imprime "B"     |   | Verifica nota >=7?|
            +-------------------+   +-------------------+
                                    /        \
                                  Sim        Não
                                 /            \
                                v              v
                        +-------------------+   +-------------------+
                        |  Imprime "C"     |   | Verifica nota >=6?|
                        +-------------------+   +-------------------+
                                                /        \
                                              Sim        Não
                                             /            \
                                            v              v
                                    +-------------------+   +-------------------+
                                    |  Imprime "D"     |   | Verifica nota >=5?|
                                    +-------------------+   +-------------------+
                                                            /        \
                                                          Sim        Não
                                                         /            \
                                                        v              v
                                                +-------------------+   +-------------------+
                                                |  Imprime "E"     |   |  Imprime "F"     |
                                                +-------------------+   +-------------------+
```

O `switch` é outra estrutura condicional que pode ser usada quando há múltiplas condições baseadas no valor de uma variável:

```javascript
let dia = new Date().getDay(); // 0 (Domingo) a 6 (Sábado)
switch (dia) {
    case 0:
        console.log("Domingo");
        break;
    case 1:
        console.log("Segunda-feira");
        break;
    case 2:
        console.log("Terça-feira");
        break;
    case 3:
        console.log("Quarta-feira");
        break;
    case 4:
        console.log("Quinta-feira");
        break;
    case 5:
        console.log("Sexta-feira");
        break;
    case 6:
        console.log("Sábado");
        break;
    default:
        console.log("Dia inválido");
}
```

No caso de uso de switches, o uso do `break` é crucial para evitar o _"fall through"_, onde a execução continua para os casos subsequentes mesmo após encontrar uma correspondência. Por outro lado, existem casos em que o _"fall through"_ é desejado, como no exemplo abaixo:

```javascript
let caractere = 'I';
switch (caractere) {
    case 'A':
    case 'E':
    case 'I': // fall through intencional
    case 'O':
    case 'U':
        console.log(`${caractere} é uma vogal.`);
        break;
    default:
        console.log(`${caractere} é uma consoante.`);
}
```

### Estruturas de Repetição

Use o `while` para repetir um bloco de código enquanto uma condição for verdadeira:

```javascript
let surpresa = "ah";
let nivelSurpresa = 10;
while (surpresa.length < nivelSurpresa) {
    surpresa += "h";
    if (surpresa.length == nivelSurpresa) surpresa += "!";
}
console.log(surpresa); // "ahhhhhhhhh!"
```

O mesmo código pode ser escrito usando `do/while`, que garante que o bloco seja executado pelo menos uma vez:

```javascript
let surpresa = "ah";
let nivelSurpresa = 2;
do {
    surpresa += "h";
    if (surpresa.length == nivelSurpresa) surpresa += "!";
} while (surpresa.length < nivelSurpresa);
console.log(surpresa); // "ah!"
```

E todos os exemplos acima podem ser escritos usando `for`, que é especialmente útil quando o número de iterações é conhecido:

```javascript
let surpresa = "ah";
let nivelSurpresa = 5;
for (let i = surpresa.length; i < nivelSurpresa; i++) {
    surpresa += "h";
    if (surpresa.length == nivelSurpresa) surpresa += "!";
}
console.log(surpresa); // "ahhhh!"
```

### Estruturas para o Tratamento de Exceções

Em JavaScript, o tratamento de exceções é realizado usando as palavras-chave `try`, `catch`, `finally` e `throw`. Esses construtos para o tratamento de fluxos excepcionais também é usada por outras linguagens, tais como Java e C#. Eles permitem que você lide com erros de forma controlada, evitando que o programa falhe abruptamente -- exceto se nenhuma exceção for capturada. 

A implementação começa pelas funções que podem lançar exceções usando a instrução `throw`, como `throw new Error("mensagem de erro")`. As exceções são lançadas quando há algum problema que impede a função de computar ou retornar um valor válido. As condições são testadas condicionalmente e podem ocorrer por diversas razões, desde um parâmetro inválido, como informar uma quantidade negativa para um produto, até um estado inconsistente ou impossível de atingir, por exemplo, tentar sacar de uma conta bancária com saldo insuficiente.

Por exemplo, considere uma função para calcular as parcelas acumulando os centavos na última:

```javascript
function calcularParcelas(valorEmprestimo, numeroParcelas, taxaJuros) {
    if (typeof valorEmprestimo !== 'number' || typeof numeroParcelas !== 'number' || typeof taxaJuros !== 'number') {
        throw new Error("Parâmetros inválidos: todos devem ser números.");
    }
    if (valorEmprestimo < 100) {
        throw new Error("O valor do empréstimo deve ser pelo menos 100.");
    }
    if (numeroParcelas < 2) {
        throw new Error("O número de parcelas deve ser pelo menos 2.");
    }
    if (taxaJuros < 0) {
        throw new Error("A taxa de juros não pode ser negativa.");
    }
    if (taxaJuros > 1) {
        throw new Error("A taxa de juros deve ser um valor decimal (por exemplo, 0.05 para 5%).");
    }
    // calcular os juros compostos
    const montante = valorEmprestimo * Math.pow((1 + taxaJuros), numeroParcelas);
    const valorFinalEmprestimo = montante;
    // fazer o calculo inteiro da parcela
    const valorParcela = Math.floor(valorFinalEmprestimo / numeroParcelas);
    // acumular o resto para adicionar à última parcela
    const resto = valorFinalEmprestimo % numeroParcelas;
    // adicionar o resto à última parcela
    const valorUltimaParcela = valorParcela + resto;

    return { valorEmprestimo, numeroParcelas, valorParcela, valorUltimaParcela };
}


// Usando a função com tratamento de exceções:
try {
    const resultado = calcularParcelas(1000, 5, 0.05); // parâmetros válidos
    console.log("Cálculo das parcelas:", resultado);
} catch (erro) {
    console.error("Erro ao calcular parcelas:", erro.message); // não será executado neste caso
}

try {
    const resultado = calcularParcelas(50, 1, -0.1); // parâmetros inválidos
    console.log("Cálculo das parcelas:", resultado);
} catch (erro) {
    // será executado e exibirá a mensagem: "O valor do empréstimo deve ser pelo menos 100."
    console.error("Erro ao calcular parcelas:", erro.message); 
}

try {
    const resultado = calcularParcelas(100, 1, -0.1); // parâmetros inválidos
    console.log("Cálculo das parcelas:", resultado);
} catch (erro) {
    // será executado e exibirá a mensagem: "O número de parcelas deve ser pelo menos 2."
    console.error("Erro ao calcular parcelas:", erro.message); 
}
```

Note que a ordem das validações dentro da função é importante, pois a primeira condição que falhar lançará uma exceção, interrompendo a execução da função. Portanto, as validações devem ser organizadas de forma lógica para fornecer feedback útil ao usuário ou chamador da função.

Finalmente, o bloco `finally` pode ser usado para executar código que deve ser executado independentemente de uma exceção ter sido lançada ou não. Isso é útil para liberar recursos, fechar conexões ou realizar outras tarefas de limpeza, mais comuns quando usamos recuros externos, como arquivos ou conexões de rede. Aqui está um exemplo sintético simples:

```javascript
function exemploFinally() { // abrindo, executando um sql e fechando uma conexão fictícia:
    let conexao = null;
    try {
        conexao = abrirConexaoBancoDeDados(); // função fictícia
        // executar operações no banco de dados
        console.log("Operações no banco de dados executadas com sucesso.");
    } catch (erro) {
        console.error("Erro ao executar operações no banco de dados:", erro.message);
    } finally {
        if (conexao) {
            conexao.fechar(); // função fictícia para fechar a conexão
            console.log("Conexão com o banco de dados fechada.");
        }
    }
}
```

## Funções

### Declaração de Funções

Funções são blocos reutilizáveis de código que realizam uma tarefa específica. Elas podem receber entradas (parâmetros), executar operações, faz computações e retornar um valor. Funções ajudam a organizar o código, sendo o primeiro passo na direção da **modularidade** e reutilização.

A anatomia básica de uma função em JavaScript inclui:

- **Declaração da função**: usando a palavra-chave `function`, seguida pelo nome da função e uma lista de parâmetros entre parênteses;
- **Corpo da função**: um bloco de código entre chaves `{}` que contém as instruções a serem executadas quando a função é chamada;
- **Retorno da função**: opcionalmente, uma função pode retornar um valor usando a palavra-chave `return`.

Funções podem ser chamadas (invocadas) pelo nome, passando os argumentos necessários. Aqui está um exemplo simples de uma função que soma dois números:

```javascript
function somar(a, b) {
    return a + b;
}

// Chamando a função e armazenando o resultado:
let resultado = somar(5, 3);
console.log(resultado); // 8
// Ou diretamente:
console.log(somar(10, 15)); // 25
```

A seguinte simbologia é usada para descrever a sintaxe das funções:

```plain
| Símbolo | Significado                    |
| ------- | ------------------------------ |
| `< >`   | Elemento obrigatório           |
| `[ ]`   | Elemento opcional              |
| `...`   | Continuação / repetição        |
```


A sintaxe geral para declarar uma função é:

```javascript
function <nome da função>([parametro 1, parametro 2, ...]) {
    // corpo da função
    [return valor];
}
```

Onde `nome da função` é o identificador da função e `parametro 1`, `parametro 2`, etc,  são os parâmetros opcionais que a função pode receber. Os identificadores devem seguir as regras de nomenclatura de variáveis em JavaScript, a saber:

- Devem começar com uma letra, sublinhado (`_`) ou cifrão (`$`);
- Podem conter letras, dígitos, sublinhados e cifrões;
- Não podem ser palavras reservadas da linguagem (como `if`, `for`, `return`, etc.);
- São sensíveis a maiúsculas e minúsculas (`minhaFuncao` é diferente de `minhafuncao`).

Considere a função para expressar surpresa vista anteriormente:

```javascript
function expressarSurpresa(nivelSurpresa) {
    let surpresa = "ah";
    for (let i = surpresa.length; i < nivelSurpresa; i++) {
        surpresa += "h";
        if (surpresa.length == nivelSurpresa) surpresa += "!";
    }
    return surpresa;
}

// Chamando a função com diferentes níveis de surpresa:
console.log(expressarSurpresa(2)); // "ah!"
console.log(expressarSurpresa(5)); // "ahhhh!"
console.log(expressarSurpresa(10)); // "ahhhhhhhhh!"
```

A mesma função poderia se chamar `expressar_surpresa`, no entanto, o estilo de nomenclatura mais comum em JavaScript é o `camelCase`, onde a primeira palavra é escrita em minúsculas e as demais palavras iniciam com maiúsculas, sem espaços ou sublinhados, por exemplo: `somarDoisNumeros`.

Particularidades da linguagem, em JavaScript os parâmetros são opcionais e podem ser omitidos na chamada da função. Se um parâmetro não for fornecido, seu valor será `undefined` dentro da função. Inclusive, é possível passar mais argumentos do que os parâmetros definidos. Esses argumentos extras podem ser acessados através do objeto especial `arguments` ou podem ser ignorados por completo. 

Aqui está um exemplo que demonstra esses conceitos:

```javascript
function mostrarParametros(a, b) {
    console.log("Parâmetro a:", a);
    console.log("Parâmetro b:", b);
    console.log("Número de argumentos recebidos:", arguments.length);
}

// Chamando a função com diferentes números de argumentos:
mostrarParametros(1);
// Parâmetro a: 1
// Parâmetro b: undefined
// Número de argumentos recebidos: 1
mostrarParametros(1, 2);
// Parâmetro a: 1
// Parâmetro b: 2
// Número de argumentos recebidos: 2
mostrarParametros(1, 2, 3, 4);
// Parâmetro a: 1
// Parâmetro b: 2
// Número de argumentos recebidos: 4
```

Dito isso, a função `expressarSurpresa` quebraria se chamada sem argumentos, pois `nivelSurpresa` seria `undefined`, e a comparação na condição do loop falharia. Para evitar isso, podemos definir um valor padrão para o parâmetro:


```javascript
function expressarSurpresa(nivelSurpresa = 5) { // valor padrão de 5
    let surpresa = "ah";
    for (let i = surpresa.length; i < nivelSurpresa; i++) {
        surpresa += "h";
        if (surpresa.length == nivelSurpresa) surpresa += "!";
    }
    return surpresa;
}
// Chamando a função sem argumentos usará o valor padrão:
console.log(expressarSurpresa()); // "ahhhh!" (nível padrão 5)
console.log(expressarSurpresa(10)); // "ahhhhhhhhh!" (nível 10)

// Se não houvesse o valor padrão, a chamada sem argumentos resultaria em erro:
console.log(expressarSurpresa()); // aoenas "ah", pois nivelSurpresa é undefined e i < undefined é falso
```

Como bons fazedores de programas, devemos sempre validar os parâmetros recebidos para garantir que a função se comporte corretamente, mesmo quando chamada com argumentos inesperados ou inválidos. Por exemplo:

```javascript
function dividir(a, b) {
    if (typeof a !== 'number' || typeof b !== 'number') {
        return NaN; // Retorna NaN se os parâmetros não forem números
    }
    if (b === 0) {
        return Infinity; // Retorna Infinity se houver tentativa de divisão por zero
    }
    return a / b;
}
// Chamando a função com parâmetros válidos:
console.log(dividir(10, 2)); // 5
```

O mesmo se aplica à função `expressarSurpresa`, onde podemos validar se o parâmetro é um número, se é positivo e se está dentro de um limite razoável (não queremos um `ahhh...` com milhões de `h`s!):

```javascript
function expressarSurpresa(nivelSurpresa = 5) {
    if (typeof nivelSurpresa !== 'number') {
        return NaN; // Retorna NaN se o parâmetro não for um número
    }
    if (nivelSurpresa <= 0) {
        return "Nenhuma surpresa, na verdade";
    }
    if (nivelSurpresa > 100) {
        return "Surpresa demais!"; // Limite máximo para evitar exageros      
    }

    let sentimento = "ah";
    for (let i = sentimento.length; i < nivelSurpresa; i++) {
        sentimento += "h";
        if (sentimento.length == nivelSurpresa) sentimento += "!";
    }
    return sentimento;
}
// Chamando a função com parâmetros válidos:
console.log(expressarSurpresa(10)); // "ahhhhhhhhh!"
// Chamando a função com parâmetros inválidos:
console.log(expressarSurpresa(-5)); // "Nenhuma surpresa, na verdade"
console.log(expressarSurpresa(150)); // "Surpresa demais!"
console.log(expressarSurpresa("muito")); // NaN
```

### Retorno de Funções

Funções podem retornar valores usando a palavra-chave `return`. Quando uma função encontra uma instrução `return`, ela imediatamente termina sua execução e retorna o valor especificado para o chamador. Se nenhuma instrução `return` for encontrada, a função retornará `undefined` por padrão.

Considere uma função que conta o número de vogais em uma string:

```javascript
function contarVogais(texto) {
    if (typeof texto !== 'string') return; // Retorna undefined se o parâmetro não for uma string

    let contador = 0;
    const vogais = "aeiouAEIOU";
    for (let i = 0; i < texto.length; i++) {
        const caractere = texto[i];
        if (vogais.includes(caractere)) contador++;
    }
    return contador; // Retorna o número de vogais encontradas
}
// Chamando a função e armazenando o resultado:
let numeroDeVogais = contarVogais("Olá, mundo!");
console.log(numeroDeVogais); // 4
// Chamando a função com um parâmetro inválido:
console.log(contarVogais(12345)); // undefined
```

A segunda opção para retornar nada é usar o `null`, que indica a ausência intencional de qualquer valor. Isso pode ser útil para sinalizar que uma função não tem um resultado válido para retornar:

```javascript
function buscarUsuarioPorId(id) {
    const usuarios = [
        { id: 1, nome: "Alice" },
        { id: 2, nome: "Bob" },
        { id: 3, nome: "Charlie" }
    ];
    for (let i = 0; i < usuarios.length; i++) {
        if (usuarios[i].id === id) {
            return usuarios[i]; // Retorna o usuário encontrado
        }
    }
    // se este return fosse omitido, a função retornaria undefined por padrão
    return null; // retorna null se o usuário não for encontrado
}
// Chamando a função com um ID existente:
let usuario = buscarUsuarioPorId(2);
console.log(usuario); // { id: 2, nome: "Bob" }
// Chamando a função com um ID inexistente:
usuario = buscarUsuarioPorId(5);
console.log(usuario); // null é mais útil neste caso pois indica que o usuário não foi encontrado e não que a função falhou
```

Valores `null` não retornam por padrão, a menos que sejam explicitamente retornados pela função. A escolha entre retornar `undefined` ou `null` depende do contexto e da intenção do programador. `undefined` geralmente indica que algo não foi definido ou não existe, enquanto `null` é usado para indicar a ausência intencional de um valor.


### Composição de Funções

Funções podem chamar outras funções dentro de seu corpo, permitindo a composição de funcionalidades e a criação de programas mais complexos. Isso promove a reutilização de código e a modularidade. Aqui está um exemplo simples de composição de funções:

```javascript
function dobrar(n) {
    return n * 2;
}

function somar(a, b) {
    return a + b;
}

function somarEDobrar(x, y) {
    let soma = somar(x, y); // chama a função somar
    return dobrar(soma); // chama a função dobrar
}

// Chamando a função composta:
console.log(somarEDobrar(3, 4)); // (3 + 4) * 2 = 14
```

Voltando ao exemplo da surpresa, podemos dividir a lógica em funções menores para melhorar a clareza e a reutilização:

```javascript
function expressarSurpresa(nivelSurpresa = 5) {
    let vogal = 'a';
    return expressar(vogal, nivelSurpresa);
}

function expressarDecepcao(nivelDecepcao = 5) {
    let vogal = 'o';
    return expressar(vogal, nivelDecepcao);
}

function expressar(vogal = 'a', nivel = 5) {
    // cláusulas guarda: se nenhuma entrar, então os parâmetros recebidos são válidos:
    if (typeof nivel !== 'number') return NaN;
    if (nivel <= 0) return "Nenhuma expressão, na verdade";
    if (nivel > 100) return "Expressão demais!";
    
    let sentimento = "ah";
    
    for (let i = sentimento.length; i < nivel; i++) sentimento += "h";
    
    return sentimento + "!";
}

// Chamando as funções compostas:
console.log(expressarSurpresa(10)); // "ahhhhhhhhh!"
console.log(expressarDecepcao(7)); // "ohhhhhhh!"
```

As funções podem chamar outras funções quantas vezes forem necessárias, criando uma cadeia de chamadas que pode ser tão profunda quanto o necessário para resolver o problema em questão. No entanto, é importante evitar chamadas recursivas infinitas, que podem levar a um estouro de pilha (_stack overflow_). A seguir está uma função profunda:

```javascript
function funcaoA(n) {
    console.log("Dentro da função A, n vale: " + n);
    funcaoB(n + 1);
    console.log("Retornando da função B...");
    console.log("n vale: " + n + " na função A");
    console.log("Retornando para o chamador...");
}
function funcaoB(n) {
    console.log("Dentro da função B, n vale: " + n);
    console.log("Chamando a função C...");
    funcaoC(n + 1);
    console.log("Retornando da função C...");
    console.log("n vale: " + n + " na função B");
    console.log("Retornando para a função A...");
}
function funcaoC(n) {
    console.log("Dentro da função C, n vale: " + n);
    // Pode continuar chamando outras funções...
}

// Iniciando a cadeia de chamadas:
funcaoA(7); // Inicia a execução a partir da função A
// Saída esperada:
// Dentro da função A, n vale: 7
// Dentro da função B, n vale: 8
// Chamando a função C...
// Dentro da função C, n vale: 9
// Retornando da função C...
// n vale: 8 na função B
// Retornando para a função A...
// n vale: 7 na função A
// Retornando para o chamador...
```

Cada função têm seu próprio escopo, o que significa que variáveis declaradas dentro de uma função não são acessíveis fora dela, a menos que sejam retornadas ou atribuídas a variáveis globais. Isso ajuda a evitar conflitos de nomes e mantém o código organizado. No exemplo acima, as variáveis `n` em cada função são independentes umas das outras.

As funções são empilhadas na pilha de chamadas (_call stack_), onde a função que está sendo executada no momento está no topo da pilha. Quando uma função chama outra, a nova função é adicionada ao topo da pilha, e quando uma função termina sua execução, ela é removida da pilha, retornando o controle para a função anterior. A seguir está uma representação visual simplificada da pilha de chamadas durante a execução do exemplo acima:

```
Call Stack (Pilha de Chamadas)
+-------------------+
| funcaoC(n=9)     |  <-- Topo da pilha (função atualmente em execução)
+-------------------+
| funcaoB(n=8)     |
+-------------------+
| funcaoA(n=7)     |
+-------------------+
```

Quando uma função causa um erro ou exceção, a pilha de chamadas pode ser exibida no console para ajudar na depuração, mostrando a sequência de chamadas que levaram ao erro, por exemplo:

```javascript
function funcaoA() {
    funcaoB();
}
function funcaoB() {
    funcaoC();
}
function funcaoC() {
    throw new Error("Algo deu errado!");
}

funcaoA(); // Inicia a cadeia de chamadas
// Saída esperada no console:
// Uncaught Error: Algo deu errado!
//     at funcaoC (<anonymous>:6:11) aqui o número 6 e 11 representam a linha e coluna do código onde o erro ocorreu
//     at funcaoB (<anonymous>:3:5)
//     at funcaoA (<anonymous>:2:5)
//     at <anonymous>:1:1
```

### Funções Anônimas e Arrow Functions

Funções anônimas são funções que não possuem um nome associado. Elas são frequentemente usadas como argumentos para outras funções, especialmente em _callbacks_ e funções de ordem superior. Aqui está um exemplo de uma função usada como callback em um método de array:

```javascript
const quadrado = function(n) {
    return n * n;
};
const numeros = [1, 2, 3, 4, 5];
const quadrados = numeros.map(quadrado);
console.log(quadrados); // [1, 4, 9, 16, 25]
```

Se a função dobro fosse apenas usada uma vez, poderíamos defini-la diretamente como uma *função anônima* dentro do `map`:

```javascript
const numeros = [1, 2, 3, 4, 5];
const quadrados = numeros.map(function(n) {
    return n * n;
});
console.log(quadrados); // [1, 4, 9, 16, 25]
```

As arrow functions (funções de seta) são uma sintaxe mais concisa para escrever funções anônimas introduzida no ECMAScript 6 (ES6). Elas utilizam a flecha `=>` para separar os parâmetros do corpo da função. Aqui está o mesmo exemplo usando uma arrow function:

```javascript
const numeros = [1, 2, 3, 4, 5];
const quadrados = numeros.map(n => n * n);
console.log(quadrados); // [1, 4, 9, 16, 25]
```

_Arrow functions_ também pode ser usadas para declarar funções:

```javascript
const pluralizar = palavra => {
    if (palavra.endsWith("s")) return palavra; // já está no plural
    if (palavra.endsWith("ão")) return palavra.slice(0, -2) + "ões"; // ex.: "coração" -> "corações"
    if (palavra.endsWith("m")) return palavra.slice(0, -1) + "ns"; // ex.: "homem" -> "homens"
    if (palavra.endsWith("l")) return palavra.slice(0, -1) + "is"; // ex.: "animal" -> "animais"
    if (palavra.endsWith("r") || palavra.endsWith("z")) return palavra + "es"; // ex.: "flor" -> "flores"

    return palavra + "s";
}

console.log(pluralizar("carro")); // "carros"
```

## Programação Modular

Esta seção aborda o conceito de modularidade em programação, independentemente da linguagem utilizada, fornecendo as bases teóricas necessárias para entender a importância dos módulos no desenvolvimento de software.

Um dos artigos mais populares na definição de módulo data de 1972 e foi escrito por David Parnas, intitulado "On the Criteria to be Used in Decomposing Systems into Modules" (Sobre os Critérios a Serem Usados na Decomposição de Sistemas em Módulos). Nele, Parnas argumenta que a modularidade deve ser baseada na ocultação de informações e na separação de responsabilidades, permitindo que cada módulo seja desenvolvido, testado e mantido de forma independente. O artigo pode ser encontrado aqui: https://dl.acm.org/doi/10.1145/361598.361623

Bertrand Meyer, em seu livro _Object-Oriented Software Construction_, também discute a importância da modularidade e encapsulamento na construção de softwares orientados a objetos. Segundo ele, a definição de módulo é uma unidade de software que combina dados e procedimentos relacionados, fornecendo uma interface clara para interação com outros módulos. Ele enfatiza que módulos bem definidos ajudam a reduzir a complexidade do sistema, facilitam a reutilização de código e melhoram a manutenção. O livro de Meyer está disponível abertamente no site do autor em: https://bertrandmeyer.com/wp-content/upLoads/OOSC2.pdf A modularidade é discutida no Capítulo 3 do livro.

Grady Booch, em _Object-Oriented Analysis and Design_, também aborda a modularidade como um princípio fundamental na engenharia de software. Booch destaca que a modularidade permite a decomposição de sistemas complexos em partes menores e mais gerenciáveis, facilitando o desenvolvimento colaborativo e a evolução do software ao longo do tempo. Ele enfatiza a importância de definir interfaces claras entre os módulos para garantir a interoperabilidade e a independência dos componentes. O livro é vendido pela Editora O'Reilly e pode ser encontrado em: https://www.oreilly.com/library/view/object-oriented-analysis-and/9780201895513/

Portanto, um módulo pode ser minúsculo como uma única função reutilizável, ou um grupo de funções relacionadas (coesas) escritas em um arquivo, ou até um conjunto de arquivos, com classes e funções, formando um pacote coeso, ou até uma biblioteca completa (conjunto de pacotes). A seguir uma representação visual simples de como um sistema modular pode ser estruturado:

```plain
+-------------------+      +-------------------+      +-------------------+
|     Módulo A      |      |     Módulo B      |      |     Módulo C      |
+-------------------+      +-------------------+      +-------------------+
|  Função 1         |      |  Função 4         |      |  Função 7         |
|  Função 2         |      |  Função 5         |      |  Função 8         |
|  Função 3         |      |  Função 6         |      |  Função 9         |
+-------------------+      +-------------------+      +-------------------+
        ^                           ^                           ^
        +---------------------------+---------------------------+
                    |                           |
            +-------------------+      +-------------------+
            |   Interface X     |      |   Interface Y     |
            +-------------------+      +-------------------+
                    |                           |
        +---------------------------+---------------------------+
        |                           |                           |
+-------------------+      +-------------------+      +-------------------+
| Sistema Principal |      |   Subsistema 1    |      |   Subsistema 2    |
+-------------------+      +-------------------+      +-------------------+
```

Resumindo, um módulo deve ter as seguintes características:

- **Encapsulamento**: Um módulo deve ocultar seus detalhes internos e expor apenas o necessário através de uma interface pública.
- **Coesão**: As funcionalidades dentro de um módulo devem estar relacionadas e focadas em uma única responsabilidade ou tarefa.
- **Baixo Acoplamento**: Um módulo deve ser o mais independente possível de outros módulos, minimizando a interdependência.
- **Reutilização**: Módulos bem projetados podem ser reutilizados em diferentes partes do sistema ou em outros projetos.
- **Manutenção Facilitada**: A modularidade facilita a manutenção e atualização do software, permitindo que mudanças em um módulo não afetem outros módulos nem outras partes do sistema.

Nas seções seguintes exploraremos como implementar a programação modular especificamente em JavaScript.


### Projetos JavaScript

Em JavaScript, um projeto geralmente consiste em um conjunto de arquivos e pastas organizados de maneira lógica para desenvolver uma aplicação ou biblioteca. A estrutura do projeto pode variar dependendo do tipo de aplicação (web, Node.js, etc.) e das ferramentas utilizadas. Os projetos JavaScript modernos frequentemente utilizam gerenciadores de pacotes como `npm` (Node Package Manager) ou Yarn para gerenciar dependências e scripts de construção. Neste guia usaremos o `npm` para inicializar um projeto que utiliza módulos ES6.

Para checar se o `npm` está instalado, execute o seguinte comando no terminal:

```bash
npm -v
```

Se o comando retornar uma versão, o `npm` está instalado corretamente. Caso contrário, você precisará instalar o Node.js, que inclui o `npm`. Você pode baixar o instalador do Node.js no site oficial: https://nodejs.org/ (ver [Ambiente de Execução](#ambiente-de-execução))

Para iniciar um novo projeto JavaScript com `npm`, siga os passos abaixo:

1. Crie uma nova pasta para o seu projeto e navegue até ela no terminal.
2. Inicialize o projeto com `npm init -y`, que cria um arquivo `package.json` com as configurações padrão.
3. Edite o arquivo `package.json` e adicione a linha `"type": "module"` para usar módulos ES6.
4. Crie um arquivo JavaScript principal, como `index.js`, onde você escreverá seu código.

Exemplo de comandos para iniciar um projeto:

```bash
mkdir meu-projeto-js
cd meu-projeto-js
npm init -y
# Crie o arquivo index.js
touch index.js
# Edite o package.json para incluir "type": "module" ou substituir "type": "commonjs" por "type": "module"
code . # abre o projeto no VS Code ou use outro editor de sua preferência
```

O arquivo `package.json` deve ficar parecido com isto:

```json
{
  "name": "meu-projeto-js",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "start": "node index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

Para executar o projeto, você pode usar o comando `npm start` que executará o script definido na seção `scripts` do `package.json`, com `node index.js` ou apenas `node .` (`.` é um símbolo que significa o diretório atual).

```bash
npm start
```

Projetos podem usar bibliotecas e frameworks externos para adicionar funcionalidades. Essas dependências podem ser instaladas usando o `npm install <nome-da-biblioteca>`. Por exemplo, para instalar a biblioteca `readline-sync`, você pode executar:

```bash
npm install readline-sync
```

Para usá-la em seu código, você pode importar os módulo usando a sintaxe de módulos ES6 com `import`. Aqui está um exemplo simples que usa `readline-sync` para ler o nome do usuário e exibir uma saudação:

```javascript
import read from 'readline-sync';

const nome = read.question('Qual é o seu nome?');

console.log(`Olá, ${nome}!`);
```

Tenha em consideração que você precisará roda o comando `npm install` sempre que clonar um projeto que contenha um arquivo `package.json`, para instalar todas as dependências listadas nele. As dependências são armazenadas na pasta `node_modules`, que não deve ser incluída no controle de versão (como Git), por isso é comum adicionar `node_modules` ao arquivo `.gitignore`.


### Programação Modular em JavaScript

JavaScript organiza os módulos na forma de arquivos separados, onde cada arquivo pode conter uma ou mais funções, classes ou variáveis. A interface do módulo é definida pelas funcionalidades que ele exporta, permitindo que outros módulos importem e utilizem essas funcionalidades. Isto é, podem existir funções e variáveis privadas dentro do módulo que não são acessíveis externamente, promovendo o encapsulamento, enquanto as funcionalidades exportadas formam a interface pública do módulo.

JavaScript suporta diferentes formas de módulos como CommonJS (usado no Node.js). Neste guia, focaremos na sintaxe de módulos ES6 que é padrão em ambientes modernos e utiliza as instruções `import` e `export` para importar e exportar funcionalidades entre módulos.

Considere o exemplo anterior da função `pluralizar`. Podemos organizá-la em um módulo separado para reutilização:

```javascript
// arquivo: pluralizar.js
export function pluralizar(palavra) {
    if (palavra.endsWith("s")) return palavra; // já está no plural
    if (palavra.endsWith("ão")) return palavra.slice(0, -2) + "ões"; // ex.: "coração" -> "corações"
    if (palavra.endsWith("m")) return palavra.slice(0, -1) + "ns"; // ex.: "homem" -> "homens"
    if (palavra.endsWith("l")) return palavra.slice(0, -1) + "is"; // ex.: "animal" -> "animais"
    if (palavra.endsWith("r") || palavra.endsWith("z")) return palavra + "es"; // ex.: "flor" -> "flores"
    return palavra + "s";
}

// arquivo: index.js
import { pluralizar } from './pluralizar.js';
console.log(pluralizar("carro")); // "carros"
console.log(pluralizar("coração")); // "corações"
```

Neste exemplo, a função `pluralizar` é exportada do módulo `pluralizar.js` usando a palavra-chave `export`. No arquivo `index.js`, a função é importada usando a instrução `import`, permitindo seu uso no código principal.

Agora, considere uma função `singularizar`. Ela poderia ser implementada em outro módulo (`singularizar.js`), ou junto com a função `pluralizar`, pois não afetaria a coesão do módulo, sendo que ambas lidam com a manipulação de formas plurais e singulares de palavras. A seguir o exemplo com ambas as funções no mesmo módulo: 

```javascript
// arquivo: flexoes.js
export function pluralizar(palavra) {
    if (palavra.endsWith("s")) return palavra; // já está no plural
    if (palavra.endsWith("ão")) return palavra.slice(0, -2) + "ões"; // ex.: "coração" -> "corações"
    if (palavra.endsWith("m")) return palavra.slice(0, -1) + "ns"; // ex.: "homem" -> "homens"
    if (palavra.endsWith("l")) return palavra.slice(0, -1) + "is"; // ex.: "animal" -> "animais"
    if (palavra.endsWith("r") || palavra.endsWith("z")) return palavra + "es"; // ex.: "flor" -> "flores"
    return palavra + "s";
}

export function singularizar(palavra) {
    if (!palavra.endsWith("s")) return palavra; // já está no singular
    if (palavra.endsWith("ões")) return palavra.slice(0, -3) + "ão"; // ex.: "corações" -> "coração"
    if (palavra.endsWith("ns")) return palavra.slice(0, -2) + "m"; // ex.: "homens" -> "homem"
    if (palavra.endsWith("is")) return palavra.slice(0, -2) + "l"; // ex.: "animais" -> "animal"
    if (palavra.endsWith("es")) {
        const semS = palavra.slice(0, -2);
        if (semS.endsWith("r") || semS.endsWith("z")) return semS;
        else return semS;
    }
    return palavra.slice(0, -1);
}

// arquivo: index.js
import { pluralizar, singularizar } from './flexoes.js';
console.log(pluralizar("carro")); // "carros"
console.log(singularizar("corações")); // "coração"
```

Para exemplificar a interface pública e o encapsulamento, considere o exemplo da função `expressarSurpresa` e `expressarDecepcao`. Podemos criar um módulo `expressoes.js` que exporta apenas essas duas funções, enquanto a função auxiliar `expressar` permanece privada dentro do módulo:

```javascript
// arquivo: expressoes.js
function expressar(vogal = 'a', nivel = 5) {
    if (typeof nivel !== 'number') return NaN;
    if (nivel <= 0) return "Nenhuma expressão, na verdade"
    if (nivel > 100) return "Expressão demais!";
    let sentimento = vogal + "h";
    for (let i = sentimento.length; i < nivel; i++) sentimento += "h";
    return sentimento + "!";
}

// podemos também exportar como arrow function, útil para funções simples:
export const expressarSurpresa = (nivelSurpresa = 5) => expressar('a', nivelSurpresa);
export const expressarDecepcao = (nivelDecepcao = 5) => expressar('o', nivelDecepcao);

// arquivo: index.js
import { expressarSurpresa, expressarDecepcao } from './expressoes.js';
console.log(expressarSurpresa(10)); // "ahhhhhhhhh!"
console.log(expressarDecepcao(7)); // "ohhhhhhh!"
```

As importações podem ser renomeadas durante a importação para evitar conflitos de nomes ou para melhorar a clareza do código:

```javascript
import { expressarSurpresa as surpresa, expressarDecepcao as decepcao } from './expressoes.js';

console.log(surpresa(8)); // "ahhhhhhh!"
console.log(decepcao(4)); // "ohhh!"
``` 

Quando um módulo exporta muitas funcionalidades, pode ser útil importar tudo de uma vez usando o caractere curinga `*` e atribuindo a um objeto:

```javascript
import * as expressoes from './expressoes.js';

console.log(expressoes.expressarSurpresa(10)); // "ahhhhhhhhh!"
console.log(expressoes.expressarDecepcao(10)); // "ohhhhhhhhh!"
```

Quando um módulo exporta uma única funcionalidade principal, é comum usar a exportação padrão (`default export`). Isso permite importar o módulo sem usar chaves `{}`. Aqui está um exemplo com a função `pluralizar` como exportação padrão:

```javascript
// arquivo: pluralizar.js
export default function pluralizar(palavra) {
    if (palavra.endsWith("s")) return palavra; // já está no plural
    if (palavra.endsWith("ão")) return palavra.slice(0, -2) + "ões"; // ex.: "coração" -> "corações"
    if (palavra.endsWith("m")) return palavra.slice(0, -1) + "ns"; // ex.: "homem" -> "homens"
    if (palavra.endsWith("l")) return palavra.slice(0, -1) + "is"; // ex.: "animal" -> "animais"
    if (palavra.endsWith("r") || palavra.endsWith("z")) return palavra + "es"; // ex.: "flor" -> "flores"
    return palavra + "s";
}
// arquivo: index.js
import pluralizar from './pluralizar.js'; // sem chaves {}
console.log(pluralizar("carro")); // "carros"
```

Exportação padrão e nomeada podem ser usadas juntas em um mesmo módulo, mas apenas uma exportação padrão é permitida por módulo:

```javascript
// arquivo: flexoes.js
export default function pluralizar(palavra) {
    // implementação...
}
export function singularizar(palavra) {
    // implementação...
}
// arquivo: index.js
import pluralizar, { singularizar } from './flexoes.js';
console.log(pluralizar("carro")); // "carros"
console.log(singularizar("corações")); // "coração"
``` 

Os módulos podem reter estado entre importações, pois são carregados apenas uma vez e suas variáveis internas mantêm seus valores. Isso pode ser útil para criar singletons ou gerenciar configurações globais. Aqui está um exemplo simples de um módulo que mantém um contador:

```javascript
// arquivo: contador.js

// contadores é privado ao módulo
const contadores = new Map();
contadores.set('default', 0);

export function incrementar(prefixo = 'default') {
    let contador = contadores.get(prefixo) || 0;
    contadores.set(prefixo, ++contador);
    return { prefixo, contador };
}

export function obterContador(prefixo = 'default') {
    return { prefixo, contador: contadores.get(prefixo) };
}

// arquivo: index.js
import { incrementar, obterContador } from './contador.js';
console.log(obterContador()); // { prefixo: "default", contador: 0 }
console.log(incrementar()); // { prefixo: "default", contador: 1 }
console.log(incrementar()); // { prefixo: "default", contador: 2 }
console.log(obterContador()); // { prefixo: "default", contador: 2 }
console.log(incrementar('user')); // { prefixo: "user", contador: 1 }
console.log(obterContador('user')); // { prefixo: "user", contador: 1 }
```


### Biblioteca Padrão do JavaScript

A Biblioteca Padrão do JavaScript, também conhecida como API padrão, é um conjunto de objetos, funções e métodos integrados que fornecem funcionalidades básicas para manipulação de dados, operações matemáticas, manipulação de strings, datas, arrays, entre outros. Esses recursos estão disponíveis em qualquer ambiente JavaScript, seja no navegador ou no Node.js.

Alguns dos principais componentes da Biblioteca Padrão do JavaScript incluem:

- `Math`: fornece propriedades e métodos para operações matemáticas, como arredondamento, geração de números aleatórios, cálculos trigonométricos, etc.
- `Date`: permite criar, manipular e formatar datas e horas.
- `String`: oferece métodos para manipulação de strings, como busca, substituição, divisão, concatenação, etc.
- `Array`: fornece métodos para manipulação de arrays, como adição, remoção, ordenação, filtragem, mapeamento, etc.
- `Object`: oferece métodos para manipulação de objetos, como criação, cópia, verificação de propriedades, etc.
- `JSON`: fornece métodos para conversão entre objetos JavaScript e strings JSON.

Operações comuns de strings incluem:

```javascript
var texto = "Olá, mundo!";
console.log(texto.length); // 13 (número de caracteres)
console.log(texto.toUpperCase()); // "OLÁ, MUNDO!" (tudo
console.log(texto.toLowerCase()); // "olá, mundo!" (tudo minúsculo)
console.log(texto.indexOf("mundo")); // 5 (posição inicial da substring)
console.log(texto.replace("mundo", "JavaScript")); // "Olá, JavaScript!" (substituição)
console.log(texto.split(", ")); // ["Olá", "mundo!"] (divisão em array)
console.log(texto.substring(0, 5)); // "Olá, " (substring do índice 0 ao 5)
console.log(texto.trim()); // "Olá, mundo!" (remove espaços em branco nas extremidades)
console.log(texto.endsWith("!")); // true (verifica se termina com "!")
```

Arrays são listas ordenadas de valores e possuem diversos métodos úteis:

```javascript
var frutas = ["maçã", "banana", "laranja"];
frutas.push("uva"); // adiciona "uva" ao final
console.log(frutas); // ["maçã", "banana", "laranja", "uva"]
frutas.pop(); // remove o último elemento
console.log(frutas); // ["maçã", "banana", "laranja"]
frutas.shift(); // remove o primeiro elemento
console.log(frutas); // ["banana", "laranja"]
frutas.unshift("morango"); // adiciona "morango" no início
console.log(frutas); // ["morango", "banana", "laranja"]
console.log(frutas.indexOf("banana")); // 1 (posição de "banana")
console.log(frutas.slice(0, 2)); // ["morango", "banana"] (subarray do índice 0 ao 2, exclusivo)
```


## Estruturas de Dados em JavaScript

Não é possível escrever programas mais complexos sem o uso de estruturas de dados adequadas. Estruturas de dados são formas específicas de organizar e armazenar dados na memória do computador, permitindo acesso e manipulação eficientes. Cada estrutura de dados é projetada para atender a diferentes necessidades e requisitos de desempenho, dependendo do tipo de dados e das operações que serão realizadas sobre eles. Enquanto algumas estruturas de dados são fornecidas diretamente pela linguagem de programação, outras podem ser implementadas pelo programador conforme necessário. As estruturas de dados podem ser heterogêneas ou homogêneas, dependendo do tipo de dados que armazenam. Estruturas de dados heterogêneas podem conter elementos de diferentes tipos, enquanto estruturas de dados homogêneas armazenam apenas elementos do mesmo tipo. JavaScript por ser uma linguagem de tipagem dinâmica, todas as suas estruturas de dados são heterogêneas por padrão, ou seja, é possível armazenar diferentes tipos de dados em arrays e objetos.

### Estruturas de Dados Elementares

A maioria das linguagens de programação modernas, incluindo JavaScript, oferecem uma variedade de estruturas de dados embutidas que facilitam o desenvolvimento de software, como objetos, registros, arrays, listas, conjuntos e mapas, sendo essas as estruturas de dados mais comuns e elementares. Este capítulo aborda essas estruturas de dados elementares em JavaScript.

#### Notação Literal de Objetos em JavaScript

O modo mais simples de representar um objeto em JavaScript é usando a notação literal de objetos, que utiliza chaves `{}` para definir um objeto e pares chave-valor para representar suas propriedades, agrupando um conjunto de características relacionadas em uma única entidade. Neste sentido, é possível armazenar múltiplas informações usando uma única variávels e passá-las às funções como um único argumento.

Por exemplo, considere uma função para calcular o índice de massa corporal (IMC) de uma pessoa. Em vez de passar vários parâmetros separados para a função, podemos agrupar as informações relevantes (a antropometria) em um objeto e passá-lo como um único argumento. A seguir um exemplo da função `imc` com parâmetros separados e com um objeto:

```javascript
function classificacao(imc) {
    if (imc < 18.5) return "Abaixo do peso";
    else if (imc < 25.0) return "Peso normal (ideal)";
    else if (imc < 30.0) return "Sobrepeso";
    else if (imc < 35.0) return "Obesidade Grau I";
    else if (imc < 40.0) return "Obesidade Grau II";
    else return "Obesidade Grau III (Mórbida)";    
}

function imc_v1(peso, altura) {
    const alturaEmMetros = altura / 100; // converter cm para metros
    const imcCalculado = (peso / (alturaEmMetros * alturaEmMetros)).toFixed(2);
    let classe = classificacao(imcCalculado);
    return imcCalculado;
}

// usando o IMC e verificando a classificação com variáveis e retornos separados
const peso = 85; // em kg
const altura = 175; // em cm
const imc1 = imc_v1(peso, altura);
const classif1 = classificacao(imc1);
console.log(`IMC: ${imc1} - Classificação: ${classif1}`);

// agora usando um objeto para agrupar os dados antropométricos e retornando ambos IMC e classificação juntos como um objeto

function imc_v2(antropometria) { // o parâmetro é um objeto contendo peso e altura
    const alturaEmMetros = antropometria.altura / 100; // converter cm para metros
    const imcCalculado = (antropometria.peso / (alturaEmMetros * alturaEmMetros)).toFixed(2);
    const classe = classificacao(imcCalculado);

    // retornando ambos IMC e classificação como um objeto usando a notação literal de objetos
    return { imc: imcCalculado, classificacao: classe };
}

const antropometria = { peso: 85, altura: 175 };
const resultado = imc_v2(antropometria); // apenas um parâmetro é passado
console.log(`IMC: ${resultado.imc} - Classificação: ${resultado.classificacao}`);
```

Os objetos podem ser aninhados, ou seja, um objeto pode conter outros objetos como propriedades. Isso é útil para representar estruturas de dados mais complexas. Por exemplo, podemos representar uma pessoa com suas informações pessoais e endereço:

```javascript
const pessoa = {
    nome: "João Silva",
    idade: 30,
    endereco: {
        rua: "Rua das Flores",
        numero: 123,
        cidade: "Rio Grande",
        estado: "RS"
    },
    // os objetos literais também podem conter métodos (funções associadas ao objeto)
    saudacao: function() {
        return `Olá, meu nome é ${this.nome} e eu moro em ${this.endereco.cidade}/${this.endereco.estado}.`;
    }
};

console.log(pessoa.saudacao()); // "Olá, meu nome é João Silva e eu moro em Rio Grande/RS."
```


#### Classes e Objetos em JavaScript

JavaScript é uma linguagem orientada a objetos baseada em protótipos, o que significa que os objetos podem herdar propriedades e métodos diretamente de outros objetos. No entanto, a partir do ECMAScript 6 (ES6), JavaScript introduziu a sintaxe de classes, que fornece uma maneira mais familiar e estruturada de criar objetos e lidar com herança.

Tenha em consideração que Programação Orientada a Objetos (POO) é um tópico extenso por si só e mereceria um guia apenas para tratar do paradigma. Nesta seção é abordado apenas o mínimo em JavaScript para implementar classes que tenham estado (atributos e propriedades) e comportamento (métodos).

Como exemplo, pense na representação de horário, de `00:00:00` à `23:59:59`. Embora tudo possa ser representado como _string_ (ex.: `"13:23:41"`), na maioria das vezes um tipo customizados são mais adequados. Tipos customizados podem ser implementados de diversas formas, as linguagens de programação disponibilizam construtos para tal, como records, structs e, claro, CLASSES. A seguir, a implementação de horário:

```javascript
// Horario.js
export default class Horario {
    // atributo privado (ENCAPSULADO) para manter a contagem de segundos de um dia: de 0 à 86399
    #segundos = 0; // o símbolo # torna o atributo privado

    constructor(horas = 0, minutos = 0, segundos = 0) {
        if (typeof (horas) !== 'number' || typeof (minutos) !== 'number' || typeof (segundos) !== 'number') {
            throw new Error('Horas, minutos e segundos devem ser números inteiros');
        }
        // converter horas e minutos em segundos para armazenamento
        const segundosTotais = ((horas | 0) * 3600 + (minutos | 0) * 60 + (segundos | 0)) % 86400;
        if (segundosTotais < 0) {
            throw new Error('O resultante não pode ser negativo');
        }
        this.#segundos = segundosTotais;
        // segundos é o parâmetro enquanto this.#segundos é o atributo
    }

    // interface pública permitindo consultar as horas, minutos e segundos
    // essas são propriedades computadas
    get horas() {
        return (this.#segundos / 3600) | 0;
    }

    get minutos() {
        return (this.#segundos % 3600 / 60) | 0;
    }

    get segundos() {
        return (this.#segundos % 60);
    }

    // métodos
    adicionaSegundos(segundos) {
        if (typeof (segundos) !== 'number') throw new Error('Segundos deve ser um inteiro');
        const segundosTotais = (this.#segundos + segundos) % 86400;
        if (segundosTotais < 0) {
            throw new Error('O resultante não pode ser negativo');
        }
        this.#segundos = segundosTotais;
    }

    adicionaMinutos(minutos) {
        if (typeof (minutos) !== 'number') throw new Error('Minutos deve ser um inteiro');
        const segundosTotais = (this.#segundos + minutos * 60) % 86400;
        if (segundosTotais < 0) {
            throw new Error('O resultante não pode ser negativo');
        }
        this.#segundos = segundosTotais;
    }

    adicionaHoras(horas) {
        if (typeof (horas) !== 'number') throw new Error('Horas deve ser um inteiro');
        const segundosTotais = (this.#segundos + horas * 3600) % 86400;
        if (segundosTotais < 0) {
            throw new Error('O resultante não pode ser negativo');
        }
        this.#segundos = segundosTotais;
    }

    // devolve uma representação string deste horário na forma de "00:00:00"
    toString() {
        return `${this.#pad(this.horas)}:${this.#pad(this.minutos)}:${this.#pad(this.segundos)}`;
    }

    // este método é privado, acessível apenas internamente
    #pad(valor) {
        return valor < 10 ? `0${valor}` : `${valor}`;
    }
}

// index.js
import Horario from './Horario.js';

const h = new Horario(13, 55, 34);
console.log(h.horas, h.minutos, h.segundos); // 13, 55, 34
h.adicionaSegundos(3);
console.log(h.horas, h.minutos, h.segundos); // 13, 55, 37
h.adicionaMinutos(30);
console.log(h.horas, h.minutos, h.segundos); // 14, 25, 37
h.adicionaHoras(13);
console.log(h.horas, h.minutos, h.segundos); // 3, 25, 37

console.log(h.toString()); // '03:25:37'
```

O exemplo anterior apresenta diversos conceitos da POO. A classe `Horario` introduz um novo tipo customizado. O estado é armazenado em segundos totais no atributo `#segundos` -- o símbolo `#` protege o atributo (um tipo de variável) de acesso externo. O construtor recebe os parâmetros para inicializar um objeto horário, na forma de `new Horario(13, 45, 12)`. O construtor é sempre invocado na instanciação de objetos, isto é, o uso do `new`. Para ler a quantidade de horas, minutos e segundos são disponibilizadas as propriedades `horas`, `minutos` e `segundos` na forma de `get horas()`, etc. As propriedades parecem funções, por causa dos parênteses, assim como os métodos `adicionaHoras()` e outros, mas não são declarados com a palavra-chave `function`. Por fim, o método `#pad(valor)` também é como uma função, porém privada, isto é, só pode ser invocada dentro da classe `Horario` -- é parte do encapsulamento, não faz sentido expor o método `pad`. 

A mesma representação de horário poderia ser implementada usando a notação literal de objetos, mas a implementação com classes oferece uma estrutura mais clara e organizada, especialmente quando se trata de criar múltiplas instâncias do mesmo tipo de objeto, cada uma com seu próprio estado e comportamento. Usar a notação literal seria útil, no entanto, para representar um horário de uso único, sem a necessidade de criar múltiplas instâncias ou reutilizar o código, como a seguir:

```javascript
const horario = {
    segundos: 12345, // representa 03:25:45
    get horas() {
        return (this.segundos / 3600) | 0;
    },
    get minutos() {
        return (this.segundos % 3600 / 60) | 0;
    },
    get segundosRestantes() {
        return (this.segundos % 60);
    },
    adicionaSegundos(segundos) {
        this.segundos = (this.segundos + segundos) % 86400;
    }
}

console.log(horario.horas, horario.minutos, horario.segundosRestantes); // 3, 25, 45
horario.adicionaSegundos(500);
console.log(horario.horas, horario.minutos, horario.segundosRestantes); // 3, 33, 5
```

#### Arrays (listas)

Arrays em JavaScript são diferentes de arrays em linguagens de tipagem estática, como C, C++ e Java. Em JavaScript, arrays são objetos dinâmicos que podem crescer e encolher conforme necessário, e podem conter elementos de diferentes tipos, funcionando, na verdade, como LISTAS ordenadas.

Um array pode ser declarado literalmente usando colchetes `[]`, determinando os elementos, ou usando o construtor `Array()`, para criar uma lista vazia. Seguem alguns exemplos:

```javascript
// declaração literal de array
const nomes = ["Ana", "Bruno", "Carlos", "Daniela"];
// arrays são ordenados, o primeiro elemento está no índice 0 e o último sempre no índice length - 1
console.log(nomes[0]); // "Ana", o primeiro nome
console.log(nomes[2]); // "Carlos", o terceiro nome
console.log(nomes.length); // 4 (número de elementos no array)
console.log(nomes[nomes.length - 1]); // "Daniela" (último elemento)

// o array pode ser criado vazio e os elementos adicionados depois
const idades = []; // ou new Array();
idades.push(25);
idades.push(30);
idades.push(22);
console.log(idades); // [25, 30, 22]

const matriculas = new Array();
matriculas.push("2026001");
matriculas.push("2026002");
matriculas.push("2026003");
console.log(matriculas); // ["2026001", "2026002", "2026003"]

// o método push (empurrar) adiciona elementos ao final do array
// este método funciona mesmo em arrays declarados com const, pois o array em si não é reatribuído, apenas modificado
nomes.push("Eduardo");
console.log(nomes); // ["Ana", "Bruno", "Carlos", "Daniela", "Eduardo"]

// o construtor Array também pode receber um número para definir o tamanho inicial do array
const estados = new Array(5); // cria um array com 5 posições vazias
console.log(estados.length); // 5
console.log(estados); // [ <5 empty items> ]
// podemos atribuir valores às posições do array diretamente
estados[0] = "RS";
estados[1] = "SC";
estados[2] = "MG";
console.log(estados); // ["RS", "SC", "MG", <2 empty items>]

// note quem em JavaScript podemos inclusive atribuir valores em índices fora do tamanho atual do array
estados[9] = "SP"; // atribuindo no índice 9
console.log(estados.length); // 10 (o array cresce automaticamente)
console.log(estados); // ["RS", "SC", "MG", <6 empty items>, "SP"]
```

Como arrays são objetos em JavaScript, eles possuem diversos métodos úteis para manipulação de listas. Alguns dos métodos mais comuns incluem:

- `push(elemento)`: Adiciona um elemento ao final do array.
- `pop()`: Remove e retorna o último elemento do array.
- `shift()`: Remove e retorna o primeiro elemento do array.
- `unshift(elemento)`: Adiciona um elemento no início do array.
- `indexOf(elemento)`: Retorna o índice da primeira ocorrência do elemento no array, ou -1 se não encontrado.
- `slice(início, fim)`: Retorna uma cópia de uma parte do array, do índice `início` ao `fim` (exclusivo).
- `splice(início, quantidade, ...elementos)`: Remove elementos do array e, opcionalmente, adiciona novos elementos.
- `forEach(callback)`: Executa uma função para cada elemento do array.
- `map(callback)`: Cria um novo array com os resultados da função aplicada a cada elemento.
- `filter(callback)`: Cria um novo array com todos os elementos que passam no teste implementado pela função fornecida.
- `join(separador)`: Junta todos os elementos do array em uma string, separados pelo `separador` especificado.
- `reverse()`: Inverte a ordem dos elementos do array in place.
- `includes(elemento)`: Retorna true se o elemento estiver presente no array, caso contrário false.

A referência completa dos métodos de arrays pode ser encontrada na documentação oficial do MDN: <https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array#m%C3%A9todos>

A seguir, alguns exemplos de uso dos métodos de arrays:

```javascript
const paises = ["Brasil", "Argentina", "Chile", "Peru", "Colômbia", "Venezuela", "Equador"];
// adicionando Uruguai ao final
paises.push("Uruguai");
// adicionando Paraguai no início
paises.unshift("Paraguai");
console.log(paises); // ["Paraguai", "Brasil", "Argentina", "Chile", "Peru", "Colômbia", "Venezuela", "Equador", "Uruguai"]

// removendo o último país
const ultimoPais = paises.pop();
console.log(ultimoPais); // "Uruguai"
// removendo o primeiro país
const primeiroPais = paises.shift();
console.log(primeiroPais); // "Paraguai"
console.log(paises); // ["Brasil", "Argentina", "Chile", "Peru", "Colômbia", "Venezuela", "Equador"]

// encontrando o índice da Colômbia
const indiceColombia = paises.indexOf("Colômbia");
console.log(indiceColombia); // 4

// criando um subarray com os três primeiros países
const primeirosTres = paises.slice(0, 3);
console.log(primeirosTres); // ["Brasil", "Argentina", "Chile"]

// removendo Chile e Peru, e adicionando Bolívia no lugar
paises.splice(2, 2, "Bolívia");
console.log(paises); // ["Brasil", "Argentina", "Bolívia", "Colômbia", "Venezuela", "Equador"]

// iterando sobre os países e exibindo-os
paises.forEach((pais, indice) => {
    console.log(`${indice + 1}. ${pais}`);
});
// 1. Brasil
// 2. Argentina
// 3. ...

// criando um novo array apenas com as duas primeiras letras de cada país em maiúsculas
const siglas = paises.map(p => p.slice(0, 2).toUpperCase()); // onde "p" é cada país do array
console.log(siglas); // ["BR", "AR", "BO", "CO", "VE", "EQ"]

// filtrando países que começam com a letra 'B'
const paisesComB = paises.filter(p => p.startsWith('B'));
console.log(paisesComB); // ["Brasil", "Bolívia"]

// juntando os países em uma única string separada por vírgulas
const listaPaises = paises.join(', ');
console.log(listaPaises); // "Brasil, Argentina, Bolívia, Colômbia, Venezuela, Equador"

// invertendo a ordem dos países
paises.reverse();
console.log(paises); // ["Equador", "Venezuela", "Colômbia", "Bolívia", "Argentina", "Brasil"]

// verificando se o Brasil está na lista
const temBrasil = paises.includes("Brasil");
console.log(temBrasil); // true
const temUruguai = paises.includes("Uruguai");
console.log(temUruguai); // false
```

Tenha sempre em consideração que arrays em JavaScript são dinâmicos e heterogêneos (diferente das outras linguagens tipadas), permitindo armazenar diferentes tipos de dados juntos:

```javascript
const misturado = [42, "texto", true, { chave: "valor" }, [1, 2, 3], null, undefined];
console.log(misturado);
// [42, "texto", true, { chave: "valor" }, [1, 2, 3], null, undefined]
```

Também não há restrições quanto ao tamanho e duplicidade de elementos:

```js
const numeros = [1, 2, 2, 3, 4, 4, 4, 5];
console.log(numeros); // [1, 2, 2, 3, 4, 4, 4, 5]
console.log(numeros.length); // 8
```


#### Conjuntos

Conjuntos (sets) são coleções não-ordenadas de valores únicos, ou seja, não permitem elementos duplicados. Em JavaScript, os conjuntos são implementados pela classe `Set`, que faz parte da Biblioteca Padrão do JavaScript desde o ECMAScript 2015 (ES6). Conjuntos são úteis quando você precisa armazenar uma coleção de itens sem se preocupar com a ordem ou duplicidade.

Por exemplo, considere o exemplo dos estados novamente, mas agora usando um conjunto para garantir que não haja estados duplicados:

```javascript
const estados = new Set();
estados.add("RS");
estados.add("SC");
estados.add("MG");
estados.add("RS"); // tentativa de adicionar duplicata, será ignorada
console.log(estados.size); // 3 (número de elementos únicos no conjunto)
console.log(estados.has("SC")); // true (verifica se "SC" está no conjunto)
console.log(estados.has("SP")); // false (verifica se "SP" está no conjunto)

// conjuntos não são ordenados, portanto não podemos acessar elementos por índice
// mas podemos iterar sobre os elementos usando for...of
for (const estado of estados) {
    console.log(estado);
}

// ou usando o método forEach
estados.forEach(estado => console.log(estado));
// ou simplesmente:
estados.forEach(console.log);

// removendo um elemento do conjunto
estados.delete("MG");
console.log(estados.size); // 2
```

É possível instanciar conjuntos a partir de Arrays e vice-versa:

```javascript
const arrayComDuplicatas = ["RS", "SC", "MG", "RS", "SC"];
const conjunto = new Set(arrayComDuplicatas); // cria um conjunto a partir do array
console.log(conjunto.size); // 3 (elementos únicos)
const novoArray = Array.from(conjunto); // cria um array a partir do conjunto
console.log(novoArray); // ["RS", "SC", "MG"]
```

Conjuntos têm melhor performance para operações de verificação de existência (`has`), adição (`add`) e remoção (`delete`) em comparação com arrays, especialmente quando a coleção é grande, pois não é necessário percorrer toda a lista para encontrar um elemento. O modo como os conjuntos são implementados possui endereçamento direto, similar a tabelas hash (que não será abordado neste material, mas podes encontrar mais a respeito em recursos sobre estruturas de dados).

Os métodos mais comuns de conjuntos incluem:
- `add(valor)`: Adiciona um valor ao conjunto.
- `delete(valor)`: Remove um valor do conjunto.
- `has(valor)`: Verifica se o conjunto contém um valor específico.
- `clear()`: Remove todos os valores do conjunto.


#### Mapas

Os Mapas (map) são coleções de pares chave-valor, onde cada chave é única e está associada a um valor. Em JavaScript, os mapas são implementados pela classe `Map`, que também faz parte da Biblioteca Padrão do JavaScript desde o ECMAScript 2015 (ES6). Mapas são úteis quando você precisa armazenar dados associados a chaves específicas, permitindo acesso rápido aos valores com base nas chaves. É semelhante aos objetos, mas com algumas diferenças importantes, como a capacidade de usar qualquer tipo de valor (não apenas strings ou símbolos) como chave. Também é semelhante aos arrays, mas com chaves personalizadas em vez de índices numéricos.

Aqui está um exemplo de uso de mapas em JavaScript:

```javascript
const mapa = new Map();
// adicionando pares chave-valor ao mapa
mapa.set("nome", "João Silva");
mapa.set("idade", 30);
mapa.set("cidade", "Rio Grande");
console.log(mapa.size); // 3 (número de pares chave-valor no mapa)
console.log(mapa.get("nome")); // "João Silva" (acessando o valor pela chave)
console.log(mapa.has("idade")); // true (verifica se a chave "idade" está no mapa)
console.log(mapa.has("pais")); // false (verifica se a chave "pais" está no mapa)
mapa.forEach((valor, chave) => {
    console.log(`${chave}: ${valor}`);
});
// nome: João Silva
// idade: 30
// cidade: Rio Grande

// neste exemplo foi armazenada uma instância de informação (uma pessoa), e poderia ter sido usado um objeto como:
const pessoa = {
    nome: "João Silva",
    idade: 30,
    cidade: "Rio Grande"
};

// no entanto pode-se usar um mapa para armazenar múltiplas pessoas, usando o nome como chave:
const pessoas = new Map();
pessoas.set("João Silva", { peso: 85, altura: 175 });
pessoas.set("Ana Maria", { peso: 60, altura: 165 });
console.log(pessoas.get("Ana Maria")); // { peso: 60, altura: 165 }

// quando não existe a chave, o método get retorna undefined
console.log(pessoas.get("Carlos")); // undefined

// removendo um par chave-valor do mapa
pessoas.delete("João Silva");
console.log(pessoas.size); // 1

// iterando sobre as chaves e valores do mapa
for (const [nome, antropometria] of pessoas) {
    console.log(`${nome}: ${antropometria.peso} kg, ${antropometria.altura} cm`);
}
```

Os métodos mais comuns de mapas incluem:
- `set(chave, valor)`: Adiciona ou atualiza um par chave-valor no mapa.
- `get(chave)`: Retorna o valor associado à chave especificada.
- `has(chave)`: Verifica se o mapa contém a chave especificada.
- `delete(chave)`: Remove o par chave-valor associado à chave especificada.
- `clear()`: Remove todos os pares chave-valor do mapa.

A decisão de quando usar um mapa em vez de um objeto depende do caso de uso específico. Mapas são mais adequados quando você precisa de chaves que não sejam strings ou símbolos, quando a ordem dos elementos é importante, ou quando você precisa de melhor performance para operações frequentes de adição e remoção de pares chave-valor.


### Estruturas de Dados Compostas

Estruturas de dados compostas são aquelas que combinam várias estruturas de dados elementares para formar uma estrutura mais complexa. Em JavaScript, é possível criar estruturas de dados compostas usando objetos, arrays, conjuntos e mapas. Essas estruturas permitem organizar e manipular dados de maneira mais eficiente e intuitiva, facilitando a resolução de problemas mais complexos. Aqui estão alguns exemplos de estruturas de dados compostas em JavaScript:

```javascript
// Exemplo 1: Array de Objetos
const pessoas = [
    { nome: "João Silva", idade: 30, cidade: "Rio Grande" },
    { nome: "Ana Maria", idade: 25, cidade: "Porto Alegre" },
    { nome: "Carlos Souza", idade: 35, cidade: "Santa Maria" }
];
console.log(pessoas[0].nome); // "João Silva"
// Exemplo 2: Objeto com Arrays
const turma = {
    nome: "Turma A",
    alunos: Map.from([
        ["2026001", { nome: "João Silva", idade: 30 }],
        ["2026002", { nome: "Ana Maria", idade: 25 }],
        ["2026003", { nome: "Carlos Souza", idade: 35 }]
    ])
};
```

É possível combinar conjuntos, arrays, mapas e objetos literais para criar estruturas mais complexas. Outras estruturas de dados, como filas, pilhas, árvores e grafos, podem ser implementadas usando essas estruturas básicas como blocos de construção.

### Estruturas de Dados Inexistentes em JavaScript

JavaScript não possui record ou structs, como em outras linguagens de programação. Também não possui filas (queues) e pilhas (stacks) como estruturas de dados nativas. Por ser fracamente tipada, não há tuplas (tuples) nem outras estruturas homogêneas. Para esses casos de uso, existem linguagens de programacão mais adequadas, ou então é possível implementar essas estruturas manualmente em JavaScript, usando as estruturas de dados elementares disponíveis.

## Considerações Finais

Este guia abordou os conceitos fundamentais de programação com JavaScript. Estes conceitos são basicamente os mesmos em outras linguagens de programação, com variações na sintaxe, formas de organizar o código e nas bibliotecas padrão. É recomendado que qualquer programador domine pelo menos uma linguagem dinâmica (como JavaScript, Python ou Ruby) e uma linguagem estática (como Rust, TypeScript, C# ou Java), para compreender as diferenças entre os paradigmas e estilos de programação. Liguagens tipadas adicionam uma camada extra de complexidade, mas também oferecem benefícios em termos de segurança e desempenho. A escolha da linguagem deve ser baseada nos requisitos do projeto, na experiência da equipe e nas características específicas de cada linguagem.