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

### 1️⃣ `using;`:
a palavra-chave `using` é uma diretiva fundamental com três propósitos principais, todos com o objetivo de tornar o código mais limpo, legível e eficiente. Dominar os três usos da diretiva using é essencial para qualquer desenvolvedor .NET/C# que preze por escrever código limpo, seguro e de fácil manutenção.    
Vamos analisar cada um deles:

🔹 `using` para importar `namespaces`:

Este é o uso mais comum e conhecido da diretiva `using`. Sua principal função é permitir que você utilize tipos (classes, structs, interfaces, etc.) de um determinado namespace sem a necessidade de escrever o nome completo do namespace toda vez.

🧩 **Analogia:**

Imagine que cada `namespace` é uma pasta no seu computador e cada tipo é um arquivo dentro dessa pasta. Em vez de digitar o caminho completo do arquivo (`C:\Documentos\Relatorios\Vendas.docx`) toda vez que precisar dele, você pode simplesmente adicionar a pasta `C:\Documentos\Relatorios\` à sua área de trabalho. A partir daí, basta se referir a `Vendas.docx`. A diretiva `using` faz exatamente isso no C#.

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

🔹 `using` **como uma instrução para gerenciamento de recursos (**`IDisposable`**)**

O segundo uso da palavra-chave `using` é como uma instrução que garante a liberação correta de recursos. Certos objetos no **.NET**, como conexões de banco de dados, streams de arquivos, e objetos gráficos, gerenciam recursos não gerenciados (memória que não está sob o controle direto do **Garbage Collector (GC)** (processo automático de gerenciamento de memória que libera a memória ocupada por objetos que não estão mais sendo usados pela aplicação)).     
Esses objetos implementam a interface `IDisposable`, que possui um único método: `Dispose()`. A instrução `using` cria um escopo e, ao final desse escopo (seja por conclusão normal ou por uma exceção), o método `Dispose()` do objeto é chamado automaticamente. Isso previne vazamentos de memória e garante que os recursos sejam liberados o mais rápido possível.

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

🔹 `using static` para importar membros estáticos

Introduzido no C# 6, o `using static` permite que você acesse membros estáticos (métodos, propriedades, campos) de uma classe diretamente, sem precisar qualificar com o nome da classe.      
Isso é particularmente útil para classes com muitos membros estáticos que você usa com frequência, como `System.Math`, `System.Console` ou classes de constantes.

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

### 2️⃣ `namespace`: 
Um `namespace` (em português, "espaço de nomes") é um mecanismo fundamental no C# e em toda a plataforma .NET para **organizar e agrupar código relacionado**, além de **prevenir conflitos de nomes**, é a espinha dorsal da arquitetura de qualquer aplicação C# bem estruturada. Eles não são opcionais para projetos sérios; são uma ferramenta essencial para garantir que seu código seja modular, escalável e de fácil manutenção. Pense nele como um sobrenome para suas classes, interfaces, structs e outros tipos.

🧩 **Analogia:**

Em uma cidade, podem existir duas pessoas chamadas "João". Para diferenciá-las, usamos seus sobrenomes: "João Silva" e "João Souza". No C#, se você tiver duas classes chamadas `Cliente`, os namespaces atuariam como esses sobrenomes, permitindo que o compilador saiba exatamente a qual delas você se refere: `Vendas.Cliente` e `Marketing.Cliente`.

**Os principais objetivos de um `namespace` são:**

🔹 **Organização:** Agrupar código com funcionalidades relacionadas. Por exemplo, todas as classes que lidam com acesso a dados podem ficar no namespace MeuProjeto.Data, enquanto as classes da interface do usuário ficariam em MeuProjeto.UI. Isso torna o projeto mais fácil de navegar e entender.      
🔹 **Prevenção de Colisões:** Evitar que duas classes com o mesmo nome entrem em conflito. Isso é crucial em projetos grandes ou ao usar bibliotecas de terceiros, que podem ter classes com nomes iguais às suas.      
🔹 **Controle de Acesso e Escopo:** Definir um escopo para os tipos, ajudando a controlar o que é visível e acessível para outras partes do seu programa.

🧠 **Exemplo:**

Vamos ver como isso funciona na prática.

**Imagine que estamos construindo um sistema de e-commerce. Podemos organizar nossas classes da seguinte forma:**

📄 **Arquivo 1:** `Produto.cs`
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

📄 **Arquivo 2:** `Pedido.cs`
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

💡 **Sem a diretiva using `Ecommerce.Modelos;`, teríamos que escrever o nome completo (fully qualified name - nome totalmente qualificado) conforme bloco abaixo:**

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

**Prevenção de conflito de nomes:**

Agora, suponha que uma biblioteca de terceiros que usamos para gerar relatórios também tenha uma classe chamada `Produto`, mas com propriedades diferentes.

**Arquivo da biblioteca de terceiros:**

```csharp

namespace Relatorios.Componentes
{
    public class Produto
    {
        // Propriedades diferentes, para um catálogo de relatório
        public string CodigoProduto { get; set; }
        public string Descricao { get; set; }
    }
}

```

> No nosso código principal, podemos usar as duas classes `Produto` sem ambiguidade, referenciando-as por seus namespaces.

**Arquivo do Programa Principal:** ``Program.cs``

```csharp

using System;
// Importamos os dois namespaces que contêm uma classe chamada 'Produto'
using Ecommerce.Modelos;
using Relatorios.Componentes;

// O compilador agora fica confuso! Qual 'Produto' usar?
// Produto produto = new Produto(); // <-- ISSO GERARIA UM ERRO DE AMBIGUIDADE!

class Program
{
    static void Main(string[] args)
    {
        // SOLUÇÃO: Usamos o nome completo (fully qualified name) para desambiguar
        Ecommerce.Modelos.Produto produtoDaLoja = new Ecommerce.Modelos.Produto
        {
            Id = 1,
            Nome = "Notebook Gamer",
            Preco = 7500.00m
        };

        Relatorios.Componentes.Produto produtoDoRelatorio = new Relatorios.Componentes.Produto
        {
            CodigoProduto = "NTBGMR-001",
            Descricao = "Notebook de Alta Performance para Jogos"
        };

        Console.WriteLine($"Produto da Loja: {produtoDaLoja.Nome}");
        Console.WriteLine($"Produto do Relatório: {produtoDoRelatorio.Descricao}");

        // SOLUÇÃO ALTERNATIVA: Alias de namespace
        // Podemos criar um "apelido" para um dos namespaces para facilitar
        using ProdutoDeRelatorio = Relatorios.Componentes.Produto;

        ProdutoDeRelatorio outroProdutoRelatorio = new ProdutoDeRelatorio();
        outroProdutoRelatorio.CodigoProduto = "XYZ-123";
    }
}

```

---

### 3️⃣ `class`:
Uma `class` (classe) é um **molde** ou uma **planta baixa** para criar **objetos**. Ela define uma estrutura que agrupa dados (representados por **campos** e **propriedades**) e comportamentos (representados por **métodos**).     
Pense em uma classe como a planta de um carro. A planta (`class Carro`) define todas as características que um carro pode ter (cor, marca, modelo, ano) e tudo que ele pode fazer (ligar, acelerar, frear).       
Um **objeto** é a instância concreta criada a partir dessa planta. Usando a mesma analogia, o "seu carro" na garagem, um Ford Mustang vermelho de 2023, é um objeto (uma instância) da classe `Carro`. Podem existir milhares de objetos `Carro`, cada um com suas próprias características (cor diferente, ano diferente), mas todos seguem a mesma estrutura definida pela classe.
Dominar o conceito de classes é o passo mais crucial para se tornar proficiente em C# e na plataforma .NET. É através delas que modelamos o mundo real e construímos sistemas complexos de forma organizada, reutilizável e robusta.

**Em resumo, uma classe define:**

🔹 **Atributos (O que o objeto é ou tem):** São os dados, representados por campos (variáveis internas) e propriedades (acessadores controlados para os campos).
🔹 **Comportamentos (O que o objeto faz):** São as ações, representadas por métodos (funções).

🧠 **Exemplo:**

Vamos criar uma classe `Funcionario` para representar um funcionário em um sistema de RH.

**A definição da classe (A planta baixa)**

No arquivo `Funcionario.cs`, definimos a estrutura.

```csharp

using System;

// Definindo o namespace para organizar nosso código
namespace Empresa.Modelos
{
    // A declaração da classe com o modificador de acesso 'public'
    // 'public' significa que esta classe pode ser acessada por qualquer outra parte do programa.
    public class Funcionario
    {
        // 1. CAMPOS (Fields)
        // São variáveis internas da classe. Por convenção, geralmente são privadas.
        private decimal _salario;

        // 2. PROPRIEDADES (Properties)
        // São a forma "pública" de expor os dados da classe.
        // Elas encapsulam a lógica de acesso aos campos.
        public int Id { get; set; }
        public string Nome { get; set; }
        public string Cargo { get; set; }

        // Propriedade com lógica customizada para proteger o campo _salario
        public decimal Salario
        {
            get { return _salario; }
            set
            {
                if (value < 0) // Regra de negócio: salário não pode ser negativo
                {
                    // Lança uma exceção se a regra for violada
                    throw new ArgumentException("O salário não pode ser negativo.");
                }
                _salario = value;
            }
        }

        // 3. CONSTRUTOR (Constructor)
        // Um método especial chamado quando um objeto desta classe é criado ('new').
        // É usado para inicializar o estado do objeto.
        public Funcionario(int id, string nome, decimal salarioInicial)
        {
            this.Id = id;
            this.Nome = nome;
            this.Salario = salarioInicial; // Usa a propriedade para garantir a validação
            this.Cargo = "Não definido"; // Valor padrão
        }

        // 4. MÉTODOS (Methods)
        // Definem o comportamento do objeto, as ações que ele pode realizar.
        public void Promover(string novoCargo, decimal aumento)
        {
            if (aumento <= 0)
            {
                throw new ArgumentException("O aumento deve ser um valor positivo.");
            }

            this.Cargo = novoCargo;
            this.Salario += aumento; // Aumenta o salário
        }

        public void ExibirDetalhes()
        {
            Console.WriteLine($"ID: {Id}, Nome: {Nome}, Cargo: {Cargo}, Salário: {Salario:C}");
        }
    }
}

```

**A Criação e Uso do Objeto (A Construção do Carro)**

Agora, em nosso programa principal (`Program.cs`), vamos criar e interagir com objetos (instâncias) da classe `Funcionario`.

```csharp

using System;
using Empresa.Modelos; // Importamos o namespace para usar a classe Funcionario

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Criando funcionários...");

        // Usamos a palavra-chave 'new' para INSTANCIAR um objeto da classe Funcionario.
        // Isso chama o construtor da classe.
        Funcionario func1 = new Funcionario(101, "Ana Silva", 5000m);
        Funcionario func2 = new Funcionario(102, "Carlos Souza", 6500m);

        // Acessando as propriedades e métodos dos objetos
        Console.WriteLine("\nDetalhes iniciais:");
        func1.ExibirDetalhes(); // Saída: ID: 101, Nome: Ana Silva, Cargo: Não definido, Salário: R$ 5.000,00
        func2.ExibirDetalhes(); // Saída: ID: 102, Nome: Carlos Souza, Cargo: Não definido, Salário: R$ 6.500,00

        // Modificando o estado dos objetos usando seus métodos
        Console.WriteLine("\nPromovendo a Ana...");
        func1.Promover("Gerente de Projetos", 1500m);

        // Exibindo o novo estado
        Console.WriteLine("\nDetalhes após promoção:");
        func1.ExibirDetalhes(); // Saída: ID: 101, Nome: Ana Silva, Cargo: Gerente de Projetos, Salário: R$ 6.500,00
        func2.ExibirDetalhes(); // O objeto func2 permanece inalterado
    }
}

```

---

`static void Main(string[] args)`: O ponto de entrada principal do programa, onde a execução começa.         
`Console.WriteLine("Hello, World!");`: Uma instrução que escreve "Hello, World!" no ecrã.
Ponto e vírgula `(;)`: Termina cada instrução C#.

---

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 Material de estudo: *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)