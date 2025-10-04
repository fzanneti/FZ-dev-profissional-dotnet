# ![Badge](https://img.shields.io/badge/1._Sintaxe_do_C%23_e_Conceitos_Fundamentais-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/1.1._Tipos_de_Dados-blue?style=for-the-badge&logo=c-sharp&logoColor=white) 
[![Microsoft Learn - Treinamentos](https://img.shields.io/badge/🔗%20Microsoft_Learn-Treinamentos-blue?logo=microsoft&logoColor=white&style=for-the-badge)](https://learn.microsoft.com/pt-br/training/)
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

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/01tipos-de-dados.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/03operadores.md)

---

**Declaração de variáveis em C#: O fundamento de tudo**

Pense em uma variável como uma "caixa" na memória do computador, etiquetada com um nome, que guarda um tipo específico de informação (um número, um texto, uma data, etc.). Declarar uma variável é o ato de criar essa caixa, definir seu nome e o tipo de dado que ela pode armazenar.

**Em C#, a estrutura para declarar uma variável é simples e segue o padrão:**

`tipo_de_dado nome_da_variavel;`

**Ou, de forma mais completa, inicializando-a com um valor:**

`tipo_de_dado nome_da_variavel = valor_inicial;`

> *Vamos detalhar os componentes e ver exemplos práticos.*

---

### 1️⃣ Nome da variável (A etiqueta da caixa)

**O nome que você dá à variável é o seu identificador. Boas práticas de nomenclatura são essenciais para um código limpo e legível. Em C#:**

- **Padrão:** Use `camelCase`. A primeira palavra começa com letra minúscula e as subsequentes com maiúscula.
    - **Correto:** `nomeCompleto`, `totalDeVendas`, `usuarioLogado`.
    - **Incorreto:** `NomeCompleto`, `total\_de\_vendas`.
- **Clareza:** O nome deve descrever o propósito da variável. 
               `idade` é melhor que `i`.        
               `clienteEmail` é melhor que `cEmail`.
- **Regras:** Não pode começar com número e não pode conter espaços ou caracteres especiais (exceto `_`).

**🧠 Exemplo:** 

Vamos ver como isso funciona em um pequeno trecho de uma aplicação de console em C#.

```csharp

using System;

class Program
{
    static void Main(string[] args)
    {
        // --- Declaração de Variáveis ---

        // 1. Declarando e inicializando na mesma linha (prática mais comum)
        string nomeProduto = "Café Especial";
        int quantidadeEmEstoque = 150;
        double precoUnitario = 12.50;
        bool produtoDisponivel = true;

        // 2. Apenas declarando e inicializando depois
        decimal valorTotalEstoque; // A variável foi criada, mas não tem valor definido ainda.
        
        // Agora, calculamos e atribuímos o valor
        valorTotalEstoque = quantidadeEmEstoque * (decimal)precoUnitario; // Precisamos converter (cast) para decimal para a operação

        // --- Utilizando as Variáveis ---

        Console.WriteLine("--- Detalhes do Produto ---");
        Console.WriteLine($"Nome: {nomeProduto}"); // Interpolação de string, a forma moderna de formatar
        Console.WriteLine($"Preço por unidade: R$ {precoUnitario}");
        Console.WriteLine($"Quantidade: {quantidadeEmEstoque}");
        Console.WriteLine($"Disponível? {produtoDisponivel}");
        
        Console.WriteLine("---------------------------");
        Console.WriteLine($"Valor total em estoque: {valorTotalEstoque:C}"); // O formatador :C transforma para o formato de moeda local
    }
}

```

**Saída do Programa:**

```bash

--- Detalhes do Produto ---
Nome: Café Especial
Preço por unidade: R$ 12,5
Quantidade: 150
Disponível? True
---------------------------
Valor total em estoque: R$ 1.875,00

```

---

### 2️⃣ Inferência de tipo com `var` (Uma forma mais concisa)

A partir do C# 3.0, você pode usar a palavra-chave `var`. Ao usar `var`, você pede ao compilador para inferir (descobrir) o tipo da variável com base no valor que você está atribuindo a ela.

**Regras para usar `var`:**

- Você deve inicializar a variável na mesma linha da declaração.
- É apenas um "açúcar sintático" para o desenvolvedor. Após a compilação, a variável terá um tipo forte definido, exatamente como se você o tivesse escrito.

**🧠 Exemplo com `var`:**

```csharp

// O compilador entende que 'nome' é uma string
var nome = "Maria Souza"; 

// O compilador entende que 'idade' é um int
var idade = 42; 

// O compilador entende que 'compraAprovada' é um bool
var compraAprovada = false;

// ISSO GERA UM ERRO DE COMPILAÇÃO!
// var email; // Erro: Variáveis declaradas com 'var' devem ser inicializadas.

```

> **Quando usar `var`?** Use quando o tipo da variável for óbvio pelo lado direito da atribuição, tornando o código mais limpo. Por exemplo, `var cliente = new Cliente();` é mais limpo que `Cliente cliente = new Cliente();`.

---

### Resumo Prático:

- **Sempre especifique o tipo:** Seja explicitamente (`int`, `string`) ou implicitamente (`var`), toda variável em C# tem um tipo definido.
- **Inicialize suas variáveis:** Evite usar variáveis que não receberam um valor inicial. O compilador C# é inteligente e muitas vezes o alertará sobre isso para prevenir erros em tempo de execução.
- **Use nomes claros e o padrão `camelCase`:** Seu "eu do futuro" e seus colegas de equipe agradecerão.
- **Escolha o tipo certo para o trabalho:** Usar `decimal` para dinheiro e `int` para contagens simples não é apenas uma boa prática, é fundamental para a precisão e performance da sua aplicação .NET.

---

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/01tipos-de-dados.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/main/fundamentos-csharp/01sintaxe-do-Csharp-e-conceitos-fundamentais/03operadores.md)

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯*C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)