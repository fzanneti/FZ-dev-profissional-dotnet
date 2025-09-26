# Estudos em C# e .NET

![Badge](https://img.shields.io/badge/Fabio%20Zanneti%20da%20Silva-Profissional-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/1._Tipos_de_Dados-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-CSharp-black)
![Autor](https://img.shields.io/badge/Autor-fzanneti-black?style=flat-square&logo=github)

---

[Compilador Online](https://www.mycompiler.io/pt/new/csharp)

**O que são tipos de dados?**     
Tipos de dados definem que tipo de informação uma variável pode armazenar. Eles são a base de qualquer linguagem de programação.

**Tabela comparativa de tipos**

|**Nome**|**Descrição**|**Exemplo de valor**|**Termo técnico**|
|:---:|---|---|---|
|`int`|Números inteiros|`42`|Tipo de valor|
|`double`|Números decimais (com ponto)|`3.14`|Tipo de valor|
|`bool`|Verdadeiro ou falso|`true`|Tipo de valor|
|`char`|Um único caractere|`'A'`|Tipo de valor|
|`string`|Texto (sequência de caracteres)|`"Olá mundo"`|Tipo de referência|
|`var`|Tipo inferido pelo compilador|`var idade = 20;`|Tipo implícito|

### 1️⃣ `int`:
- Tipo numérico inteiro
- **Tamanho:** 32 bits (4 bytes)
- **Valores:** -2.147.483.648 a 2.147.483.647
- **Uso:** 
    1. Contadores
    2. IDs
    3. Números inteiros

**Exemplo de dados `int` (Inteiro):**

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

**Exemplo de dados `string`:**

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

**Exemplo de dados `bool`:**

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

**Exemplo de dados `double`:**

```csharp

double preco = 19.99;
double pi = 3.1415926535;

```


### 5️⃣ `char` (Caractere): 
- **O que é?:** Um único caractere Unicode, ou seja, uma unidade fundamental de texto que representa um símbolo único, como uma letra, um número ou um sinal, padronizado pelo padrão Unicode. Em termos práticos, é o menor "pedaço" de texto que um computador pode manipular. O Unicode atribui um valor numérico único a cada caractere, conhecido como ponto de código, para que diferentes sistemas e idiomas possam representá-los de forma consistente.
- **Tamanho:** 16 bits (2 bytes)
- **Valores:** Caractere entre aspas simples
- **Uso:**
    1. Caracteres individuais

**Exemplo de dados `char`:**

```csharp

char letra = 'A';
char simbolo = '$';

```

---

### 6️⃣ `var` (Inferência de Tipo): 
- **O que é?:** Não é um tipo, mas uma palavra-chave para inferência de tipo, ou seja, é a capacidade de um compilador ou interpretador de deduzir automaticamente o tipo de uma variável ou expressão sem que o programador precise declará-lo explicitamente. Em vez de escrever `<string> minhavariavel = "hello"`, o código se torna `<var> minhavariavel = "hello"`, onde o compilador infere que `minhavariavel` é do tipo `string`. Isso torna o código mais conciso e legível, sendo uma técnica comum em linguagens de programação modernas.
- **Uso:**
    1. O compilador determina o tipo automaticamente
- **Vantagem:** Código mais limpo, mas o tipo é definido em tempo de compilação

**Exemplo de dados `var`:**

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
- Use `double` para números com casas decimais
- Use `char` para caracteres únicos
- Use `var` quando o tipo for óbvio pelo valor atribuído

> O `var` é especialmente útil em consultas **LINQ** que são uma forma integrada à linguagem de consultar diversas fontes de dados (como coleções de objetos em memória, bancos de dados e XML) diretamente no código .NET (C# e Visual Basic), oferecendo uma sintaxe declarativa, similar à SQL, para filtrar, ordenar e agrupar dados de maneira eficiente e padronizada, e quando os nomes de tipos são longos. **Sempre inicialize variáveis** `var` na declaração.

---

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 Material de estudo: *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)