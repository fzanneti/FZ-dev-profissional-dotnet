# ![Badge](https://img.shields.io/badge/3.%20POO%20--%20Classes%2C%20Heran%C3%A7a%2C%20Polimorfismo-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/3.2._Encapsulamento-blue?style=for-the-badge&logo=c-sharp&logoColor=white)
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

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/03poo-classes-heran%C3%A7a-polimorfismo/01classe.md) | [➡️]()

---

**Desvendando o encapsulamento em C#:**

No universo da programação orientada a objetos (POO), um dos pilares fundamentais que garantem a organização, segurança e manutenibilidade do código é o encapsulamento. Para quem está começando em C#, compreender este conceito é um passo crucial para escrever um código mais robusto e profissional. Este guia didático irá desmistificar o encapsulamento e seus principais atores: os modificadores de acesso `private`, `public` e `protected`.

---

**O que é encapsulamento? Uma analogia para clarear as ideias**

Imagine uma máquina de café expresso. Você, como usuário, tem uma interface simples para interagir: um botão para ligar, outro para escolher o tipo de café e o local para colocar a xícara. O que você não vê – e não precisa se preocupar – é com a complexa engenharia interna: a moagem dos grãos, o aquecimento da água na temperatura exata, a pressão aplicada. Tudo isso está "encapsulado" dentro da máquina.

Na programação, o encapsulamento funciona de maneira semelhante. Uma "classe" (o nosso projeto da máquina de café) agrupa seus dados (as informações, como a quantidade de água) e seus comportamentos (as ações, como "fazer café"). O encapsulamento consiste em esconder os detalhes complexos da implementação e expor apenas uma interface clara e segura para o mundo exterior.

**Essa prática traz enormes vantagens:**

🔹 **Segurança:** Protege os dados internos de modificações acidentais ou indevidas.      
🔹 **Manutenção simplificada:** Permite que a lógica interna de uma classe seja alterada sem quebrar o código que a utiliza.       
🔹 **Organização:** Agrupa dados e métodos relacionados, tornando o código mais legível e coeso.    

**Os guardiões do acesso: `public`, `private` e `protected`**

Para controlar o que fica exposto e o que fica escondido em nossas classes, o **C#** nos oferece os **modificadores de acesso**. Vamos entender os três principais usando a analogia de uma Casa.

---

### 1️⃣ `public`: A Porta da frente (Acesso total)

O modificador `public` torna um membro da classe (seja um dado ou um método) totalmente acessível a qualquer um, de qualquer lugar do seu projeto. É a porta da frente da nossa casa: qualquer pessoa pode ver e interagir com o que é público.

**Analogia:** A sua caixa de correio. Ela fica do lado de fora da casa (public) para que o carteiro (outra parte do seu código) possa depositar as cartas sem precisar entrar.

**🧠 Exemplo:**

Vamos criar uma classe `ContaBancaria`. O número da conta e o nome do titular são informações que outras partes do sistema podem precisar visualizar.

```csharp

// Uma classe que representa uma conta bancária
public class ContaBancaria
{
    // Atributos (dados) públicos
    public string NumeroDaConta;
    public string NomeDoTitular;

    // Um método (comportamento) público
    public void ExibirInformacoes()
    {
        Console.WriteLine($"Conta: {NumeroDaConta}, Titular: {NomeDoTitular}");
    }
}

// Em outra parte do seu código (como no programa principal)
class Program
{
    static void Main(string[] args)
    {
        // Criando um objeto do tipo ContaBancaria
        ContaBancaria minhaConta = new ContaBancaria();

        // Acessando e modificando os membros públicos diretamente
        minhaConta.NumeroDaConta = "12345-6";
        minhaConta.NomeDoTitular = "Maria Silva";

        // Chamando um método público
        minhaConta.ExibirInformacoes();
    }
}

```

> Neste caso, qualquer parte do código pode criar uma `ContaBancaria` e acessar ou modificar `NumeroDaConta` e `NomeDoTitular` livremente.

---

### 2️⃣ `private`: O cofre do quarto (Acesso restrito)

O modificador `private` é o oposto do `public`. Ele restringe o acesso a um membro apenas à própria classe onde ele foi declarado. Nenhuma outra classe pode ver ou interagir com ele diretamente.

**Analogia:** O cofre dentro do seu quarto. Apenas você (`a própria classe`) sabe a combinação e pode acessá-lo. Visitantes (`outras classes`) nem sabem que ele existe.

**🧠 Exemplo:**

O saldo de uma conta bancária é uma informação crítica. Não queremos que qualquer parte do código possa alterá-lo para um valor qualquer (por exemplo, um valor negativo). Vamos proteger o saldo tornando-o `private`.

```csharp

// A mesma classe, agora com encapsulamento
public class ContaBancaria
{
    public string NumeroDaConta;
    public string NomeDoTitular;

    // O saldo agora é PRIVADO
    private double saldo;

    // Método público para depositar de forma controlada
    public void Depositar(double valor)
    {
        if (valor > 0)
        {
            saldo += valor;
            Console.WriteLine($"Depósito de R$ {valor} realizado com sucesso.");
        }
        else
        {
            Console.WriteLine("O valor do depósito deve ser positivo.");
        }
    }

    // Método público para consultar o saldo
    public double ConsultarSaldo()
    {
        return saldo;
    }
}

// No programa principal
class Program
{
    static void Main(string[] args)
    {
        ContaBancaria minhaConta = new ContaBancaria();
        minhaConta.NumeroDaConta = "12345-6";
        minhaConta.NomeDoTitular = "Maria Silva";

        // TENTATIVA INVÁLIDA: Isso gerará um ERRO de compilação!
        // minhaConta.saldo = -500; // O cofre está trancado!

        // A forma correta e segura de interagir
        minhaConta.Depositar(200.50);
        minhaConta.Depositar(-50); // A lógica de proteção impedirá isso

        // Consultando o saldo através do método público
        Console.WriteLine($"Saldo atual: R$ {minhaConta.ConsultarSaldo()}");
    }
}

```

> Veja que agora não podemos mais acessar `saldo` diretamente. A única forma de modificar o saldo é através do método `Depositar`, que contém uma regra de validação, garantindo a integridade dos nossos dados. Isso é o encapsulamento em ação!

---

### 3️⃣ `protected`: Segredos de família (Acesso por herança)

O modificador `protected` é um intermediário. Um membro `protected` é acessível dentro da própria classe e também por qualquer classe que "herde" dela (suas classes filhas).

Analogia: As receitas de família. Elas estão guardadas dentro de casa e não são para os visitantes (`public`), mas são passadas de pais para filhos (`classes filhas`).

**🧠 Exemplo:**

Vamos criar um tipo especial de conta, uma `ContaPoupanca`, que vai herdar as características da nossa `ContaBancaria` e adicionar uma taxa de juros. O método que calcula os juros precisa acessar o saldo, mas não queremos que o saldo seja público.

```csharp

public class ContaBancaria
{
    public string NumeroDaConta;
    public string NomeDoTitular;

    // Alterando de 'private' para 'protected'
    protected double saldo;

    public void Depositar(double valor)
    {
        if (valor > 0)
        {
            saldo += valor;
        }
    }

    public double ConsultarSaldo()
    {
        return saldo;
    }
}

// ContaPoupanca "herda de" ContaBancaria
public class ContaPoupanca : ContaBancaria
{
    public void AdicionarJuros()
    {
        // Consegue acessar o 'saldo' porque é PROTEGIDO e ContaPoupanca é uma "filha"
        double juros = saldo * 0.005; // Exemplo de taxa de juros
        saldo += juros;
        Console.WriteLine($"Juros de R$ {juros} adicionados.");
    }
}

// No programa principal
class Program
{
    static void Main(string[] args)
    {
        ContaPoupanca minhaPoupanca = new ContaPoupanca();

        // TENTATIVA INVÁLIDA: Mesmo sendo herdado, 'saldo' não é público!
        // minhaPoupanca.saldo = 10000; // ERRO! Acesso restrito à família.

        minhaPoupanca.Depositar(1000);
        minhaPoupanca.AdicionarJuros();

        Console.WriteLine($"Novo saldo da poupança: R$ {minhaPoupanca.ConsultarSaldo()}");
    }
}

```

> Neste exemplo, a `ContaPoupanca` pode manipular diretamente o `saldo` para adicionar os juros, pois ela é uma "herdeira" da `ContaBancaria`. No entanto, para o resto do programa (a classe `Program`), o `saldo` continua inacessível diretamente.

---

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/03poo-classes-heran%C3%A7a-polimorfismo/01classe.md) | [➡️]()

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)