# Estudos em C# e .NET

![Badge](https://img.shields.io/badge/Fabio%20Zanneti%20da%20Silva-Profissional-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/4._Entrada_e_Saída-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-CSharp-black)
![Autor](https://img.shields.io/badge/Autor-fzanneti-black?style=flat-square&logo=github)

[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)

---

Bem-vindo à quarta parte do nosso guia definitivo de C# para iniciantes! Após aprendermos sobre variáveis, operadores e tipos de dados, é hora de dar um passo crucial: fazer nossos programas interagirem com o usuário. Nesta seção, vamos explorar como exibir informações na tela (saída) e como receber dados digitados pelo usuário (entrada).

**A porta de entrada e saída: O console**

Em nossas primeiras aplicações, o principal meio de comunicação será o `console`, também conhecido como terminal ou prompt de comando. É aquela tela de texto onde podemos executar comandos e ver os resultados de nossos programas. Em C#, a classe `Console` é a ferramenta fundamental para todas as operações de entrada e saída nesse ambiente.

---

### 1️⃣ Saída de dados: Mostrando informações na tela

Para que um programa seja útil, ele precisa, no mínimo, nos mostrar o que está fazendo ou qual foi o resultado de suas operações. Em C#, utilizamos principalmente dois métodos para "escrever" no console.

**`Console.WriteLine()`: Escrevendo com quebra de linha**  

O método `WriteLine()` exibe uma informação no console e, em seguida, move o cursor para a próxima linha. É como digitar algo e pressionar "Enter".

🧠 **Exemplo:** 

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

🧠 **Exemplo:**

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

🧠 **Exemplo:**

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

🧠 **Exemplo:**

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

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 Material de estudo: *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)