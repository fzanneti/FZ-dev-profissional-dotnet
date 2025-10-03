# ![Badge](https://img.shields.io/badge/1._Sintaxe_do_C%23_e_Conceitos_Fundamentais-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/1.1._Tipos_de_Dados-blue?style=for-the-badge&logo=c-sharp&logoColor=white) 
[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![Autor](https://img.shields.io/badge/Autor-Fabio%20Zanneti%20da%20Silva-black?style=flat-square&logo=github)
![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-C%23-blue)
![Ambiente](https://img.shields.io/badge/Ambiente-.NET-blue)
[![C# / .NET](https://img.shields.io/badge/🔗%20C%23‑.NET-Visite-blue)](https://dotnet.microsoft.com/pt-br/languages/csharp)
[![Documentação do C#](https://img.shields.io/badge/🔗%20C%23-Documentação-blue?logo=c-sharp&logoColor=white)](https://learn.microsoft.com/pt-br/dotnet/csharp/)
[![Wex - End to End Engineering](https://img.shields.io/badge/🔗%20DIO%20Repositório%20FZ-WEX%20E2E%20C%23-ff0000?logo=c-sharp&logoColor=white)](https://github.com/fzanneti/DIO-wex-e2e-csharp)

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/README.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/02declaracao-de-variaveis.md)

---

**O que são tipos de dados?** 

Tipos de dados definem que tipo de informação uma variável pode armazenar. Eles são a base de qualquer linguagem de programação.

**Tabela comparativa de tipos**

|**Nome**|**Descrição**|**Exemplo de valor**|
|:---:|:---:|:---:|
|`int`|Números inteiros|`42`|
|`double`|Números decimais (com ponto)|`3.14`|
|`decimal`|Números decimais (alta precisão, ponto fixo)|`3.14m`|
|`bool`|Verdadeiro ou falso|`true`|
|`char`|Um único caractere|`'A'`|
|`string`|Texto (sequência de caracteres)|`"Olá mundo"`|
|`var`|Tipo inferido pelo compilador|`var idade = 20;`|

---

### 1️⃣ `int`:
- Tipo numérico inteiro
- **Tamanho:** 32 bits (4 bytes)
- **Valores:** -2.147.483.648 a 2.147.483.647
- **Uso:** 
    1. Contadores
    2. IDs
    3. Números inteiros

**🧠 Exemplo de dados `int` (Inteiro):**

```csharp

int idade = 44;
int quantidade = 100;

```

---

### 2️⃣ `string`:
- **O que é?:** Sequência de caracteres Unicode, ou seja, uma série de símbolos ou letras que podem ser representados num sistema de codificação universal, onde cada símbolo recebe um número único (ponto de código) para ser identificado em diferentes plataformas. O padrão Unicode permite que computadores manipulem textos de vários idiomas e scripts, como letras, números, pontuações e emojis, usando um único arquivo binário para representar qualquer caractere.
- **Tamanho:** Variável (pode ser muito grande)
- **Valores:** Texto entre aspas duplas
- **Uso:**
    1. Nomes
    2. Mensagens
    3. Textos

**🧠 Exemplo de dados `string`:**

```csharp

string nome = "Fabio";
string sobrenome = "Zanneti";
string mensagem = "Olá, mundo!";

```

---

### 3️⃣ `bool` (Booleano): 
- **O que é?:** Valor lógico verdadeiro/falso, ou seja, é um tipo de dado lógico que só pode ter dois valores: `Verdadeiro` ou `Falso`. Esse tipo de dado é fundamental na lógica e na ciência da computação, sendo utilizado em expressões que avaliam condições e controlam o fluxo de execução de programas, como em estruturas `if` e `while`.
- **Tamanho:** 1 bit (mas ocupa 1 byte na memória)
- **Valores:** `true` ou `false`
- **Uso:**
    1. Condições
    2. Flags lógicas

**🧠 Exemplo de dados `bool`:**

```csharp

bool estaAtivo = true;
bool temPermissao = false;

```

---

### 4️⃣ `double` (Ponto flutuante):
- **O que é?:** Número de ponto flutuante de precisão dupla, ou seja, é um tipo de dado que armazena números decimais (não inteiros) utilizando 64 bits de memória. Isso permite que ele represente uma gama mais ampla e com maior precisão os números do que um tipo float de precisão simples (que usa 32 bits), sendo ideal para cálculos científicos, simulações complexas e aplicações financeiras que exigem alta exatidão.
- **Tamanho:** 64 bits (8 bytes)
- **Valores:** ±5.0 × 10⁻³²⁴ a ±1.7 × 10³⁰⁸
- **Uso:**
    1. Valores decimais
    2. Cálculos científicos

**🧠 Exemplo de dados `double`:**

```csharp

double preco = 19.99;
double pi = 3.1415926535;

```

---

### 5️⃣ `decimal` (Alta precisão para valores decimais):
- **O que é?:** Tipo de dado numérico de ponto fixo com alta precisão, utilizado principalmente para cálculos financeiros e monetários. Ele armazena números decimais com **28 a 29 dígitos significativos**, evitando erros de arredondamento comuns em tipos de ponto flutuante como `double`. Ideal quando a exatidão é mais importante que a performance.

- **Tamanho:** 128 bits (16 bytes)
- **Valores:** ±1.0 × 10⁻²⁸ a ±7.9 × 10²⁸
- **Uso:**
    1. Valores monetários
    2. Cálculos financeiros precisos
    3. Situações em que erros de arredondamento devem ser evitados

**🧠 Exemplo de dados `decimal`:**

```csharp

decimal salario = 12345.67m;
decimal juros = 0.015m;

```

> **Nota:** É necessário usar o sufixo `m` (ou `M`) para indicar que o número é do tipo `decimal`.

---

### 6️⃣ `char` (Caractere): 
- **O que é?:** Um único caractere Unicode, ou seja, uma unidade fundamental de texto que representa um símbolo único, como uma letra, um número ou um sinal, padronizado pelo padrão Unicode. Em termos práticos, é o menor "pedaço" de texto que um computador pode manipular. O Unicode atribui um valor numérico único a cada caractere, conhecido como ponto de código, para que diferentes sistemas e idiomas possam representá-los de forma consistente.
- **Tamanho:** 16 bits (2 bytes)
- **Valores:** Caractere entre aspas simples
- **Uso:**
    1. Caracteres individuais

**🧠 Exemplo de dados `char`:**

```csharp

char letra = 'A';
char simbolo = '$';

```

---

### 7️⃣ `var` (Inferência de Tipo): 
- **O que é?:** Não é um tipo, mas uma palavra-chave para inferência de tipo, ou seja, é a capacidade de um compilador ou interpretador de deduzir automaticamente o tipo de uma variável ou expressão sem que o programador precise declará-lo explicitamente. Em vez de escrever `<string> minhavariavel = "hello"`, o código se torna `<var> minhavariavel = "hello"`, onde o compilador infere que `minhavariavel` é do tipo `string`. Isso torna o código mais conciso e legível, sendo uma técnica comum em linguagens de programação modernas.
- **Uso:**
    1. O compilador determina o tipo automaticamente
- **Vantagem:** Código mais limpo, mas o tipo é definido em tempo de compilação

**🧠 Exemplo de dados `var`:**

```csharp

var nome = "Maria";      // string
var idade = 30;          // int
var salario = 2550.00;   // double
var ativo = true;        // bool

```

---

### Resumo Prático:

- Use `int` para números inteiros
- Use `string` para textos
- Use `bool` para verdadeiro/falso
- Use `double` para números com casas decimais (comuns, como em cálculos científicos)
- Use `decimal` para números decimais que exigem **alta precisão**, como em cálculos **financeiros e monetários**
- Use `char` para caracteres únicos
- Use `var` quando o tipo for óbvio pelo valor atribuído

> O `decimal` é ideal quando **precisão nos valores decimais** é essencial, como em operações com dinheiro (ex: salários, impostos, juros). Deve ser usado com o sufixo `m` (ex: `199.99m`).

> O `var` é especialmente útil em consultas **LINQ** que são uma forma integrada à linguagem de consultar diversas fontes de dados (como coleções de objetos em memória, bancos de dados e XML) diretamente no código .NET (C# e Visual Basic), oferecendo uma sintaxe declarativa, similar à SQL, para filtrar, ordenar e agrupar dados de maneira eficiente e padronizada, e quando os nomes de tipos são longos. **Sempre inicialize variáveis** `var` na declaração.

---

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/README.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/02declaracao-de-variaveis.md)

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)