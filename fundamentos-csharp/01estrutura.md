# Estudos em C# e .NET

![Badge](https://img.shields.io/badge/Fabio%20Zanneti%20da%20Silva-Profissional-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/1._Estrutura_C%23-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-CSharp-black)
![Autor](https://img.shields.io/badge/Autor-fzanneti-black?style=flat-square&logo=github)

---

### Sintaxe do C# e Conceitos Fundamentais:

<img src="" alt="Banner" width="600px"/>

**Um programa básico em C# é organizado da seguinte forma:**

1️⃣ `using;`: a palavra-chave `using` é uma diretiva fundamental com três propósitos principais, todos com o objetivo de tornar o código mais limpo, legível e eficiente. Dominar os três usos da diretiva using é essencial para qualquer desenvolvedor .NET/C# que preze por escrever código limpo, seguro e de fácil manutenção.

**Vamos analisar cada um deles:**

🔵 `using` para importar `namespaces`:

Este é o uso mais comum e conhecido da diretiva `using`. Sua principal função é permitir que você utilize tipos (classes, structs, interfaces, etc.) de um determinado namespace sem a necessidade de escrever o nome completo do namespace toda vez.

---

💡 **Analogia:**

Imagine que cada `namespace` é uma pasta no seu computador e cada tipo é um arquivo dentro dessa pasta. Em vez de digitar o caminho completo do arquivo (`C:\Documentos\Relatorios\Vendas.docx`) toda vez que precisar dele, você pode simplesmente adicionar a pasta `C:\Documentos\Relatorios\` à sua área de trabalho. A partir daí, basta se referir a `Vendas.docx`. A diretiva `using` faz exatamente isso no C#.

---

🧠 **Exemplo:**    

> *Sem `using`*

```csharp

// Exemplo sem a diretiva using
// Note como o código fica verboso e repetitivo.
class Program
{
    static void Main(string[] args)
    {
        System.Console.WriteLine("Digite seu nome:");
        string nome = System.Console.ReadLine();
        System.Console.WriteLine($"Olá, {nome}!");

        // Usando uma lista
        System.Collections.Generic.List<string> nomes = new System.Collections.Generic.List<string>();
        nomes.Add("Ana");
        nomes.Add("Carlos");
    }
}

```

> *Com `using`*

Ao declarar `using System;` e `using System.Collections.Generic;` no topo do arquivo, o compilador já sabe onde procurar pelas classes `Console` e `List<T>`, tornando o código muito mais enxuto e legível.

```csharp

// Exemplo com a diretiva using
// O código fica mais limpo e direto.
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Digite seu nome:");
        string nome = Console.ReadLine();
        Console.WriteLine($"Olá, {nome}!");

        // Usando uma lista
        List<string> nomes = new List<string>();
        nomes.Add("Ana");
        nomes.Add("Carlos");
    }
}

```

---

🔵 `using` **como uma instrução para gerenciamento de recursos (**`IDisposable`**)**

O segundo uso da palavra-chave `using` é como uma instrução que garante a liberação correta de recursos. Certos objetos no **.NET**, como conexões de banco de dados, streams de arquivos, e objetos gráficos, gerenciam recursos não gerenciados (memória que não está sob o controle direto do **Garbage Collector (GC)** (processo automático de gerenciamento de memória que libera a memória ocupada por objetos que não estão mais sendo usados pela aplicação)).     
Esses objetos implementam a interface `IDisposable`, que possui um único método: `Dispose()`. A instrução `using` cria um escopo e, ao final desse escopo (seja por conclusão normal ou por uma exceção), o método `Dispose()` do objeto é chamado automaticamente. Isso previne vazamentos de memória e garante que os recursos sejam liberados o mais rápido possível.

---

🧠 **Exemplo:**

> Leitura de um arquivo

```csharp

using System;
using System.IO;

class LeituraArquivo
{
    public void LerConteudo(string caminho)
    {
        // A instrução 'using' garante que o StreamReader será fechado (Dispose() será chamado)
        // mesmo que ocorra um erro durante a leitura do arquivo.
        using (StreamReader leitor = new StreamReader(caminho))
        {
            string linha;
            while ((linha = leitor.ReadLine()) != null)
            {
                Console.WriteLine(linha);
            }
        } // O método leitor.Dispose() é chamado automaticamente aqui.
    }
}

```

> Este código é, na prática, uma forma mais elegante e segura de escrever o seguinte bloco `try-finally`:

``` csharp

// Equivalente manual sem a instrução 'using'
StreamReader leitor = null;
try
{
    leitor = new StreamReader("caminho/do/arquivo.txt");
    // ... lógica de leitura ...
}
finally
{
    if (leitor != null)
    {
        leitor.Dispose(); // Garante a liberação do recurso
    }
}

```

---

🔵 `using static` para importar membros estáticos

Introduzido no C# 6, o `using static` permite que você acesse membros estáticos (métodos, propriedades, campos) de uma classe diretamente, sem precisar qualificar com o nome da classe.      
Isso é particularmente útil para classes com muitos membros estáticos que você usa com frequência, como `System.Math`, `System.Console` ou classes de constantes.

---

🧠 **Exemplo:**

> *Sem `using static`*

``` csharp

using System;

class Calculadora
{
    public double CalcularAreaCirculo(double raio)
    {
        // Repetimos 'Math' várias vezes
        return Math.PI * Math.Pow(raio, 2);
    }

    public void Saudar()
    {
        // Usamos o nome da classe 'Console'
        Console.WriteLine("Cálculo finalizado.");
    }
}

```

> *Com `using static`*

O código se torna mais conciso, quase como se estivéssemos usando funções globais.

``` csharp

// Importamos todos os membros estáticos de System.Math e System.Console
using static System.Math;
using static System.Console;

class Calculadora
{
    public double CalcularAreaCirculo(double raio)
    {
        // PI e Pow podem ser chamados diretamente
        return PI * Pow(raio, 2);
    }

    public void Saudar()
    {
        // WriteLine pode ser chamado diretamente
        WriteLine("Cálculo finalizado.");
    }
}

```

> 🚨 **Cuidado:** Use `using static` com moderação. Importar membros estáticos de muitas classes pode poluir o escopo global e diminuir a legibilidade, tornando difícil identificar de qual classe um método se origina.

---

2️⃣ `namespace`: Um `namespace` (em português, "espaço de nomes") é um mecanismo fundamental no C# e em toda a plataforma .NET para **organizar e agrupar código relacionado**, além de **prevenir conflitos de nomes**.    
Pense nele como um sobrenome para suas classes, interfaces, structs e outros tipos.

---

💡 **Analogia:**

Em uma cidade, podem existir duas pessoas chamadas "João". Para diferenciá-las, usamos seus sobrenomes: "João Silva" e "João Souza". No C#, se você tiver duas classes chamadas `Cliente`, os namespaces atuariam como esses sobrenomes, permitindo que o compilador saiba exatamente a qual delas você se refere: `Vendas.Cliente` e `Marketing.Cliente`.

---

**Os principais objetivos de um `namespace` são:**

🔹 **Organização:** Agrupar código com funcionalidades relacionadas. Por exemplo, todas as classes que lidam com acesso a dados podem ficar no namespace MeuProjeto.Data, enquanto as classes da interface do usuário ficariam em MeuProjeto.UI. Isso torna o projeto mais fácil de navegar e entender.      
🔹 **Prevenção de Colisões:** Evitar que duas classes com o mesmo nome entrem em conflito. Isso é crucial em projetos grandes ou ao usar bibliotecas de terceiros, que podem ter classes com nomes iguais às suas.      
🔹 **Controle de Acesso e Escopo:** Definir um escopo para os tipos, ajudando a controlar o que é visível e acessível para outras partes do seu programa.    

---

🧠 **Exemplo:**

Vamos ver como isso funciona na prática.

**Imagine que estamos construindo um sistema de e-commerce. Podemos organizar nossas classes da seguinte forma:**

📄 **Arquivo 1:** Produto.cs
> Aqui, definimos as classes relacionadas aos produtos e ao inventário dentro do `namespace` `Ecommerce.Modelos`.

```csharp

namespace Ecommerce.Modelos
{
    public class Produto
    {
        public int Id { get; set; }
        public string Nome { get; set; }
        public decimal Preco { get; set; }
    }

    public class Inventario
    {
        public int QuantidadeEmEstoque { get; set; }
    }
}

```

---

📄 **Arquivo 2:** Pedido.cs
> Agora, criamos uma classe `Pedido` que precisa utilizar a classe `Produto`. Para isso, usamos a diretiva `using` para "importar" tudo que está dentro do `namespace` `Ecommerce.Modelos`.

```csharp

// A diretiva 'using' nos dá acesso direto às classes do namespace Ecommerce.Modelos
using Ecommerce.Modelos;
using System.Collections.Generic;

namespace Ecommerce.Servicos
{
    public class Pedido
    {
        public int PedidoId { get; set; }
        public List<Produto> Itens { get; set; } // Podemos usar 'Produto' diretamente!
        public decimal ValorTotal { get; set; }

        public Pedido()
        {
            Itens = new List<Produto>();
        }
    }
}

```

💡 **Sem a diretiva `using Ecommerce.Modelos;`, teríamos que escrever o nome completo (fully qualified name):**

```csharp

namespace Ecommerce.Servicos
{
    public class Pedido
    {
        // Código mais verboso sem a diretiva 'using'
        public System.Collections.Generic.List<Ecommerce.Modelos.Produto> Itens { get; set; }
    }
}

```

---

3. `class`: Declara uma classe, que é a principal unidade para encapsular funcionalidades em C#.
4. `static void Main(string[] args)`: O ponto de entrada principal do programa, onde a execução começa.
5. `Console.WriteLine("Hello, World!");`: Uma instrução que escreve "Hello, World!" no ecrã.
6. Ponto e vírgula `(;)`: Termina cada instrução C#.

---

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 Material de estudo: *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)