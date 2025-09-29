# ![Badge](https://img.shields.io/badge/2._Estruturas_de_Dados%2c_Loops_e_Condicionais-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/Fabio%20Zanneti%20da%20Silva-Profissional-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/2.2._Condicionais-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-CSharp-black)
![Ambiente](https://img.shields.io/badge/Ambiente-.NET-black)
![Autor](https://img.shields.io/badge/Autor-fzanneti-black?style=flat-square&logo=github)

[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)

---

**Desvendando o poder das condicionais em C#: Um guia definitivo para iniciantes**

Para quem está a dar os primeiros passos no mundo da programação, entender como fazer um programa "pensar" e tomar decisões é um marco fundamental. Na linguagem C#, a espinha dorsal dessa capacidade de decisão reside nas condicionais. Este guia didático foi criado para desmistificar as estruturas `if`, `else` e `switch`, tornando-as conceitos claros e acessíveis até mesmo para quem nunca escreveu uma linha de código.

**O que são condicionais e por que são essenciais?**

Imagine que você está a dar instruções a alguém. Em vez de uma lista rígida de tarefas, você provavelmente diria algo como: "**Se** estiver a chover, leve um guarda-chuva. **Caso contrário**, use óculos de sol." No mundo da programação, as condicionais funcionam exatamente da mesma forma. Elas permitem que o seu programa avalie uma determinada condição e execute blocos de código específicos com base no resultado dessa avaliação, que será sempre `verdadeiro` ou `falso`.

Essa capacidade de tomar decisões é o que torna os programas dinâmicos e inteligentes, permitindo-lhes reagir a diferentes entradas de dados, interações do utilizador e outros eventos.

---

### 1️⃣ - A estrutura `if`: A tomada de decisão fundamental

A instrução `if` é a forma mais básica de condicional. A sua sintaxe é simples e direta, assemelhando-se a uma pergunta de "sim" ou "não".

**Sintaxe básica:**

```csharp

if (condição)
{
    // Bloco de código a ser executado se a condição for verdadeira
}

```

A `condição` dentro dos parênteses é uma expressão que o C# avalia como sendo `verdadeira` ou `falsa`. Se for `verdadeira`, o código dentro das chaves `{}` é executado. Se for `falsa`, o programa simplesmente ignora esse bloco de código e continua a sua execução.

**🧠 Exemplo prático: Verificação de idade**

Vamos criar um programa simples que verifica se uma pessoa é maior de idade.

```csharp

int idade = 20;

if (idade >= 18)
{
    Console.WriteLine("Você é maior de idade e pode entrar.");
}

```

> Neste exemplo, a condição `idade >= 18` é avaliada. Como `20` é maior ou igual a `18`, a condição é `verdadeira`, e a mensagem `"Você é maior de idade e pode entrar."` será exibida no ecrã.

---

### 2️⃣ - A estrutura `else`: O caminho alternativo

A instrução `if` é ótima para executar código quando uma condição é verdadeira, mas e se quisermos fazer algo quando ela for falsa? É aqui que entra o `else`. O `else` oferece um caminho de execução alternativo.

**Sintaxe básica:**

```csharp

if (condição)
{
    // Bloco de código a ser executado se a condição for verdadeira
}
else
{
    // Bloco de código a ser executado se a condição for falsa
}

```

**🧠 Exemplo prático: Verificação de idade com alternativa**

Vamos expandir o nosso exemplo anterior para fornecer uma resposta caso a pessoa seja menor de idade.

``` csharp

int idade = 15;

if (idade >= 18)
{
    Console.WriteLine("Você é maior de idade e pode entrar.");
}
else
{
    Console.WriteLine("Desculpe, a sua entrada não é permitida por ser menor de idade.");
}

```

> Aqui, como a `idade` é `15`, a condição `idade >= 18` é `falsa`. Portanto, o bloco de código dentro do if é ignorado, e o bloco de código dentro do `else` é executado, exibindo a mensagem `"Desculpe, a sua entrada não é permitida por ser menor de idade."`.

---

### 3️⃣ - Múltiplas condições com `else if`

E se tivermos mais de duas possibilidades? Podemos encadear múltiplas verificações usando o `else if`.

**🧠 Exemplo prático: Classificação de notas**

Imagine um sistema que classifica as notas dos alunos.

```csharp

int nota = 85;

if (nota >= 90)
{
    Console.WriteLine("Excelente!");
}
else if (nota >= 70)
{
    Console.WriteLine("Bom trabalho!");
}
else if (nota >= 50)
{
    Console.WriteLine("Precisa de estudar mais.");
}
else
{
    Console.WriteLine("Reprovado.");
}

```

> O programa verificará as condições em ordem. Como `85` não é maior ou igual a `90`, ele passa para a próxima condição. Como `85` é maior ou igual a `70`, a mensagem `"Bom trabalho!"` será exibida, e as restantes condições não serão verificadas.

---

### 4️⃣ - A estrutura `switch`: Uma alternativa elegante para múltiplas escolhas

Quando você precisa de comparar uma única variável com vários valores possíveis, usar uma longa cadeia de `if-else if` pode tornar o código verboso e difícil de ler. O `switch` oferece uma solução mais limpa e organizada para esses cenários.

Pense no `switch` como um menu de um restaurante. Você tem uma opção (a variável que está a ser avaliada) e escolhe um dos pratos (os `case`).

**Sintaxe básica:**

```csharp

switch (variavel)
{
    case valor1:
        // Bloco de código para o valor1
        break;
    case valor2:
        // Bloco de código para o valor2
        break;
    // ... outros casos
    default:
        // Bloco de código se nenhum dos casos for correspondido
        break;
}

```

🔹 **`switch (variavel)`:** A variável cujo valor queremos comparar.      
🔹 **`case valorX:`:** Um valor específico com o qual a variável pode ser comparada.     
🔹 **`break;`:** Essencial! O `break` informa ao programa para sair do bloco `switch` assim que um caso correspondente for executado. Sem ele, a execução "cairia" para o próximo caso.     
🔹 **`default:`:** Opcional, mas altamente recomendado. O código aqui é executado se o valor da variável não corresponder a nenhum dos `case`. É semelhante ao `else` final numa cadeia `if-else if`.    

**🧠 Exemplo prático: Menu de opções**

Vamos criar um menu simples onde o utilizador escolhe uma opção.

```csharp

int opcao = 2;

switch (opcao)
{
    case 1:
        Console.WriteLine("Você selecionou: Novo Jogo");
        break;
    case 2:
        Console.WriteLine("Você selecionou: Carregar Jogo");
        break;
    case 3:
        Console.WriteLine("Você selecionou: Opções");
        break;
    case 4:
        Console.WriteLine("Você selecionou: Sair");
        break;
    default:
        Console.WriteLine("Opção inválida!");
        break;
}

```

> Neste caso, como `opcao` é 2, a saída será "Você selecionou: Carregar Jogo". O `break` então garante que o programa saia do `switch`.

**Quando usar `if-else` vs. `switch`?**

Para um iniciante, a escolha entre `if-else` e `switch` pode parecer confusa. Aqui está uma regra simples:

🔹 Use `if-else` ou `if-else if` quando estiver a lidar com condições complexas que envolvem intervalos (por exemplo, `nota >= 90`), comparações lógicas (`&&` - E, `||` - OU) ou múltiplas variáveis.       
🔹 Use `switch` quando estiver a comparar o valor de uma única variável com uma lista de valores específicos e constantes (números, strings, etc.). Geralmente, resulta num código mais limpo e legível para este cenário.     

Dominar as condicionais `if`, `else` e `switch` é o primeiro grande passo para escrever programas que são mais do que apenas uma sequência de comandos. É o ponto em que você começa a dar inteligência e flexibilidade ao seu código. Continue a praticar com diferentes cenários e, em breve, tomar decisões nos seus programas C# será algo natural e intuitivo.

---

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)