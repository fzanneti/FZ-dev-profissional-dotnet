# ![Badge](https://img.shields.io/badge/1._Sintaxe_do_C%23_e_Conceitos_Fundamentais-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/1.1._Tipos_de_Dados-blue?style=for-the-badge&logo=c-sharp&logoColor=white) 
[![Microsoft Learn - Treinamentos](https://img.shields.io/badge/🔗%20Microsoft_Learn-Treinamentos-blue?logo=microsoft&logoColor=white&style=for-the-badge)](https://learn.microsoft.com/pt-br/training/)
[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![Autor](https://img.shields.io/badge/Autor-Fabio%20Zanneti%20da%20Silva-blue?style=flat-square&logo=github)
![Ambiente](https://img.shields.io/badge/Ambiente-.NET-52057b)
![Linguagem](https://img.shields.io/badge/Linguagem-C%23-52057b)
[![Visual Studio Code](https://img.shields.io/badge/🔗%20Visual%20Studio%20Code-0078D7?logo=visualstudiocode&logoColor=white)](https://code.visualstudio.com/)
[![C# / .NET](https://img.shields.io/badge/🔗%20C%23‑.NET-Visite-52057b)](https://dotnet.microsoft.com/pt-br/languages/csharp)
[![Documentação do C#](https://img.shields.io/badge/🔗%20C%23-Documentação-52057b?logo=c-sharp&logoColor=white)](https://learn.microsoft.com/pt-br/dotnet/csharp/)
[![freeCodeCamp](https://img.shields.io/badge/🔗%20freeCodeCamp-Português-00cbcc?logo=freecodecamp&logoColor=white)](https://www.freecodecamp.org/portuguese/)
[![Wex - End to End Engineering](https://img.shields.io/badge/🔗%20DIO%20Repositório%20FZ-WEX%20E2E%20C%23-00cbcc?logo=c-sharp&logoColor=white)](https://github.com/fzanneti/DIO-wex-e2e-csharp)

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/03operadores.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/02estruturas-de-dados-loops-e-condicionais/01arrays-e-listas.md)

---

**A porta de entrada e saída: O console**

Em nossas primeiras aplicações, o principal meio de comunicação será o `console`, também conhecido como terminal ou prompt de comando. É aquela tela de texto onde podemos executar comandos e ver os resultados de nossos programas. Em C#, a classe `Console` é a ferramenta fundamental para todas as operações de entrada e saída nesse ambiente.

---

### 1️⃣ Saída de dados: Mostrando informações na tela

Para que um programa seja útil, ele precisa, no mínimo, nos mostrar o que está fazendo ou qual foi o resultado de suas operações. Em C#, utilizamos principalmente dois métodos para "escrever" no console.

**`Console.WriteLine()`: Escrevendo com quebra de linha**  

O método `WriteLine()` exibe uma informação no console e, em seguida, move o cursor para a próxima linha. É como digitar algo e pressionar "Enter".

**🧠 Exemplo:** 

```csharp

// Exibe uma mensagem de boas-vindas
Console.WriteLine("Olá, mundo!");

// Exibe a idade
Console.WriteLine("Eu tenho 44 anos.");

```

**Saída no Console:**

```bash

Olá, mundo!
Eu tenho 44 anos.

```

**`Console.Write()`: Escrevendo na mesma linha**

Diferente do `WriteLine()`, o método `Write()` exibe a informação e mantém o cursor na mesma linha, permitindo que a próxima saída de dados comece imediatamente após a anterior.

**🧠 Exemplo:**

```csharp

Console.Write("Meu nome é ");
Console.Write("Fabio");
Console.Write(" e estou aprendendo C#.");

```

**Saída no Console:**

```bash

Meu nome é Fabio e estou aprendendo C#.

```

---

### 2️⃣ Formatando a saída: Deixando as mensagens mais claras

Exibir texto puro é útil, mas frequentemente precisamos combinar textos com os valores armazenados em nossas variáveis. Existem duas maneiras principais de fazer isso.

**🔹 Concatenação de strings**

A forma mais tradicional é "somar" (concatenar) strings usando o operador `+`.

**🧠 Exemplo:**

```csharp

string nome = "Maria";
int idade = 25;

Console.WriteLine("A usuária " + nome + " tem " + idade + " anos de idade.");

```

**Saída no Console:**

```bash

A usuária Maria tem 25 anos de idade.

```

**🔹 Interpolação de strings (A forma moderna e recomendada)**

A interpolação de strings é uma maneira mais limpa, legível e eficiente de embutir expressões e variáveis dentro de uma string. Para usá-la, basta colocar um cifrão (`$`) antes das aspas da string e envolver as variáveis em chaves (`{}`).

**🧠 Exemplo:**

```csharp

string produto = "café";
double preco = 12.50;

Console.WriteLine($"O produto {produto} custa R$ {preco}.");

```

**Saída no Console:**

```bash

O produto café custa R$ 12.50.

```

> A interpolação é a abordagem preferida pela maioria dos desenvolvedores C# por sua clareza e simplicidade.

---

### 3️⃣ Entrada de dados: Recebendo informações do usuário

Agora vem a parte interativa: aprender a pausar o programa e esperar que o usuário digite algo.

**`Console.ReadLine()`: Lendo uma Linha de Texto**

O método `ReadLine()` faz exatamente o que o nome sugere, ele lê toda a sequência de caracteres que o usuário digita até que a tecla **Enter** seja pressionada.

> ⚠️ **Atenção:** Se o usuário digitar algo não numérico, essas conversões geram exceção. Para evitar isso, use:

```csharp

bool sucesso = int.TryParse(entrada, out int idade);
if (sucesso)
{
    Console.WriteLine($"Idade válida: {idade}");
}
else
{
    Console.WriteLine("Valor inválido!");
}


```

---

### 5️ Funções

**🔹 Conceito** 

Funções são blocos de código reutilizáveis que executam uma tarefa específica.

**🧠 Exemplo:**

```csharp

static void Saudacao()
{
    Console.WriteLine("Bem-vindo ao programa!");
}

// static → usada em contexto de console
// void → não retorna valor
// Saudacao → nome da função
// () → sem parâmetros


```

**Chamada da função:**

```csharp

static void Main(string[] args)
{
    Saudacao(); // Chamando a função
}


```

**Extensões com parâmetro e retorno:**

```csharp

static void Saudar(string nome)
{
    Console.WriteLine($"Olá, {nome}!");
}

static int Dobro(int numero)
{
    return numero * 2;
}


```

**🧠 Programa completo integrado:**

```csharp

using System;

class Programa
{
    static void Main(string[] args)
    {
        // Entrada
        Console.WriteLine("Digite seu nome:");
        string nome = Console.ReadLine();

        Console.WriteLine("Digite sua idade:");
        string entradaIdade = Console.ReadLine();

        // Conversão segura
        bool idadeValida = int.TryParse(entradaIdade, out int idade);

        if (!idadeValida)
        {
            Console.WriteLine("Idade inválida. Encerrando programa.");
            return;
        }

        // Saída com interpolação
        Console.WriteLine($"Olá, {nome}! Você tem {idade} anos.");

        // Operadores
        if (idade >= 18)
        {
            Console.WriteLine("Você é maior de idade.");
        }
        else
        {
            Console.WriteLine("Você é menor de idade.");
        }

        // Função com parâmetro
        Saudar(nome);

        // Função com retorno
        int idadeDobro = Dobro(idade);
        Console.WriteLine($"O dobro da sua idade é {idadeDobro}.");
    }

    static void Saudar(string nome)
    {
        Console.WriteLine($"Seja bem-vindo, {nome}!");
    }

    static int Dobro(int numero)
    {
        return numero * 2;
    }
}

```

---

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/03operadores.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/02estruturas-de-dados-loops-e-condicionais/01arrays-e-listas.md)

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯  *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)