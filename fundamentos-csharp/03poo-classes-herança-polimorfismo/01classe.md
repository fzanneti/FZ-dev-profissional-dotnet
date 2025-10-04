# ![Badge](https://img.shields.io/badge/3.%20POO%20--%20Classes%2C%20Heran%C3%A7a%2C%20Polimorfismo-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

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

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/a63e2d15354df1dd0db5a476a78ec93117daa636/fundamentos-csharp/02estruturas-de-dados-loops-e-condicionais/03loops.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/03poo-classes-heran%C3%A7a-polimorfismo/02encapsulamento.md)

---

**O que é uma classe? A planta da sua casa**

Imagine que você quer construir uma casa. Antes de assentar o primeiro tijolo, você precisa de uma planta baixa. Essa planta detalha tudo sobre a casa: quantos quartos terá, a localização das janelas, a cor da porta. A planta não é a casa em si, mas o **molde** para construir quantas casas idênticas você quiser.

No **C#**, uma classe é exatamente isso: uma planta, um molde. Ela define a estrutura de algo que queremos criar no nosso programa. Esse "algo" nós chamamos de **objeto**. Assim como a planta define as características de uma casa, a classe define as **propriedades** (características) e os **métodos** (comportamentos) de um objeto.

**Em termos simples:**

🔹 **Classe:** O molde (ex: a planta de um carro).       
🔹 **Objeto:** A instância concreta criada a partir do molde (ex: um carro específico, com uma cor e placa definidas).    

---

**Anatomia de uma classe: Propriedades e métodos**

Toda classe em **C#** é composta fundamentalmente por duas coisas: **propriedades** e **métodos**. Vamos usar a analogia de um `Carro` para entender cada uma.

### 1️⃣ Propriedades: As características do objeto

As propriedades são as características que descrevem um objeto. São como os "adjetivos" do seu molde. Se a nossa classe é `Carro`, quais seriam suas propriedades?

🔹 Cor      
🔹 Modelo      
🔹 Ano      
🔹 Velocidade Atual     

> Em **C#**, nós declaramos essas propriedades dentro da classe, especificando o tipo de dado que cada uma armazenará (texto, número, etc.).

**🧠 Exemplo:**

```csharp

public class Carro
{
    // Propriedades
    public string Cor { get; set; }
    public string Modelo { get; set; }
    public int Ano { get; set; }
    public int VelocidadeAtual { get; private set; } 
    // O 'private set' indica que a velocidade só pode ser alterada por métodos dentro da própria classe

}

```

> Neste exemplo, `Cor` e `Modelo` são do tipo `string` (texto), e `Ano` e `VelocidadeAtual` são `int` (números inteiros). O `{ get; set; }` é a forma padrão do C# para permitir que essas propriedades sejam lidas (`get`) e alteradas (`set`).

---

### 2️⃣ Métodos: As ações que o objeto pode fazer

Os métodos definem o que um objeto pode **fazer**. São as "ações" ou "comportamentos" do seu molde. Se um carro tem características, ele também pode realizar ações. Quais seriam os métodos de um `Carro`?

🔹 Acelerar     
🔹 Frear     
🔹 Buzinar     

> Métodos são blocos de código que executam uma tarefa específica.

**🧠 Exemplo - (complementando a classe `Carro`):**

```csharp

public class Carro
{
    // Propriedades
    public string Cor { get; set; }
    public string Modelo { get; set; }
    public int Ano { get; set; }
    public int VelocidadeAtual { get; private set; }

    // Construtor: Um método especial para criar o objeto
    public Carro(string cor, string modelo, int ano)
    {
        Cor = cor;
        Modelo = modelo;
        Ano = ano;
        VelocidadeAtual = 0; // Todo carro começa parado
    }

    // Métodos
    public void Acelerar(int aumento)
    {
        VelocidadeAtual += aumento;
        Console.WriteLine($"Acelerando! Velocidade atual: {VelocidadeAtual} km/h");
    }

    public void Frear(int reducao)
    {
        VelocidadeAtual -= reducao;
        if (VelocidadeAtual < 0)
        {
            VelocidadeAtual = 0;
        }
        Console.WriteLine($"Freando... Velocidade atual: {VelocidadeAtual} km/h");
    }

    public void Buzinar()
    {
        Console.WriteLine("Bibi!");
    }
}

```

> Neste código, `Acelerar`, `Frear` e `Buzinar` são métodos. Note que `Acelerar` e `Frear` recebem um valor para modificar a propriedade `VelocidadeAtual`. Já o método `Buzinar` simplesmente executa uma ação.

---

### 3️⃣ Criando e usando objetos: Construindo a casa

Agora que temos a planta (`Classe Carro`), como construímos os carros (`Objetos`)? Usamos a palavra-chave `new`.

Imagine que queremos criar dois carros diferentes a partir do nosso molde.

**🧠 Exemplo:**

```csharp

// Em outro arquivo do seu projeto, como o Program.cs

class Program
{
    static void Main(string[] args)
    {
        // Criando o primeiro objeto (instância) da classe Carro
        Carro meuFusca = new Carro("Azul", "Fusca", 1975);

        // Criando o segundo objeto
        Carro minhaFerrari = new Carro("Vermelho", "Ferrari F40", 1990);

        // Acessando as propriedades dos objetos
        Console.WriteLine($"Tenho um {meuFusca.Modelo} do ano {meuFusca.Ano} e cor {meuFusca.Cor}.");
        Console.WriteLine($"E também uma {minhaFerrari.Modelo} de cor {minhaFerrari.Cor}.");

        // Usando os métodos dos objetos
        minhaFerrari.Acelerar(100);
        minhaFerrari.Buzinar();
        minhaFerrari.Frear(30);

        meuFusca.Acelerar(20);
    }
}

```

**O que aconteceu aqui?**

🔹 **`Carro meuFusca = new Carro(...):`** Criamos uma instância (um objeto) da classe `Carro`. O `new` "constrói" o objeto, e nós passamos os valores iniciais ("Azul", "Fusca", 1975) para o método construtor que definimos na classe.       
🔹 **`meuFusca.Modelo:`** Acessamos a propriedade `Modelo` do objeto `meuFusca`. Cada objeto tem seus próprios valores para suas propriedades. O `meuFusca` é azul, mas a `minhaFerrari` é vermelha.        
🔹 **`minhaFerrari.Acelerar(100):`** Chamamos o método `Acelerar` do objeto `minhaFerrari`. Essa ação afeta apenas a `minhaFerrari`, aumentando a sua `VelocidadeAtual`. O `meuFusca` permanece parado até que seu próprio método `Acelerar` seja chamado.     

---

**Por que usar classes? A organização é a chave**

Neste ponto, você pode estar se perguntando: por que toda essa estrutura? A resposta está em três pilares:

🔹 **Organização:** Classes agrupam dados (propriedades) e comportamentos (métodos) relacionados em um único lugar. Isso torna o código muito mais limpo, legível e fácil de dar manutenção. Em vez de ter variáveis e funções soltas, você tem "moldes" bem definidos.       
🔹 **Reutilização:** Uma vez que você define uma classe, pode criar quantos objetos quiser a partir dela, como fizemos com `meuFusca` e `minhaFerrari`. Você não precisa reescrever o código para cada novo carro.        
🔹 **Abstração:** Uma classe permite esconder a complexidade interna. Quem usa o objeto `Carro` não precisa saber como o método `Acelerar` funciona por dentro, apenas que ele existe e que vai aumentar a velocidade. Isso é como dirigir um carro de verdade: você pisa no acelerador sem precisar entender a mecânica da combustão do motor.    

**Resumo**

|**Conceito**|**Analogia**|**Descrição**|**Código**|
|:---:|---|---|---|
|Classe|A planta de uma casa|O molde que define a estrutura de um objeto.|`public class Carro { ... }`|
|Objeto|A casa construída|A instância concreta criada a partir de uma classe.|`Carro meuCarro = new Carro();`|
|Propriedade|A cor ou o nº de quartos|Uma característica ou dado do objeto.|`public string Cor { get; set; }`|
|Método|A ação de abrir uma porta|Um comportamento ou ação que o objeto pode realizar.|`public void Acelerar() { ... }`|

---

[⬅️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/a63e2d15354df1dd0db5a476a78ec93117daa636/fundamentos-csharp/02estruturas-de-dados-loops-e-condicionais/03loops.md) | [➡️](https://github.com/fzanneti/FZ-dev-profissional-dotnet/blob/3cc1b4076f9d01a46d36909b3292fb9d97cfcbbc/fundamentos-csharp/03poo-classes-heran%C3%A7a-polimorfismo/02encapsulamento.md)

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)