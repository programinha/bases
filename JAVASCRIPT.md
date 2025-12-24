# As Bases com JavaScript

As linguagens de programação servem para nós expressarmos o que queremos que o computador faça. Como os idiomas humanos, elas são diferentes na escrita (sintaxe) e até na forma de organizar o pensamento (paradigma de programação). Até usando a mesma linguagem podemos encontrar diversas maneiras de resolver um mesmo problema. No entanto, todas essas linguagens compartilham construtos comuns para guardar o estado do programa, decidir o que fazer dada uma condição, realizar um conjunto de tarefas um determinado número de vezes, obter e devolver informações, modularizar uma solução reutilizável, etc. Esse guia apresenta esses construtos usando a linguagem de programação JavaScript.

## História do JavaScript

Em 1995 a web era estática. A Netscape Communications, criadora do navegador dominante Netscape Navigator, queria adicionar interatividade. Eles seguiram dois caminhos: incorporar a complexa linguagem Java para tarefas pesadas e uma linguagem de script leve para tarefas simples do lado do cliente. Brendan Eich foi contratado em abril de 1995 e recebeu a tarefa de criar essa linguagem de script. Sob imensa pressão de prazo, ele desenvolveu um protótipo funcional em apenas dez dias. A linguagem foi inicialmente chamada de "Mocha", depois brevemente "LiveScript". O detalhe crucial "não contado" é a mudança de nome para JavaScript em dezembro de 1995. Isso foi uma jogada puramente de marketing para capitalizar o hype em torno da popular linguagem de programação Java da Sun Microsystems. Apesar do nome, as linguagens são totalmente diferentes, fato que causou (e ainda causa) confusão entre os desenvolvedores.

Com a guerra dos navegadores e a padronização (final dos anos 90 - início dos anos 2000), a Microsoft criou sua própria implementação, o JScript, para o Internet Explorer 3. A ausência de um padrão único levou à "guerra dos navegadores", onde os desenvolvedores lutavam para escrever código que funcionasse em diferentes navegadores. Para resolver isso, a Netscape submeteu o JavaScript à European Computer Manufacturers Association (ECMA) para padronização, resultando na especificação ECMAScript (ECMA-262), publicada pela primeira vez em junho de 1997. Enquanto o JavaScript é a implementação usada nos navegadores, o ECMAScript é a especificação oficial e neutra em relação aos fornecedores.

Por um tempo, o JavaScript foi descartado por muitos desenvolvedores sérios como uma "linguagem de brinquedo" usada principalmente para validação básica de formulários e pop-ups. O ponto de virada ocorreu por volta de 2005 com a popularização do AJAX (Asynchronous JavaScript and XML), uma técnica que permitia que páginas da web atualizassem conteúdo dinamicamente sem recarregar a página inteira, como acontece no Gmail, Google Maps, Instagram, entre outros.

A próxima revolução ocorreu em 2009, quando Ryan Dahl introduziu o Node.js, um ambiente de execução que permitia que o JavaScript fosse executado no lado do servidor, fora do navegador. Isso significava que o JavaScript poderia ser usado tanto para desenvolvimento front-end quanto back-end, criando o "JavaScript full-stack" e solidificando seu papel como uma linguagem de propósito geral.

Hoje, o JavaScript é uma linguagem de programação amplamente utilizada no mundo, alimentando virtualmente todos os web sites, bem como aplicativos móveis (React Native, Ionic) e aplicativos de desktop (Electron, Discord, Slack, etc).


## Linguagem interpretada

JavaScript é uma linguagem interpretada, assim como PHP, Python e Ruby, em oposição a uma linguagem compilada como C, Java e Rust. Por interpretada, entende-se que o código fonte é executado diretamente por um interpretador, sem a necessidade de um processo de compilação prévio para transformar o código fonte em código de máquina executável.

No navegador, o interpretador de JavaScript é parte do motor do navegador (como V8 no Google Chrome e Node.js, SpiderMonkey no Firefox, JavaScriptCore no Safari, etc.). Em ambientes fora do navegador, como o Node.js, o interpretador é parte do ambiente de execução.

Experimente o interpretador agora mesmo: abra o console do seu navegador (geralmente com F12 ou Ctrl+Shift+J) e digite:

```javascript
alert(`Olá, ${prompt("Qual é o seu nome?")}!`);
```


## Linguagem de tipagem dinâmica

JavaScript é uma linguagem de tipagem dinâmica, assim como Python, Ruby e PHP, em oposição a linguagens de tipagem estática como C, C# e Java. Por tipagem dinâmica, entende-se que o tipo de uma variável é pós-determinado e conhecido em tempo de execução, permitindo maior flexibilidade na atribuição de valores.

Experimente agora mesmo no console do seu navegador:

```javascript
var valor = 42; // valor é um número
console.log(typeof valor); // "number"
valor = "Olá, mundo!"; // agora valor é uma string
console.log(typeof valor); // "string"
```

## Ambiente de execução

JavaScript é executado em diversos ambientes, desde que seja disponibilizado um JavaScript engine (motor), sendo os mais comuns os navegadores web e o Node.js. Cada ambiente fornece APIs específicas que permitem interagir com o sistema onde o JavaScript está sendo executado. Por exemplo, em um navegador você pode pegar a localização geográfica do usuário através da API de Geolocalização, enquanto no Node.js você pode acessar o sistema de arquivos do servidor.

Teste você mesmo no console do navegador:

```javascript
navigator.geolocation.getCurrentPosition(function(position) {
    console.log(`Eu estou em Latitude: ${position.coords.latitude} e Longitude: ${position.coords.longitude}`);
});
```

O objeto `navigator` é uma API específica do ambiente do navegador e não está disponível no Node.js, por exemplo. Para executar JavaScript fora do navegador é necessário instalar o Node.js.

## Instalando o Node.js

Para instalar o Node.js, siga os passos abaixo:

1. Acesse o site oficial do Node.js: [https://nodejs.org/](https://nodejs.org/);
2. Baixe o instalador adequado para o seu sistema operacional (Windows, macOS, Linux) -- de preferência a versão LTS (Long Term Support);
3. Execute o instalador e siga as instruções na tela;
4. Após a instalação, abra o terminal (Prompt de Comando no Windows, Terminal no macOS/Linux) e verifique se o Node.js foi instalado corretamente:


```bash
node -v
```

Deve exibir a versão do Node.js instalada.

Há três maneiras para executar um código JavaScript usando o Node.js:

1. **REPL (Read-Eval-Print Loop)**: Abra o terminal e digite `node` para iniciar o REPL interativo. Você pode digitar comandos JavaScript diretamente e ver os resultados imediatamente, como: `console.log("Olá, mundo!");`;
2. **Arquivo JavaScript**: Crie um arquivo com a extensão `.js` (por exemplo, `programinha.js`) e escreva seu código JavaScript nele. Depois, execute o arquivo no terminal com o comando `node programinha.js`;
3. **Executar código diretamente no terminal**: Você pode executar um comando JavaScript diretamente no terminal usando o comando `node -e "console.log('Olá, mundo!');"`.

Recortes pequenos de código neste guia podem ser testados diretamente no console do navegador, no REPL do Node.js ou diretamente no terminal (3ra opção acima). Exemples maiores podem ser salvos em arquivos `.js` e executados com o Node.js. Os projetos mais complexos serão criados usando o gerenciador de pacotes npm (Node Package Manager), que é instalado automaticamente junto com o Node.js (que será explicado mais adiante nesse guia).


## Valores

Em JavaScript, tudo gira em torno de valores. Valores são as unidades básicas de dados que o programa manipula. Eles podem ser números, texto, objetos, funções, entre outros. Cada valor tem um tipo associado a ele, que determina como o valor pode ser usado e quais operações podem ser realizadas sobre ele.

JavaScript possui dois tipos principais de valores: primitivos e objetos. Primeiramente, vamos explorar os primitivos, listados abaixo:

- `Number`: representa números, tanto inteiros quanto de ponto flutuante (ex: `42`, `3.14`, `-7`, `2.8e3`) e também valores especiais como `Infinity`, `-Infinity` e `NaN` (Not a Number);
- `String`: representa sequências de caracteres (ex: `"Olá, mundo!"`);
- `Boolean`: representa valores lógicos, `true` ou `false`;
- `Undefined`: representa uma variável que foi declarada, mas não inicializada;
- `Null`: representa a ausência intencional de qualquer valor;
- `Symbol`: representa um identificador único e imutável (introduzido no ECMAScript 6);
- `BigInt`: representa números inteiros muito grandes (introduzido no ECMAScript 2020).

Experimente o seguinte código:

```javascript
console.log(typeof 42); // "number"
console.log(typeof "Olá, mundo!"); // "string"
console.log(typeof true); // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null); // "object" (isso é um bug histórico em JavaScript)
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

Strings literais são definidas com aspas simples (`'`), aspas duplas (`"`) ou crases (`` ` ``). As crases permitem interpolação de variáveis e expressões usando `${}`:

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


## Operadores

Operadores são símbolos ou palavras-chave que realizam operações sobre valores. Eles podem ser classificados nas seguintes categorias:

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
console.log(5 > 'teste'); // false (comparação numérica, 'teste' é NaN)
console.log(5 < 'teste'); // false (comparação numérica, 'teste' é NaN)
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
var x = 10; // atribuição simples
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
var y = 5;
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
var idade = 20;
var podeDirigir = (idade >= 18) ? "Sim" : "Não";
console.log(podeDirigir); // "Sim" porque idade é 20 e 20 >= 18
```

Exemplo de uso do operador typeof:

```javascript
console.log(typeof 42); // "number"
console.log(typeof "Olá"); // "string"
console.log(typeof true); // "boolean"
```

Exemplos de uso dos operadores bit a bit:

```javascript
console.log(5 & 3); // 1 (0101 & 0011 = 0001)
console.log(5 | 3); // 7 (0101 | 0011 = 0111)
console.log(5 ^ 3); // 6 (0101 ^ 0011 = 0110)
console.log(5 << 1); // 10 (0101 << 1 = 1010)
console.log(5 >> 1); // 2 (0101 >> 1 = 0010)
console.log(5 >>> 1); // 2 (0101 >>> 1 = 0010)
```

## Expressões, Sentenças, Declarações e Blocos

Em JavaScript, uma **expressão** é qualquer fragmento de código que produz um valor. Pode ser tão simples quanto um número ou uma string literal, ou tão complexo quanto uma chamada de função ou uma operação matemática. Por exemplo:

```javascript
5 + 3; // expressão que produz o valor 8
"Olá, " + "mundo!"; // expressão que produz a string "Olá, mundo!"
Math.max(5, 10); // expressão que produz o valor 10
```

Sentenças (ou instruções) são unidades completas de código que realizam uma ação. Elas podem incluir expressões, mas também podem conter palavras-chave e estruturas de controle. As sentenças geralmente terminam com um ponto e vírgula (`;`), embora em muitos casos o JavaScript permita omiti-lo. Exemplos de sentenças incluem:

```javascript
var x = 10; // declaração de variável (sentença)

console.log(x); // chamada de função (sentença)
if (x > 5) { // sentença condicional
    console.log("x é maior que 5");
}
```

As declarações são um tipo específico de sentença que introduz novas variáveis, funções ou outras entidades no escopo atual. Exemplos de declarações incluem:

```javascript
var y = 20; // declaração de variável

function dobro(n) { // declaração de função
    return n * 2;
}
```

Os blocos são conjuntos de sentenças agrupadas entre chaves `{}`. Eles são usados para definir o escopo de variáveis e para agrupar sentenças em estruturas de controle, como loops e condicionais. Por exemplo:

```javascript
var x = 10;

if (x > 5) { // o bloco começa aqui
    var mensagem = "x é maior que 5";
    console.log(mensagem);
} // o bloco termina aqui   
```

Blocos podem ser aninhados dentro de outros blocos, permitindo a criação de estruturas complexas de controle de fluxo, por exemplo:

```javascript
for (var i = 0; i < 3; i++) { // bloco do loop
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

A estrutura condicional mais simples é o `if`, que executa um bloco de código se uma condição for verdadeira:

```javascript
var idade = 20;
if (idade >= 18) {
    console.log("Você é maior de idade.");
}

// ainda, o bloco pode ser omitido se houver apenas uma sentença:
if (idade >= 18) console.log("Você é maior de idade.");
```

Estruturas mais complexas podem ser criadas usando `else if` e `else`:

```javascript
var nota = 8.5;
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
var dia = new Date().getDay(); // 0 (Domingo) a 6 (Sábado)
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
var caractere = 'I';
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

Use o `while` para repetir um bloco de código enquanto uma condição for verdadeira:

```javascript
var surpresa = "ah";
var nivelSurpresa = 10;
while (surpresa.length < nivelSurpresa) {
    surpresa += "h";
    if (surpresa.length == nivelSurpresa) surpresa += "!";
}
console.log(surpresa); // "ahhhhhhhhh!"
```

O mesmo código pode ser escrito usando `do/while`, que garante que o bloco seja executado pelo menos uma vez:

```javascript
var surpresa = "ah";
var nivelSurpresa = 2;
do {
    surpresa += "h";
    if (surpresa.length == nivelSurpresa) surpresa += "!";
} while (surpresa.length < nivelSurpresa);
console.log(surpresa); // "ah!"
```

E todos os exemplos acima podem ser escritos usando `for`, que é especialmente útil quando o número de iterações é conhecido:

```javascript
var surpresa = "ah";
var nivelSurpresa = 5;
for (var i = surpresa.length; i < nivelSurpresa; i++) {
    surpresa += "h";
    if (surpresa.length == nivelSurpresa) surpresa += "!";
}
console.log(surpresa); // "ahhhh!"
```

O tratamento de exceções será abordado mais adiante neste guia, assim como funções e retornos.


## Declaração de Funções

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
var resultado = somar(5, 3);
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
    var surpresa = "ah";
    for (var i = surpresa.length; i < nivelSurpresa; i++) {
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
    var surpresa = "ah";
    for (var i = surpresa.length; i < nivelSurpresa; i++) {
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

    var sentimento = "ah";
    for (var i = sentimento.length; i < nivelSurpresa; i++) {
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

## Composição de Funções

Funções podem chamar outras funções dentro de seu corpo, permitindo a composição de funcionalidades e a criação de programas mais complexos. Isso promove a reutilização de código e a modularidade. Aqui está um exemplo simples de composição de funções:

```javascript
function dobrar(n) {
    return n * 2;
}

function somar(a, b) {
    return a + b;
}

function somarEDobrar(x, y) {
    var soma = somar(x, y); // chama a função somar
    return dobrar(soma); // chama a função dobrar
}

// Chamando a função composta:
console.log(somarEDobrar(3, 4)); // (3 + 4) * 2 = 14
```

Voltando ao exemplo da surpresa, podemos dividir a lógica em funções menores para melhorar a clareza e a reutilização:

```javascript
function expressarSurpresa(nivelSurpresa = 5) {
    var vogal = 'a';
    return expressar(vogal, nivelSurpresa);
}

function expressarDecepcao(nivelDecepcao = 5) {
    var vogal = 'o';
    return expressar(vogal, nivelDecepcao);
}

function expressar(vogal = 'a', nivel = 5) {
    if (typeof nivel !== 'number') {
        return NaN;
    }
    if (nivel <= 0) {
        return "Nenhuma expressão, na verdade";
    }
    if (nivel > 100) {
        return "Expressão demais!";
    }
    var sentimento = "ah";
    for (var i = sentimento.length; i < nivel; i++) {
        sentimento += "h";
    }
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

## Funções Anônimas e Arrow Functions

Funções anônimas são funções que não possuem um nome associado. Elas são frequentemente usadas como argumentos para outras funções, especialmente em _callbacks_ e funções de ordem superior. Aqui está um exemplo de uma função usada como callback em um método de array:

```javascript
var quadrado = function(n) {
    return n * n;
};
var numeros = [1, 2, 3, 4, 5];
var quadrados = numeros.map(quadrado);
console.log(quadrados); // [1, 4, 9, 16, 25]
```

Se a função dobro fosse apenas usada uma vez, poderíamos defini-la diretamente como uma *função anônima* dentro do `map`:

```javascript
var numeros = [1, 2, 3, 4, 5];
var quadrados = numeros.map(function(n) {
    return n * n;
});
console.log(quadrados); // [1, 4, 9, 16, 25]
```

As arrow functions (funções de seta) são uma sintaxe mais concisa para escrever funções anônimas introduzida no ECMAScript 6 (ES6). Elas utilizam a flecha `=>` para separar os parâmetros do corpo da função. Aqui está o mesmo exemplo usando uma arrow function:

```javascript
var numeros = [1, 2, 3, 4, 5];
var quadrados = numeros.map(n => n * n);
console.log(quadrados); // [1, 4, 9, 16, 25]
```

_Arrow functions_ também pode ser usadas para declarar funções:

```javascript
var pluralizar = palavra => {
    if (palavra.endsWith("s")) return palavra; // já está no plural
    if (palavra.endsWith("ão")) return palavra.slice(0, -2) + "ões"; // ex.: "coração" -> "corações"
    if (palavra.endsWith("m")) return palavra.slice(0, -1) + "ns"; // ex.: "homem" -> "homens"
    if (palavra.endsWith("l")) return palavra.slice(0, -1) + "is"; // ex.: "animal" -> "animais"
    if (palavra.endsWith("r") || palavra.endsWith("z")) return palavra + "es"; // ex.: "flor" -> "flores"

    return palavra + "s";
}

console.log(pluralizar("carro")); // "carros"
```

## Módulos em JavaScript

Módulos são unidades de código reutilizáveis que encapsulam funcionalidades específicas, permitindo a organização e a separação de responsabilidades em um programa. Em JavaScript, os módulos podem ser criados usando a sintaxe de módulos ES6 (ECMAScript 2015) ou utilizando sistemas de módulos como CommonJS (usado no Node.js). Neste guia, focaremos na sintaxe de módulos ES6 que é padrão em ambientes modernos.






## Biblioteca Padrão do JavaScript

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


## Próximos passos

Agora que você já conhece as bases do JavaScript, está na hora de aprofundar seus conhecimentos. Explore os seguintes tópicos para continuar sua jornada:

- Variáveis e Tipos de Dados
- Operadores e Expressões
- Estruturas de Controle if, switch, loops)
- Funções e Escopo
- Objetos e Arrays
- Manipulação do DOM (Document Object Model)
- Eventos e Manipulação de Eventos
- Programação Assíncrona (Promises, async/await)
- Módulos e Pacotes (npm)
- Ferramentas de Desenvolvimento (Babel, Webpack)
- Frameworks e Bibliotecas Populares (React, Angular, Vue.js)
- Testes e Depuração
- Boas Práticas e Padrões de Código
- Desenvolvimento Full-Stack com JavaScript (Node.js, Express, MongoDB)
- Segurança em Aplicações JavaScript
- Performance e Otimização
- Acessibilidade em Aplicações Web
- Progressive Web Apps (PWAs)
- WebAssembly e JavaScript
- Desenvolvimento Mobile com JavaScript (React Native, Ionic)
- Electron para Aplicações Desktop
- Tendências Futuras em JavaScript (ESNext, Web3, etc.)
- Contribuição para Projetos Open Source em JavaScript
- Comunidade e Recursos de Aprendizado
- Carreira como Desenvolvedor JavaScript
- Preparação para Entrevistas Técnicas em JavaScript
- Construção de Portfólio e Projetos Pessoais
- Networking e Participação em Eventos da Comunidade
- Desenvolvimento Contínuo e Aprendizado ao Longo da Carreira
- Exploração de Outras Linguagens Relacionadas (TypeScript, CoffeeScript)
- Participação em Hackathons e Desafios de Programação
- Mentoria e Ensino de JavaScript para Outros
- Desenvolvimento de Soft Skills para Desenvolvedores
- Gestão de Projetos e Colaboração em Equipes de Desenvolvimento
- Exploração de Novas Tecnologias e Ferramentas no Ecossistema JavaScript
- Contribuição para a Evolução do JavaScript (propostas para o TC39)
- Exploração de Casos de Uso Avançados (Machine Learning, IoT, etc.)
- Desenvolvimento de Jogos com JavaScript (Three.js, Babylon.js)
- Participação em Conferências e Workshops de JavaScript
- Leitura de Livros e Artigos Avançados sobre JavaScript
- Exploração de Padrões de Design em JavaScript
- Desenvolvimento de APIs com JavaScript (GraphQL, REST)
- Exploração de Ferramentas de DevOps para Projetos JavaScript (Docker, CI/CD)
- Desenvolvimento de Aplicações em Tempo Real com JavaScript (Socket.io, WebSockets)