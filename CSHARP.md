# As Bases com C#

As linguagens de programação servem para nós expressarmos o que queremos que o computador faça. Como os idiomas humanos, elas são diferentes na escrita (sintaxe) e até na forma de organizar o pensamento (paradigma de programação). Até usando a mesma linguagem podemos encontrar diversas maneiras de resolver um mesmo problema. No entanto, todas essas linguagens compartilham construtos comuns para guardar o estado do programa, decidir o que fazer dada uma condição, realizar um conjunto de tarefas um determinado número de vezes, obter e devolver informações, modularizar uma solução reutilizável, etc. Esse guia apresenta esses construtos usando a linguagem de programação C#.

## Sumário

- [As Bases com C#](#as-bases-com-c)
  - [Sumário](#sumário)
  - [Introdução](#introdução)
    - [História do C#](#história-do-c)
    - [Linguagem Compilada](#linguagem-compilada)
    - [Linguagem de Tipagem Estática](#linguagem-de-tipagem-estática)
    - [Linguagem de Tipagem Forte](#linguagem-de-tipagem-forte)
    - [Ambiente de Execução](#ambiente-de-execução)
    - [Instalando o .NET](#instalando-o-net)
  - [Estado e Computação](#estado-e-computação)
    - [Valores](#valores)
    - [Variáveis e Constantes](#variáveis-e-constantes)
      - [Declaração de Variáveis com Tipos Explícitos](#declaração-de-variáveis-com-tipos-explícitos)
      - [Inferência de Tipos com var](#inferência-de-tipos-com-var)
      - [Constantes](#constantes)
      - [Exemplos Práticos](#exemplos-práticos)
      - [Ordem de Preferência para Declarar Variáveis](#ordem-de-preferência-para-declarar-variáveis)
      - [Escopo de Variáveis](#escopo-de-variáveis)
    - [Operadores](#operadores)
    - [Expressões, Sentenças, Declarações e Blocos](#expressões-sentenças-declarações-e-blocos)
  - [Estruturas de Controle](#estruturas-de-controle)
    - [Estruturas Condicionais](#estruturas-condicionais)
    - [Estruturas de Repetição](#estruturas-de-repetição)
    - [Estruturas para o Tratamento de Exceções](#estruturas-para-o-tratamento-de-exceções)
  - [Funções e Métodos](#funções-e-métodos)
    - [Declaração de Métodos](#declaração-de-métodos)
    - [Retorno de Métodos](#retorno-de-métodos)
    - [Composição de Métodos](#composição-de-métodos)
    - [Métodos Anônimos e Funções Lambda](#métodos-anônimos-e-funções-lambda)
  - [Programação Modular](#programação-modular)
    - [Projetos C#](#projetos-c)
    - [Programação Modular em C#](#programação-modular-em-c)
    - [Biblioteca Padrão do C#](#biblioteca-padrão-do-c)
  - [Estruturas de Dados em C#](#estruturas-de-dados-em-c)
    - [Estruturas de Dados Elementares](#estruturas-de-dados-elementares)
      - [Tipos de Valor em C#](#tipos-de-valor-em-c)
      - [Classes e Objetos em C#](#classes-e-objetos-em-c)
      - [Listas e Coleções](#listas-e-coleções)
      - [Conjuntos](#conjuntos)
      - [Dicionários](#dicionários)
    - [Estruturas de Dados Compostas](#estruturas-de-dados-compostas)
    - [Registros em C#](#registros-em-c)
  - [Considerações Finais](#considerações-finais)


## Introdução

### História do C#

A história serve para compreender o presente através do passado.

C# foi desenvolvido pela Microsoft a partir de 2000 como parte da iniciativa .NET Framework, com o objetivo de criar uma linguagem moderna orientada a objetos que combinasse o poder do C++ com a simplicidade do Visual Basic e as capacidades de gerenciamento automático de memória inspiradas em Java. Anders Hejlsberg, o principal arquiteto do C#, também foi responsável pela criação do Delphi e influenciou o desenvolvimento de TypeScript. A primeira versão (C# 1.0) foi lançada em 2002 junto com o .NET Framework 1.0.

C# foi projetado desde o início para ser uma linguagem de tipagem forte e estática, o que contrasta significativamente com linguagens como JavaScript. Essa decisão de design oferecia maior segurança em tempo de compilação, melhor desempenho e suporte melhorado do IDE (Integrated Development Environment) como o Visual Studio.

Ao longo dos anos, C# evoluiu significativamente. Recursos importantes foram adicionados em versões subsequentes: C# 2.0 introduziu genéricos, C# 3.0 introduziu LINQ (Language Integrated Query) e tipos anônimos, C# 5.0 introduziu async/await para programação assíncrona, C# 8.0 introduziu tipos de referência anulável (nullable reference types) e C# 9.0 introduziu registros (records) como um novo tipo de referência. Em 2020, a Microsoft liberou o .NET 5 (agora chamado de .NET Core) como a plataforma principal para desenvolvimento em C#, consolidando C# como uma linguagem verdadeiramente multiplataforma.

Atualmente, C# é amplamente utilizado para desenvolvimento de aplicações empresariais, jogos (especialmente com Unity), servidores web (com ASP.NET Core) e aplicações desktop (com Windows Forms, WPF e MAUI). C# é uma linguagem de propósito geral, moderna e em contínua evolução.

### Linguagem Compilada

C# é uma linguagem compilada, assim como C, C++ e Java, em oposição a uma linguagem interpretada como JavaScript, Python e Ruby. Por compilada, entende-se que o código fonte é traduzido para um formato intermediário chamado Intermediate Language (IL) durante o processo de compilação, que é então executado pelo .NET Runtime (anteriormente chamado de Common Language Runtime - CLR).

O processo de compilação em C# ocorre em duas fases:

1. **Compilação para IL**: O compilador C# (`csc`) traduz o código fonte para Intermediate Language.
2. **Compilação Just-In-Time (JIT)**: O .NET Runtime compila o IL para código de máquina nativo durante a execução.

Essa abordagem oferece benefícios tanto da compilação antecipada quanto da interpretação, permitindo otimizações em tempo de execução e portabilidade entre plataformas.

Para executar um programa em C#, você precisa ter o .NET SDK instalado. O processo típico é:

```bash
dotnet build     # Compila o projeto
dotnet run       # Executa o programa compilado
```

### Linguagem de Tipagem Estática

C# é uma linguagem de tipagem estática, assim como Java, C++ e Rust, em oposição a linguagens de tipagem dinâmica como JavaScript, Python e Ruby. Por tipagem estática, entende-se que o tipo de uma variável é determinado em tempo de compilação, não em tempo de execução. Isso significa que você deve declarar o tipo de cada variável, parâmetro e retorno de função explicitamente.

A tipagem estática oferece várias vantagens:

- **Segurança em Tempo de Compilação**: Os erros de tipo são detectados antes da execução do programa.
- **Melhor Desempenho**: O compilador pode otimizar o código com base nos tipos conhecidos.
- **Melhor Suporte do IDE**: O editor pode fornecer autocompletar e refatoração mais precisos.
- **Documentação Clara**: Os tipos servem como documentação implícita do código.

Experimente o seguinte código:

```csharp
int idade = 30;          // idade é um inteiro
string nome = "João";    // nome é uma string
double salario = 3500.50; // salario é um número de ponto flutuante

// Isso causaria um erro de compilação:
// string x = 42;  // Erro: não é possível converter int para string implicitamente
```

### Linguagem de Tipagem Forte

C# é uma linguagem de tipagem forte, o que significa que não há conversão implícita entre tipos incompatíveis. Por exemplo, não é possível atribuir um inteiro a uma variável de string sem uma conversão explícita. Isso contrasta com linguagens como JavaScript que são fracamente tipadas.

```csharp
int numero = 42;
string texto = numero.ToString();  // conversão explícita necessária

// Conversão de string para inteiro
string entrada = "123";
int valor = int.Parse(entrada);    // ou int.TryParse(entrada, out valor);
```

### Ambiente de Execução

C# é executado no .NET Runtime, que fornece um ambiente gerenciado com coleta de lixo automática, gerenciamento de memória e acesso a uma extensa biblioteca padrão. O .NET permite desenvolver aplicações para múltiplas plataformas (Windows, Linux, macOS) a partir de um único código-base.

Existem várias implementações do .NET:

- **.NET Framework**: A implementação original, disponível apenas para Windows.
- **.NET Core**: Agora chamado apenas de .NET, é a implementação moderna e multiplataforma.
- **Mono**: Implementação de código aberto do .NET.

### Instalando o .NET

Para instalar o .NET, siga os passos abaixo:

1. Acesse o site oficial do .NET: [https://dotnet.microsoft.com/](https://dotnet.microsoft.com/);
2. Baixe o instalador adequado para o seu sistema operacional (Windows, macOS, Linux) -- de preferência a versão LTS (Long Term Support);
3. Execute o instalador e siga as instruções na tela;
4. Após a instalação, abra o terminal (Prompt de Comando no Windows, Terminal no macOS/Linux) e verifique se o .NET foi instalado corretamente:

```bash
dotnet --version
```

O comando anterior deve exibir a versão do .NET instalada.

Para criar um novo projeto C# console, execute:

```bash
dotnet new console -n MeuProjetoCSharp
cd MeuProjetoCSharp
dotnet run
```

Este comando cria um novo projeto de console com a seguinte estrutura:

```
MeuProjetoCSharp/
├── Program.cs
├── MeuProjetoCSharp.csproj
└── obj/
```

O arquivo `Program.cs` contém o código inicial:

```csharp
// Program.cs
Console.WriteLine("Hello, World!");
```

Para executar o projeto:

```bash
dotnet run
```


## Estado e Computação

### Valores

Em C#, tudo gira em torno de valores tipados. Valores são as unidades básicas de dados que o programa manipula, e cada valor tem um tipo explícito associado a ele, que determina como o valor pode ser usado e quais operações podem ser realizadas sobre ele.

C# possui dois tipos principais de valores: tipos de valor (value types) e tipos de referência (reference types).

**Tipos de Valor Primitivos:**

- `int`: Inteiro de 32 bits (ex: `42`, `-7`, `0`)
- `long`: Inteiro de 64 bits (ex: `9223372036854775807L`)
- `float`: Número de ponto flutuante de 32 bits (ex: `3.14f`)
- `double`: Número de ponto flutuante de 64 bits (ex: `3.14159`, `2.8e3`)
- `decimal`: Número decimal de alta precisão para operações financeiras (ex: `19.95m`)
- `bool`: Valor booleano, `true` ou `false`
- `char`: Caractere Unicode único (ex: `'A'`, `'é'`)
- `string`: Sequência de caracteres (ex: `"Olá, mundo!"`)

**Tipos de Referência:**

- `object`: Tipo base de todos os tipos em C#
- `string`: Cadeias de caracteres (imutáveis)
- Classes customizadas

Experimente o seguinte código:

```csharp
int numero = 42;
double valor = 3.14;
string texto = "Olá, mundo!";
bool condicao = true;
char caractere = 'A';

Console.WriteLine($"número: {numero}, tipo: {numero.GetType()}");          // int
Console.WriteLine($"valor: {valor}, tipo: {valor.GetType()}");            // double
Console.WriteLine($"texto: {texto}, tipo: {texto.GetType()}");            // string
Console.WriteLine($"condicao: {condicao}, tipo: {condicao.GetType()}");    // bool
Console.WriteLine($"caractere: {caractere}, tipo: {caractere.GetType()}"); // char
```

Em C#, não há valores especiais como `NaN` ou `Infinity` para números inteiros, mas números de ponto flutuante podem ter esses valores:

```csharp
double infinito = double.PositiveInfinity;
double nao = double.NaN;
Console.WriteLine(infinito);  // Infinity
Console.WriteLine(nao);       // NaN
```

As strings em C# são sequências de caracteres Unicode de 16 bits. Você pode acessar caracteres individuais usando notação de índice:

```csharp
string palavra = "C#";
Console.WriteLine(palavra[0]); // 'C'
Console.WriteLine(palavra[1]); // '#'
Console.WriteLine(palavra.Length); // 2

// Strings têm diversos métodos úteis
Console.WriteLine(palavra.ToUpper());        // "C#"
Console.WriteLine(palavra.ToLower());        // "c#"
Console.WriteLine("Olá".Length);             // 3
```

C# suporta interpolação de strings usando o prefixo `$`:

```csharp
string nome = "Alice";
int idade = 25;
// Usando interpolação de strings
Console.WriteLine($"Olá, {nome}! Você tem {idade} anos.");
// "Olá, Alice! Você tem 25 anos."

// Concatenação tradicional
Console.WriteLine("Olá, " + nome + "! Você tem " + idade + " anos.");
```

### Variáveis e Constantes

Variáveis são usadas para armazenar valores que podem ser alterados durante a execução do programa. Em C#, variáveis devem ser declaradas com um tipo explícito usando a palavra-chave `var` (tipo inferido), ou especificando o tipo diretamente (recomendado para clareza). Constantes são valores que não podem ser alterados após a inicialização, declaradas com a palavra-chave `const`.

#### Declaração de Variáveis com Tipos Explícitos

A forma mais clara e recomendada é declarar o tipo explicitamente:

```csharp
int idade = 30;
string nome = "João";
double salario = 3500.50;
bool ativo = true;

Console.WriteLine($"Nome: {nome}, Idade: {idade}, Salário: {salario}");
```

#### Inferência de Tipos com var

C# suporta **inferência de tipos** através da palavra-chave `var`, que permite ao compilador determinar o tipo automaticamente com base no valor atribuído. Isso reduz a verbosidade do código enquanto mantém a tipagem estática e forte. O compilador infere o tipo em tempo de compilação, não em tempo de execução como em linguagens dinamicamente tipadas.

```csharp
var idade = 30;              // compilador infere como int
var nome = "João";           // compilador infere como string
var salario = 3500.50;       // compilador infere como double
var ativo = true;            // compilador infere como bool

Console.WriteLine($"Nome: {nome}, Idade: {idade}");
// O tipo ainda é estático e forte:
Console.WriteLine(idade.GetType());   // System.Int32
Console.WriteLine(nome.GetType());    // System.String
```

A inferência de tipos com `var` é especialmente útil quando o tipo é evidente ou ao trabalhar com tipos complexos:

```csharp
// Com tipos complexos, var reduz verbosidade:
var dicionario = new Dictionary<string, int> { { "Alice", 30 }, { "Bob", 25 } };
var lista = new List<string> { "maçã", "banana", "laranja" };
var resultado = Math.Max(10, 20);

// Comparado com:
Dictionary<string, int> dicionario2 = new Dictionary<string, int> { { "Alice", 30 }, { "Bob", 25 } };
List<string> lista2 = new List<string> { "maçã", "banana", "laranja" };
int resultado2 = Math.Max(10, 20);
```

**Importante**: `var` NÃO torna o código dinamicamente tipado. O tipo é determinado em tempo de compilação e não pode ser alterado:

```csharp
var numero = 42;        // tipo: int
// numero = "texto";    // ERRO em tempo de compilação: não é possível atribuir string a int

var texto = "Olá";      // tipo: string
// texto = 123;         // ERRO em tempo de compilação: não é possível atribuir int a string
```

#### Constantes

Constantes são valores que não podem ser alterados após a inicialização. Elas são declaradas com a palavra-chave `const` e devem ser inicializadas no momento da declaração:

```csharp
const double PI = 3.14159;
const int DIAS_POR_ANO = 365;
const string VERSAO = "1.0.0";

Console.WriteLine($"PI: {PI}, Dias por ano: {DIAS_POR_ANO}");

// PI = 3.14;    // ERRO em tempo de compilação: não é possível reatribuir uma constante
```

#### Exemplos Práticos

```csharp
// Reatribuição de variáveis:
var idade = 30;
idade = 31;      // válido
var nome = "João";
nome = "Maria";  // válido

// As variáveis em C# também podem ser inicializadas após a declaração:
int numero;
numero = 42;     // inicialização após declaração
Console.WriteLine(numero);

// Usando var em loops:
var numeros = new[] { 1, 2, 3, 4, 5 };
foreach (var numero in numeros) {
    Console.WriteLine(numero * 2);
}

// Com LINQ:
var pares = numeros.Where(n => n % 2 == 0).ToList();
// pares é do tipo List<int>, inferido pelo compilador
```

#### Ordem de Preferência para Declarar Variáveis

A ordem recomendada para declarar variáveis em C# é:

1. `const` - para valores que não podem ser alterados;
2. Tipo explícito (`int`, `string`, `List<T>`, etc.) - quando você quer documentar o tipo claramente;
3. `var` - quando o tipo é óbvio pelo contexto e torna o código mais legível.

```csharp
// Exemplo de cada preferência:
const double PI = 3.14159;                  // 1. Constante
string nome = "João";                       // 2. Tipo explícito (documentação clara)
var idade = 30;                             // 3. var (tipo óbvio: int)
Dictionary<string, int> dados = new();      // 2. Tipo complexo (para clareza)
```

#### Escopo de Variáveis

Em C#, as variáveis têm escopo de bloco. Uma variável declarada dentro de um bloco `{}` é acessível apenas dentro daquele bloco:

```csharp
void ExemploEscopo()
{
    var x = 10; // escopo de método
    {
        var y = 20; // escopo de bloco
        Console.WriteLine(x); // 10 (válido)
        Console.WriteLine(y); // 20 (válido)
    }
    // Console.WriteLine(y); // ERRO: y está fora do escopo
}
```

### Operadores

Operadores são símbolos ou palavras-chave que realizam operações sobre valores. Eles podem ser classificados nas seguintes categorias:

- Operadores **Aritméticos**: realizam operações matemáticas básicas, como adição (`+`), subtração (`-`), multiplicação (`*`), divisão (`/`), módulo (`%`);
- Operadores de **Comparação**: comparam dois valores e retornam um valor booleano `true` ou `false`, como igualdade (`==`), desigualdade (`!=`), maior que (`>`), menor que (`<`), etc.;
- Operadores **Lógicos**: combinam valores booleanos e retornam um valor booleano, como E (`&&`), OU (`||`) e NÃO (`!`);
- Operadores de **Atribuição**: atribuem valores a variáveis. O operador mais comum é o igualdade (`=`);
- Operadores de **Incremento e Decremento**: aumentam ou diminuem o valor de uma variável em 1. O operador de incremento é `++` e o de decremento é `--`;
- Operadores **Ternários**: uma forma concisa de expressar uma condição com a sintaxe `condição ? valorSeVerdadeiro : valorSeFalso`;
- Operadores **Bit a Bit**: realizam operações a nível de bits em números inteiros.

Exemplos de uso dos operadores aritméticos:

```csharp
Console.WriteLine(5 + 3);   // 8
Console.WriteLine(10 - 4);  // 6
Console.WriteLine(6 * 7);   // 42
Console.WriteLine(20 / 5);  // 4
Console.WriteLine(10 % 3);  // 1 (resto da divisão)
```

Exemplos de uso dos operadores de comparação:

```csharp
Console.WriteLine(5 == 5);     // true
Console.WriteLine(5 != 3);     // true
Console.WriteLine(5 > 3);      // true
Console.WriteLine(5 < 10);     // true
Console.WriteLine(5 >= 5);     // true
Console.WriteLine(3 <= 2);     // false
```

Exemplos de uso dos operadores lógicos:

```csharp
Console.WriteLine(true && false);   // false
Console.WriteLine(true || false);   // true
Console.WriteLine(!true);           // false
Console.WriteLine((5 > 3) && (2 < 4)); // true
```

Exemplos de uso dos operadores de atribuição:

```csharp
int x = 10;      // atribuição simples
x += 5;          // equivalente a x = x + 5
Console.WriteLine(x);  // 15
x -= 3;          // equivalente a x = x - 3
Console.WriteLine(x);  // 12
x *= 2;          // equivalente a x = x * 2
Console.WriteLine(x);  // 24
x /= 4;          // equivalente a x = x / 4
Console.WriteLine(x);  // 6
```

Exemplo de uso do operador ternário:

```csharp
int idade = 20;
string podeDirigir = (idade >= 18) ? "Sim" : "Não";
Console.WriteLine(podeDirigir);  // "Sim"
```

### Expressões, Sentenças, Declarações e Blocos

Em C#, uma **expressão** é qualquer fragmento de código que produz um valor. Pode ser tão simples quanto um número ou uma string literal, ou tão complexo quanto uma chamada de método ou uma operação matemática. Por exemplo:

```csharp
5 + 3;                    // expressão que produz o valor 8
"Olá, " + "mundo!";       // expressão que produz a string "Olá, mundo!"
Math.Max(5, 10);          // expressão que produz o valor 10
```

Sentenças (ou instruções) são unidades completas de código que realizam uma ação. Elas podem incluir expressões, mas também podem conter palavras-chave e estruturas de controle. As sentenças geralmente terminam com um ponto e vírgula (`;`). Exemplos de sentenças incluem:

```csharp
int x = 10;              // declaração de variável (sentença)
Console.WriteLine(x);    // chamada de método (sentença)
if (x > 5) {             // sentença condicional
    Console.WriteLine("x é maior que 5");
}
```

As declarações são um tipo específico de sentença que introduz novas variáveis, métodos ou outras entidades no escopo atual. Exemplos incluem:

```csharp
int y = 20;              // declaração de variável

int Dobro(int n)         // declaração de método
{
    return n * 2;
}
```

Os blocos são conjuntos de sentenças agrupadas entre chaves `{}`. Eles são usados para definir o escopo de variáveis e para agrupar sentenças em estruturas de controle, como loops e condicionais. Por exemplo:

```csharp
int x = 10;

if (x > 5) {            // o bloco começa aqui
    const string mensagem = "x é maior que 5";
    Console.WriteLine(mensagem);
}                       // o bloco termina aqui
```

Blocos podem ser aninhados dentro de outros blocos:

```csharp
for (int i = 0; i < 3; i++) {           // bloco do loop
    Console.WriteLine($"Iteração {i}");
    if (i % 2 == 0) {                   // bloco aninhado do if
        Console.WriteLine($"{i} é um número par");
    } else {                             // bloco aninhado do else
        Console.WriteLine($"{i} é um número ímpar");
    }
}
```


## Estruturas de Controle

Estruturas de controle são usadas para controlar o fluxo de execução do código com base em condições ou repetições. As principais estruturas de controle em C# incluem:

- Estruturas condicionais: `if`, `else if`, `else`, `switch`
- Estruturas de repetição: `for`, `while`, `do...while`, `foreach`
- Controle de loop: `break`, `continue`
- Tratamento de exceções: `try`, `catch`, `finally`, `throw`
- Declarações de término: `return`

### Estruturas Condicionais

A estrutura condicional mais simples é o `if`, que executa um bloco de código se uma condição for verdadeira:

```csharp
int idade = 20;
if (idade >= 18) {
    Console.WriteLine("Você é maior de idade.");
}

// ainda, o bloco pode ser omitido se houver apenas uma sentença:
if (idade >= 18) Console.WriteLine("Você é maior de idade.");
```

Estruturas mais complexas podem ser criadas usando `else if` e `else`:

```csharp
double nota = 8.5;
if (nota >= 9) {
    Console.WriteLine("A");
} else if (nota >= 8) {
    Console.WriteLine("B");
} else if (nota >= 7) {
    Console.WriteLine("C");
} else if (nota >= 6) {
    Console.WriteLine("D");
} else if (nota >= 5) {
    Console.WriteLine("E");
} else {
    Console.WriteLine("F");
}
```

O `switch` é outra estrutura condicional que pode ser usada quando há múltiplas condições baseadas no valor de uma variável:

```csharp
int dia = DateTime.Now.DayOfWeek switch {
    DayOfWeek.Sunday => 0,
    DayOfWeek.Monday => 1,
    DayOfWeek.Tuesday => 2,
    DayOfWeek.Wednesday => 3,
    DayOfWeek.Thursday => 4,
    DayOfWeek.Friday => 5,
    DayOfWeek.Saturday => 6,
    _ => -1
};

// ou a forma tradicional:
int diaSemana = (int)DateTime.Now.DayOfWeek;
switch (diaSemana) {
    case 0:
        Console.WriteLine("Domingo");
        break;
    case 1:
        Console.WriteLine("Segunda-feira");
        break;
    case 2:
        Console.WriteLine("Terça-feira");
        break;
    default:
        Console.WriteLine("Dia inválido");
        break;
}
```

### Estruturas de Repetição

Use o `while` para repetir um bloco de código enquanto uma condição for verdadeira:

```csharp
string surpresa = "ah";
int nivelSurpresa = 10;
while (surpresa.Length < nivelSurpresa) {
    surpresa += "h";
    if (surpresa.Length == nivelSurpresa) surpresa += "!";
}
Console.WriteLine(surpresa);  // "ahhhhhhhhh!"
```

O mesmo código pode ser escrito usando `do/while`, que garante que o bloco seja executado pelo menos uma vez:

```csharp
string surpresa = "ah";
int nivelSurpresa = 2;
do {
    surpresa += "h";
    if (surpresa.Length == nivelSurpresa) surpresa += "!";
} while (surpresa.Length < nivelSurpresa);
Console.WriteLine(surpresa);  // "ah!"
```

E todos os exemplos acima podem ser escritos usando `for`, que é especialmente útil quando o número de iterações é conhecido:

```csharp
string surpresa = "ah";
int nivelSurpresa = 5;
for (int i = surpresa.Length; i < nivelSurpresa; i++) {
    surpresa += "h";
    if (surpresa.Length == nivelSurpresa) surpresa += "!";
}
Console.WriteLine(surpresa);  // "ahhhh!"
```

C# também oferece `foreach` para iterar sobre coleções:

```csharp
string[] paises = { "Brasil", "Argentina", "Chile" };
foreach (string pais in paises) {
    Console.WriteLine(pais);
}
```

### Estruturas para o Tratamento de Exceções

Em C#, o tratamento de exceções é realizado usando as palavras-chave `try`, `catch`, `finally` e `throw`. Esses construtos permitem que você lide com erros de forma controlada, evitando que o programa falhe abruptamente.

Exemplo de uma função que valida parâmetros e lança exceções:

```csharp
(int valorParcela, int valorUltimaParcela) CalcularParcelas(
    decimal valorEmprestimo, 
    int numeroParcelas, 
    decimal taxaJuros)
{
    if (valorEmprestimo < 100) {
        throw new ArgumentException("O valor do empréstimo deve ser pelo menos 100.");
    }
    if (numeroParcelas < 2) {
        throw new ArgumentException("O número de parcelas deve ser pelo menos 2.");
    }
    if (taxaJuros < 0) {
        throw new ArgumentException("A taxa de juros não pode ser negativa.");
    }
    if (taxaJuros > 1) {
        throw new ArgumentException("A taxa de juros deve ser um valor decimal (por exemplo, 0.05 para 5%).");
    }

    // calcular os juros compostos
    decimal montante = valorEmprestimo * (decimal)Math.Pow((double)(1 + taxaJuros), numeroParcelas);
    int valorParcela = (int)(montante / numeroParcelas);
    int resto = (int)(montante % numeroParcelas);
    int valorUltimaParcela = valorParcela + resto;

    return (valorParcela, valorUltimaParcela);
}

// Usando a função com tratamento de exceções:
try {
    var resultado = CalcularParcelas(1000m, 5, 0.05m);
    Console.WriteLine($"Parcelas calculadas com sucesso: {resultado}");
} catch (ArgumentException erro) {
    Console.Error.WriteLine($"Erro ao calcular parcelas: {erro.Message}");
}
```

O bloco `finally` pode ser usado para executar código que deve ser executado independentemente de uma exceção ter sido lançada ou não:

```csharp
void ExemploFinally() {
    StreamWriter arquivo = null;
    try {
        arquivo = new StreamWriter("dados.txt");
        arquivo.WriteLine("Dados salvos com sucesso.");
    } catch (IOException erro) {
        Console.Error.WriteLine($"Erro ao escrever no arquivo: {erro.Message}");
    } finally {
        if (arquivo != null) {
            arquivo.Dispose();
            Console.WriteLine("Arquivo fechado.");
        }
    }
}
```


## Funções e Métodos

### Declaração de Métodos

Métodos são blocos reutilizáveis de código que realizam uma tarefa específica. Eles recebem entradas (parâmetros), executam operações e retornam um valor. Em C#, métodos devem ter um tipo de retorno explícito (ou `void` se não retornarem nada).

A anatomia básica de um método em C# inclui:

- **Modificador de acesso**: `public`, `private`, `protected`, etc.
- **Tipo de retorno**: O tipo do valor retornado pelo método, ou `void` se não retorna nada
- **Nome do método**: Um identificador que segue as convenções de nomenclatura
- **Parâmetros**: Uma lista de parâmetros com tipos explícitos
- **Corpo do método**: Um bloco de código que contém as instruções a serem executadas

Aqui está um exemplo simples de um método que soma dois números:

```csharp
int Somar(int a, int b) {
    return a + b;
}

// Chamando o método e armazenando o resultado:
int resultado = Somar(5, 3);
Console.WriteLine(resultado);  // 8

// Ou diretamente:
Console.WriteLine(Somar(10, 15));  // 25
```

A sintaxe geral para declarar um método é:

```csharp
[modificador] TipoRetorno NomeDoMétodo(TipoParametro1 parametro1, TipoParametro2 parametro2, ...) {
    // corpo do método
    [return valor];
}
```

Métodos podem ter valores padrão para parâmetros:

```csharp
string ExpressarSurpresa(int nivelSurpresa = 5) {
    string surpresa = "ah";
    for (int i = surpresa.Length; i < nivelSurpresa; i++) {
        surpresa += "h";
        if (surpresa.Length == nivelSurpresa) surpresa += "!";
    }
    return surpresa;
}

// Chamando o método sem argumentos usará o valor padrão:
Console.WriteLine(ExpressarSurpresa());      // "ahhhh!" (nível padrão 5)
Console.WriteLine(ExpressarSurpresa(10));    // "ahhhhhhhhh!" (nível 10)
```

Como bons fazedores de programas, devemos sempre validar os parâmetros recebidos:

```csharp
double Dividir(double a, double b) {
    if (b == 0) {
        throw new ArgumentException("O divisor não pode ser zero.");
    }
    return a / b;
}

// Chamando a função com parâmetros válidos:
Console.WriteLine(Dividir(10, 2));  // 5
```

### Retorno de Métodos

Métodos podem retornar valores usando a palavra-chave `return`. Quando um método encontra uma instrução `return`, ele imediatamente termina sua execução e retorna o valor especificado para o chamador. Se o tipo de retorno for `void`, o método não retorna um valor.

Exemplo de um método que conta o número de vogais em uma string:

```csharp
int ContarVogais(string texto) {
    if (texto == null) return 0;
    
    int contador = 0;
    string vogais = "aeiouAEIOU";
    foreach (char caractere in texto) {
        if (vogais.Contains(caractere)) {
            contador++;
        }
    }
    return contador;
}

// Chamando o método:
int numeroDeVogais = ContarVogais("Olá, mundo!");
Console.WriteLine(numeroDeVogais);  // 4
```

Métodos que podem não retornar um resultado podem usar `null` ou retornar um tipo anulável:

```csharp
Usuario? BuscarUsuarioPorId(int id) {
    Usuario[] usuarios = new[] {
        new Usuario { Id = 1, Nome = "Alice" },
        new Usuario { Id = 2, Nome = "Bob" },
        new Usuario { Id = 3, Nome = "Charlie" }
    };

    foreach (var usuario in usuarios) {
        if (usuario.Id == id) {
            return usuario;
        }
    }
    return null;  // retorna null se o usuário não for encontrado
}

class Usuario {
    public int Id { get; set; }
    public string Nome { get; set; }
}

// Chamando o método:
Usuario? usuario = BuscarUsuarioPorId(2);
if (usuario != null) {
    Console.WriteLine(usuario.Nome);  // "Bob"
}
```

### Composição de Métodos

Métodos podem chamar outros métodos dentro de seu corpo, permitindo a composição de funcionalidades:

```csharp
int Dobrar(int n) {
    return n * 2;
}

int Somar(int a, int b) {
    return a + b;
}

int SomarEDobrar(int x, int y) {
    int soma = Somar(x, y);  // chama o método Somar
    return Dobrar(soma);     // chama o método Dobrar
}

// Chamando a método composto:
Console.WriteLine(SomarEDobrar(3, 4));  // (3 + 4) * 2 = 14
```

Os métodos podem ser aninhados em classes para criar uma estrutura organizada:

```csharp
class Expressoes {
    public string ExpressarSurpresa(int nivelSurpresa = 5) {
        return Expressar('a', nivelSurpresa);
    }

    public string ExpressarDecepcao(int nivelDecepcao = 5) {
        return Expressar('o', nivelDecepcao);
    }

    private string Expressar(char vogal, int nivel = 5) {
        if (nivel <= 0) return "Nenhuma expressão, na verdade";
        if (nivel > 100) return "Expressão demais!";
        
        string sentimento = "" + vogal + "h";
        for (int i = sentimento.Length; i < nivel; i++) {
            sentimento += "h";
        }
        return sentimento + "!";
    }
}

// Usando a classe:
var expressoes = new Expressoes();
Console.WriteLine(expressoes.ExpressarSurpresa(10));    // "ahhhhhhhhh!"
Console.WriteLine(expressoes.ExpressarDecepcao(7));     // "ohhhhhhh!"
```

### Métodos Anônimos e Funções Lambda

Funções lambda (também chamadas de expressões lambda) são uma forma concisa de escrever métodos anônimos. Elas utilizam a sintaxe `=>` (lê-se "vai para" ou "retorna") para separar os parâmetros do corpo da função.

Exemplo básico:

```csharp
List<int> numeros = new List<int> { 1, 2, 3, 4, 5 };

// Usando uma função lambda com Select do LINQ
var quadrados = numeros.Select(n => n * n);
foreach (var q in quadrados) {
    Console.WriteLine(q);  // 1, 4, 9, 16, 25
}

// Lambda com múltiplas linhas
var resultado = numeros.Where(n => {
    bool ehPar = n % 2 == 0;
    return ehPar;
});
```

Lambdas também podem ser atribuídas a variáveis:

```csharp
Func<int, int> Quadrado = n => n * n;
Console.WriteLine(Quadrado(5));  // 25

Action<string> ImprimirMensagem = mensagem => Console.WriteLine(mensagem);
ImprimirMensagem("Olá, mundo!");  // "Olá, mundo!"
```

Exemplo mais complexo com métodos:

```csharp
List<string> palavras = new List<string> { "carro", "coração", "homem", "animal", "flor", "luz" };

// Usando lambda para pluralizar palavras
var pluralizadas = palavras.Select(palavra => {
    if (palavra.EndsWith("s")) return palavra;
    if (palavra.EndsWith("ão")) return palavra[..^2] + "ões";
    if (palavra.EndsWith("m")) return palavra[..^1] + "ns";
    if (palavra.EndsWith("l")) return palavra[..^1] + "is";
    if (palavra.EndsWith("r") || palavra.EndsWith("z")) return palavra + "es";
    return palavra + "s";
});

foreach (var p in pluralizadas) {
    Console.WriteLine(p);  // carros, corações, homens, animais, flores, luzes
}
```


## Programação Modular

Um módulo pode ser minúsculo como um método reutilizável, ou um grupo de métodos relacionados (coesos) escritos em uma classe, ou um conjunto de classes formando um namespace, ou até uma biblioteca completa (conjunto de projetos compilados em um assembly).

Resumindo, um módulo deve ter as seguintes características:

- **Encapsulamento**: Um módulo deve ocultar seus detalhes internos e expor apenas o necessário através de uma interface pública.
- **Coesão**: As funcionalidades dentro de um módulo devem estar relacionadas e focadas em uma única responsabilidade.
- **Baixo Acoplamento**: Um módulo deve ser o mais independente possível de outros módulos.
- **Reutilização**: Módulos bem projetados podem ser reutilizados em diferentes partes do sistema.
- **Manutenção Facilitada**: A modularidade facilita a manutenção e atualização do software.

### Projetos C#

Um projeto C# é um conjunto de arquivos organizados logicamente para desenvolver uma aplicação. Projetos modernos em C# utilizam o formato `.csproj` (C# Project File) que é baseado em XML. Os projetos podem referenciar outras bibliotecas (assemblies) através de pacotes NuGet ou referências diretas.

Para criar um novo projeto C#:

```bash
dotnet new console -n MeuProjetoCSharp
cd MeuProjetoCSharp
```

O arquivo `MeuProjetoCSharp.csproj` contém a configuração do projeto:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net8.0</TargetFramework>
    <LangVersion>latest</LangVersion>
  </PropertyGroup>
</Project>
```

Para instalar um pacote NuGet:

```bash
dotnet add package NomeDoPacote
```

Para executar o projeto:

```bash
dotnet run
```

### Programação Modular em C#

Em C#, a modularidade é alcançada através de namespaces, classes, interfaces e access modifiers. Cada classe pode encapsular dados (propriedades) e comportamentos (métodos), e os modificadores de acesso controlam o que é visível externamente.

Exemplo de uma classe bem encapsulada:

```csharp
// arquivo: Horario.cs
namespace MeuProjetoCSharp;

/// <summary>
/// Representa um horário de 00:00:00 a 23:59:59
/// </summary>
public class Horario {
    private int segundos = 0;  // atributo privado (encapsulado)

    public Horario(int horas = 0, int minutos = 0, int segundos = 0) {
        if (horas < 0 || horas > 23 || minutos < 0 || minutos > 59 || segundos < 0 || segundos > 59) {
            throw new ArgumentException("Valores de hora, minuto ou segundo inválidos.");
        }
        this.segundos = (horas * 3600 + minutos * 60 + segundos) % 86400;
    }

    public int Horas => this.segundos / 3600;
    public int Minutos => (this.segundos % 3600) / 60;
    public int Segundos => this.segundos % 60;

    public void AdicionaSegundos(int segundos) {
        this.segundos = (this.segundos + segundos) % 86400;
    }

    public void AdicionaMinutos(int minutos) {
        this.segundos = (this.segundos + minutos * 60) % 86400;
    }

    public void AdicionaHoras(int horas) {
        this.segundos = (this.segundos + horas * 3600) % 86400;
    }

    public override string ToString() {
        return $"{Pad(Horas)}:{Pad(Minutos)}:{Pad(Segundos)}";
    }

    private string Pad(int valor) {
        return valor < 10 ? $"0{valor}" : $"{valor}";
    }
}

// arquivo: Program.cs
var h = new Horario(13, 55, 34);
Console.WriteLine($"{h.Horas}, {h.Minutos}, {h.Segundos}");  // 13, 55, 34
h.AdicionaSegundos(3);
Console.WriteLine($"{h.Horas}, {h.Minutos}, {h.Segundos}");  // 13, 55, 37
h.AdicionaMinutos(30);
Console.WriteLine($"{h.Horas}, {h.Minutos}, {h.Segundos}");  // 14, 25, 37
h.AdicionaHoras(13);
Console.WriteLine($"{h.Horas}, {h.Minutos}, {h.Segundos}");  // 3, 25, 37
Console.WriteLine(h.ToString());  // 03:25:37
```

### Biblioteca Padrão do C#

A Biblioteca Padrão do C# (Base Class Library) fornece uma extensa coleção de tipos e funcionalidades, incluindo:

- `System`: Tipos fundamentais como `Object`, `String`, `Int32`, etc.
- `System.Collections`: Coleções como `List<T>`, `Dictionary<TKey, TValue>`, etc.
- `System.Linq`: Language Integrated Query para manipulação de dados.
- `System.IO`: Operações de arquivo e fluxo de dados.
- `System.Net`: Funcionalidades de rede.
- `System.Text`: Manipulação de strings e codificação.

Operações comuns com strings:

```csharp
string texto = "Olá, mundo!";
Console.WriteLine(texto.Length);                    // 13
Console.WriteLine(texto.ToUpper());                 // "OLÁ, MUNDO!"
Console.WriteLine(texto.ToLower());                 // "olá, mundo!"
Console.WriteLine(texto.IndexOf("mundo"));          // 5
Console.WriteLine(texto.Replace("mundo", "C#"));    // "Olá, C#!"
string[] palavras = texto.Split(", ");              // ["Olá", "mundo!"]
Console.WriteLine(texto.Substring(0, 5));           // "Olá, "
Console.WriteLine(texto.Trim());                    // "Olá, mundo!"
Console.WriteLine(texto.EndsWith("!"));             // true
```

Operações com listas:

```csharp
List<string> frutas = new List<string> { "maçã", "banana", "laranja" };
frutas.Add("uva");
Console.WriteLine(string.Join(", ", frutas));  // "maçã, banana, laranja, uva"

frutas.RemoveAt(frutas.Count - 1);  // remove o último elemento
Console.WriteLine(frutas.IndexOf("banana"));    // 1

List<string> subLista = frutas.GetRange(0, 2); // pega os primeiros 2
foreach (var fruta in subLista) {
    Console.WriteLine(fruta);
}
```


## Estruturas de Dados em C#

Estruturas de dados são formas específicas de organizar e armazenar dados na memória do computador. C# fornece várias estruturas de dados integradas e permite criar estruturas customizadas.

### Estruturas de Dados Elementares

#### Tipos de Valor em C#

C# oferece tipos de valor primitivos e tipos de valor customizados (structs):

```csharp
// Tipos primitivos
int numero = 42;
double valor = 3.14;
decimal dinheiro = 19.95m;
bool condicao = true;
char letra = 'A';

// Tipos de valor customizados (structs)
public struct Ponto {
    public int X { get; set; }
    public int Y { get; set; }
    
    public Ponto(int x, int y) {
        X = x;
        Y = y;
    }
}

var ponto = new Ponto(10, 20);
Console.WriteLine($"X: {ponto.X}, Y: {ponto.Y}");
```

#### Classes e Objetos em C#

C# é uma linguagem orientada a objetos. Classes definem tipos customizados que combinam dados (propriedades) e comportamento (métodos):

```csharp
public class Pessoa {
    public string Nome { get; set; }
    public int Idade { get; set; }
    
    public Pessoa(string nome, int idade) {
        Nome = nome;
        Idade = idade;
    }
    
    public void Saudacao() {
        Console.WriteLine($"Olá, meu nome é {Nome} e tenho {Idade} anos.");
    }
}

var pessoa = new Pessoa("João Silva", 30);
pessoa.Saudacao();  // "Olá, meu nome é João Silva e tenho 30 anos."
```

#### Listas e Coleções

C# oferece a classe genérica `List<T>` para armazenar coleções de elementos do mesmo tipo:

```csharp
List<string> nomes = new List<string> { "Ana", "Bruno", "Carlos", "Daniela" };
Console.WriteLine(nomes[0]);          // "Ana"
Console.WriteLine(nomes.Count);       // 4
Console.WriteLine(nomes[nomes.Count - 1]);  // "Daniela"

// Adicionando elementos
nomes.Add("Eduardo");
Console.WriteLine(string.Join(", ", nomes));

// Removendo elementos
nomes.Remove("Bruno");
Console.WriteLine(string.Join(", ", nomes));
```

#### Conjuntos

C# oferece a classe genérica `HashSet<T>` para armazenar coleções de valores únicos:

```csharp
HashSet<string> estados = new HashSet<string> { "RS", "SC", "MG" };
estados.Add("RS");  // será ignorado (duplicata)
Console.WriteLine(estados.Count);  // 3

foreach (var estado in estados) {
    Console.WriteLine(estado);
}

Console.WriteLine(estados.Contains("SC"));  // true
```

#### Dicionários

C# oferece a classe genérica `Dictionary<TKey, TValue>` para armazenar pares chave-valor:

```csharp
Dictionary<string, int> idades = new Dictionary<string, int> {
    { "João Silva", 30 },
    { "Ana Maria", 25 },
    { "Carlos Souza", 35 }
};

Console.WriteLine(idades["João Silva"]);  // 30
Console.WriteLine(idades["Ana Maria"]);   // 25

foreach (var par in idades) {
    Console.WriteLine($"{par.Key}: {par.Value} anos");
}
```

### Estruturas de Dados Compostas

Estruturas compostas combinam várias estruturas elementares:

```csharp
// Array de Objetos
Pessoa[] pessoas = new[] {
    new Pessoa("João Silva", 30),
    new Pessoa("Ana Maria", 25),
    new Pessoa("Carlos Souza", 35)
};

// List de objetos
List<Pessoa> listaPessoas = new List<Pessoa>(pessoas);

// Dictionary com tipos complexos
Dictionary<int, Pessoa> pessoasId = new Dictionary<int, Pessoa> {
    { 1, new Pessoa("João Silva", 30) },
    { 2, new Pessoa("Ana Maria", 25) }
};
```

### Registros em C#

C# 9.0 introduziu registros (records) que são tipos de referência otimizados para dados imutáveis:

```csharp
public record Pessoa(string Nome, int Idade);

var pessoa1 = new Pessoa("João", 30);
var pessoa2 = new Pessoa("João", 30);

Console.WriteLine(pessoa1 == pessoa2);  // true (igualdade estrutural)
Console.WriteLine($"{pessoa1.Nome}, {pessoa1.Idade}");  // João, 30
```

Registros são especialmente úteis para Data Transfer Objects (DTOs) e valores imutáveis.


## Considerações Finais

Este guia abordou os conceitos fundamentais de programação com C#. C# é uma linguagem moderna, fortemente tipada e estática, que oferece segurança em tempo de compilação, melhor desempenho e suporte superior do IDE em comparação com linguagens dinamicamente tipadas como JavaScript.

A tipagem estática e forte em C# força o programador a ser explícito sobre os tipos, o que reduz erros em tempo de execução e melhora a documentação implícita do código. Embora isso adicione complexidade no início, os benefícios a longo prazo em termos de manutenibilidade e confiabilidade são significativos.

É recomendado que qualquer programador moderno domine pelo menos uma linguagem dinâmica (como JavaScript, Python ou Ruby) e uma linguagem estática (como C#, TypeScript, Java ou Rust), para compreender as diferenças entre os paradigmas e estilos de programação.

C# continua evoluindo com novas versões lançadas anualmente, trazendo recursos modernos como nullable reference types, pattern matching, records e muito mais. A plataforma .NET, na qual C# é executado, oferece um ecossistema robusto e multiplataforma para desenvolvimento de aplicações empresariais, web, mobile e jogos.
