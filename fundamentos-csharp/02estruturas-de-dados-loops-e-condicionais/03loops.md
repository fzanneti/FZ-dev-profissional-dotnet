# ![Badge](https://img.shields.io/badge/2._Estruturas_de_Dados%2c_Loops_e_Condicionais-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/2.3._Loops-blue?style=for-the-badge&logo=c-sharp&logoColor=white)
[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![Autor](https://img.shields.io/badge/Autor-Fabio%20Zanneti%20da%20Silva-blue?style=flat-square&logo=github)
![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Ambiente](https://img.shields.io/badge/Ambiente-.NET-52057b)
![Linguagem](https://img.shields.io/badge/Linguagem-C%23-52057b)
[![C# / .NET](https://img.shields.io/badge/🔗%20C%23‑.NET-Visite-52057b)](https://dotnet.microsoft.com/pt-br/languages/csharp)
[![Documentação do C#](https://img.shields.io/badge/🔗%20C%23-Documentação-52057b?logo=c-sharp&logoColor=white)](https://learn.microsoft.com/pt-br/dotnet/csharp/)
[![freeCodeCamp](https://img.shields.io/badge/freeCodeCamp-Português-00cbcc?logo=freecodecamp&logoColor=white)](https://www.freecodecamp.org/portuguese/)
[![Wex - End to End Engineering](https://img.shields.io/badge/🔗%20DIO%20Repositório%20FZ-WEX%20E2E%20C%23-00cbcc?logo=c-sharp&logoColor=white)](https://github.com/fzanneti/DIO-wex-e2e-csharp)

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/02estruturas-de-dados-loops-e-condicionais/02condicionais.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/03poo-classes-heran%C3%A7a-polimorfismo/01classe.md)

---

**O que são loops?**

Imagine que você precisa repetir uma tarefa várias vezes. Em vez de escrever o mesmo código repetidamente, você pode usar um "loop" (laço de repetição). Loops são estruturas que executam um bloco de código enquanto uma determinada condição for verdadeira.

---

### 1️⃣ - Loop `for`

O `for` é ideal quando você sabe exatamente quantas vezes deseja repetir uma ação. Ele é composto por três partes:

🔹 **Inicialização:** Onde você declara e inicializa uma variável de controle (geralmente chamada de `i`).      
🔹 **Condição:** A condição que será verificada antes de cada repetição. O loop continuará enquanto a condição for verdadeira.      
🔹 **Incremento/Decremento:** O que acontece com a variável de controle após cada repetição.

**🧠 Exemplo:**

```csharp

for (int i = 0; i < 5; i++)
{
    Console.WriteLine("Olá, mundo!");
}

```

> Neste exemplo, o código imprimirá `"Olá, mundo!"` cinco vezes.

**Saída no console:**

```bash

Olá, mundo!
Olá, mundo!
Olá, mundo!
Olá, mundo!
Olá, mundo!

```

---

### 2️⃣ - Loop `while`

O `while` é usado quando você não sabe quantas vezes precisa repetir uma ação, mas sabe a condição que deve ser satisfeita para continuar.

**🧠 Exemplo:**

```csharp

int i = 0;
while (i < 5)
{
    Console.WriteLine("O valor de i é: " + i);
    i++;
}

```

> Este código fará o mesmo que o exemplo do `for`, mas a estrutura é um pouco diferente. O `while` verifica a condição antes de executar o bloco de código.

**Saída no console:**

```bash

O valor de i é: 0
O valor de i é: 1
O valor de i é: 2
O valor de i é: 3
O valor de i é: 4

```

---

### 3️⃣ - Loop `foreach`

O `foreach` é a forma mais simples de percorrer os elementos de uma coleção, como uma lista ou um array.

**🧠 Exemplo:**

```csharp

string[] frutas = { "Maçã", "Banana", "Laranja", "Pêra" };

foreach (string fruta in frutas)
{
    Console.WriteLine(fruta);
}

```

> Este código irá percorrer o array `frutas` e imprimir cada um dos seus elementos.

**Saída no console:**

```bash

Maçã
Banana
Laranja
Pêra

```

---

**Quando usar cada um?**

🔹 **`for`:** Quando você sabe o número de repetições.      
🔹 **`while`:** Quando você não sabe o número de repetições, mas sabe a condição de parada.    
🔹 **`foreach`:** Quando você precisa percorrer todos os elementos de uma coleção.    

---

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/02estruturas-de-dados-loops-e-condicionais/02condicionais.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/03poo-classes-heran%C3%A7a-polimorfismo/01classe.md)

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)