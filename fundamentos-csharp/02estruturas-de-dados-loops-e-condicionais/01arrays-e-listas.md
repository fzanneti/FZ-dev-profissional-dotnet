# Estruturas de Dados, Loops e Condicionais

![Badge](https://img.shields.io/badge/Fabio%20Zanneti%20da%20Silva-Profissional-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/1._Arrays_e_Listas-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-CSharp-black)
![Ambiente](https://img.shields.io/badge/Ambiente-.NET-black)
![Autor](https://img.shields.io/badge/Autor-fzanneti-black?style=flat-square&logo=github)

[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)

---

No universo da programação em C#, saber como agrupar e gerenciar dados é uma habilidade fundamental. Duas das estruturas mais comuns para essa tarefa são os **arrays** e as **listas**. Embora ambos sirvam para armazenar coleções de elementos, eles possuem características distintas que os tornam mais adequados para diferentes situações.

Este guia foi criado para ser o seu ponto de partida, desmistificando esses conceitos de forma clara e didática, mesmo que você nunca tenha escrito uma linha de código.

### 1️⃣ Arrays: As "caixas" de tamanho fixo

Imagine que você precisa guardar uma coleção de livros em uma estante. Antes de comprar a estante, você decide que ela terá espaço para exatamente 5 livros. Nem mais, nem menos. Um **array** em C# funciona de maneira muito parecida.

Um **array** é uma estrutura que armazena uma **quantidade fixa** de elementos de um **mesmo tipo**. Uma vez que você define o tamanho de um **array**, ele não pode ser alterado.

**Características principais:**

🔹 **Tamanho fixo:** O número de elementos é definido no momento da sua criação e não pode mudar.      
🔹 **Mesmo tipo de dado:** Todos os elementos dentro de um array devem ser do mesmo tipo (só inteiros, só textos, etc.).     
🔹 **Acesso rápido:** O acesso a um elemento é extremamente rápido, pois o computador sabe exatamente onde encontrá-lo na memória através de um "endereço" chamado índice.    

**Como declarar e inicializar um array**

Você pode criar um **array** de duas maneiras principais.

**▶️ Declarando o tamanho primeiro:**

Primeiro, você especifica o tipo dos dados que o **array** vai guardar, seguido de colchetes `[ ]`, o nome da variável, e depois informa o tamanho dele.

```csharp

// Declara um array de inteiros com espaço para 3 números.
int[] numeros = new int[3];

// Agora, vamos colocar valores em cada posição.
// Lembre-se: a contagem de posições (índice) começa em ZERO!
numeros[0] = 10; // Primeira posição (índice 0)
numeros[1] = 20; // Segunda posição (índice 1)
numeros[2] = 30; // Terceira posição (índice 2)

```

**▶️ Inicializando com valores diretos:**

Você pode criar o **array** e já fornecer todos os seus elementos. O C# é inteligente o suficiente para contar quantos elementos você passou e definir o tamanho do **array** automaticamente.

```csharp

// Declara e inicializa um array de inteiros com três valores.
int[] numeros = { 1, 2, 3 };

// Declara e inicializa um array de textos (strings).
string[] frutas = { "Maçã", "Banana", "Laranja" };

```

> No exemplo acima, `numeros` terá um tamanho fixo de 3 e `frutas` também terá um tamanho fixo de 3.

**Como acessar os elementos de um array?**

Para ler ou modificar um valor em um **array**, você utiliza seu **índice** (a posição do elemento). A regra de ouro é: **a contagem de índices sempre começa em 0**.

```csharp

int[] numeros = { 10, 20, 30 };

// Para ler o valor da primeira posição (índice 0)
Console.WriteLine(numeros[0]); // O resultado será: 10

// Para ler o valor da terceira posição (índice 2)
Console.WriteLine(numeros[2]); // O resultado será: 30

// Para alterar o valor da segunda posição (índice 1)
numeros[1] = 25;
Console.WriteLine(numeros[1]); // O resultado agora será: 25

```

> 🚨 **Cuidado!** Tentar acessar um índice que não existe (por exemplo, `numeros[3]` em um **array** de 3 posições) resultará em um erro (`IndexOutOfRangeException`), pois você está tentando acessar uma "caixa" que não existe na sua "estante".

---

### 2️⃣ Listas (`List<T>`): A "mochila" expansível

Agora, imagine que em vez de uma estante fixa, você tem uma mochila para guardar seus livros. Você pode começar com um livro, adicionar mais dois depois e, se precisar, remover um. A mochila se ajusta à quantidade de livros que você carrega. Essa é a essência de uma **lista** (`List<T>`) em C#.

Uma `List<T>` é uma coleção **dinâmica**, ou seja, seu tamanho pode aumentar ou diminuir conforme você adiciona ou remove elementos. O `<T>` na sintaxe significa que ela é "genérica", ou seja, você define o tipo de dado que ela vai armazenar ao criá-la (por exemplo, `List<int>` para inteiros, `List<string>` para textos).

**Características principais:**

🔹 **Tamanho dinâmico:** Você pode adicionar e remover itens livremente, e a **lista** se ajusta automaticamente.    
🔹 **Mesmo tipo de dado (Type-Safe):** Assim como os arrays, uma `List<T>` só armazena elementos do tipo que você especificou.      
🔹 **Flexibilidade:** Oferece métodos úteis para adicionar, remover, buscar e ordenar elementos.    

**Como declarar e inicializar uma lista?**

Para usar listas, você precisa declarar uma variável do tipo `List<T>` e criar uma nova instância dela.

```csharp

// Declara e cria uma lista vazia para armazenar textos (strings).
List<string> nomes = new List<string>();

```

**Você também pode inicializá-la com alguns valores iniciais, de forma parecida com um array:**

```csharp

// Declara e inicializa uma lista de nomes.
List<string> nomes = new List<string> { "Ana", "Carlos" };

```

**Como adicionar e acessar elementos em uma lista?**

A grande vantagem das listas é a facilidade de manipulação.

**Adicionando elementos:**

Você usa o método `.Add()` para inserir um novo elemento ao final da lista.

```csharp

List<string> nomes = new List<string>();

nomes.Add("Ana");    // A lista agora contém: {"Ana"}
nomes.Add("Carlos"); // A lista agora contém: {"Ana", "Carlos"}
nomes.Add("Bia");    // A lista agora contém: {"Ana", "Carlos", "Bia"}

```

**Acessando elementos:**

O acesso aos elementos é feito da mesma forma que nos arrays: usando índices que começam em 0.

```csharp

Console.WriteLine(nomes[0]); // O resultado será: Ana
Console.WriteLine(nomes[1]); // O resultado será: Carlos

```

**Removendo elementos:**

Você pode remover itens usando o método `.Remove()` (para remover um valor específico) ou `.RemoveAt()` (para remover pela posição/índice).

```csharp

// Remove o nome "Carlos" da lista
nomes.Remove("Carlos");

// A lista agora contém: {"Ana", "Bia"}

// Remove o elemento que está na primeira posição (índice 0)
nomes.RemoveAt(0);

// A lista agora contém: {"Bia"}

```

**Verificando o tamanho:**

Para saber quantos itens existem em uma **lista**, você usa a propriedade `.Count` (diferente do `.Length` dos arrays).

```csharp

List<string> nomes = new List<string> { "Ana", "Carlos", "Bia" };
Console.WriteLine(nomes.Count); // O resultado será: 3

```

**🧠 Programa completo integrado - (Mini sistema de lista de tarefas (To-Do List)):**

**Objetivo:**

🔹 Definir um conjunto fixo de categorias para as tarefas.      
🔹 Permitir que o usuário adicione novas tarefas a uma lista.     
🔹 Permitir que o usuário "conclua" (remova) uma tarefa da lista.     
🔹 Exibir todas as tarefas pendentes.    

```csharp

using System;
using System.Collections.Generic;

// Para simplificar, vamos criar uma classe para representar uma Tarefa.
// Uma tarefa terá uma Descrição e uma Categoria.
public class Tarefa
{
    public string Descricao { get; set; }
    public string Categoria { get; set; }

    // Este é um "construtor" que facilita a criação de uma nova tarefa.
    public Tarefa(string descricao, string categoria)
    {
        Descricao = descricao;
        Categoria = categoria;
    }

    // Sobrescrevemos o método ToString() para exibir a tarefa de forma legível.
    public override string ToString()
    {
        return $"[{Categoria}] - {Descricao}";
    }
}

public class ProgramaListaDeTarefas
{
    public static void Main(string[] args)
    {
        // ==================================================================
        // 1. USANDO ARRAY para um conjunto FIXO de dados
        // ==================================================================
        // Nossas categorias de tarefas são fixas. Não planejamos adicionar novas
        // categorias durante a execução do programa. Um Array é perfeito para isso.
        string[] categoriasValidas = { "Trabalho", "Estudo", "Pessoal", "Compras" };

        Console.WriteLine("Categorias de tarefas disponíveis:");
        // Usamos um loop 'foreach' para percorrer e exibir todos os itens do array.
        foreach (string categoria in categoriasValidas)
        {
            Console.WriteLine($"- {categoria}");
        }
        Console.WriteLine("---------------------------------------------");


        // ==================================================================
        // 2. USANDO LISTA para uma coleção DINÂMICA de dados
        // ==================================================================
        // A lista de tarefas precisa ser dinâmica. Podemos adicionar novas tarefas
        // a qualquer momento. Uma List<T> é a escolha ideal.
        List<Tarefa> minhasTarefas = new List<Tarefa>();


        // ==================================================================
        // 3. Adicionando itens à LISTA
        // ==================================================================
        Console.WriteLine("\nAdicionando novas tarefas à lista...\n");

        // Criamos novas tarefas e usamos o método .Add() para incluí-las na lista.
        // Note que usamos as categorias definidas em nosso array.
        minhasTarefas.Add(new Tarefa("Preparar relatório mensal", categoriasValidas[0])); // Trabalho
        minhasTarefas.Add(new Tarefa("Estudar sobre Arrays e Listas", categoriasValidas[1])); // Estudo
        minhasTarefas.Add(new Tarefa("Comprar leite e pão", categoriasValidas[3])); // Compras
        minhasTarefas.Add(new Tarefa("Ligar para o médico", categoriasValidas[2])); // Pessoal


        // ==================================================================
        // 4. Exibindo os itens da LISTA
        // ==================================================================
        Console.WriteLine("### Minhas Tarefas Pendentes ###");
        ExibirTarefas(minhasTarefas);


        // ==================================================================
        // 5. Removendo um item da LISTA
        // ==================================================================
        Console.WriteLine("\nConcluindo a tarefa 'Comprar leite e pão'...");

        // Para remover, primeiro precisamos encontrar a tarefa na lista.
        Tarefa tarefaParaRemover = null;
        foreach (Tarefa tarefa in minhasTarefas)
        {
            if (tarefa.Descricao == "Comprar leite e pão")
            {
                tarefaParaRemover = tarefa;
                break; // Encontramos a tarefa, podemos parar o loop.
            }
        }

        // Se a tarefa foi encontrada (não é nula), nós a removemos.
        if (tarefaParaRemover != null)
        {
            minhasTarefas.Remove(tarefaParaRemover);
            Console.WriteLine("Tarefa concluída e removida da lista!\n");
        }


        // ==================================================================
        // 6. Exibindo a lista final
        // ==================================================================
        Console.WriteLine("### Minhas Tarefas Pendentes Atualizadas ###");
        ExibirTarefas(minhasTarefas);
    }

    // Uma função auxiliar para exibir as tarefas de forma organizada.
    // Recebe uma lista de tarefas como parâmetro.
    public static void ExibirTarefas(List<Tarefa> tarefas)
    {
        if (tarefas.Count == 0)
        {
            Console.WriteLine("Nenhuma tarefa pendente. Bom trabalho!");
        }
        else
        {
            // O loop percorre cada tarefa na lista e a imprime no console.
            // Note que a contagem de tarefas é feita com .Count
            Console.WriteLine($"Total de tarefas: {tarefas.Count}");
            for (int i = 0; i < tarefas.Count; i++)
            {
                // Acessamos cada tarefa pelo seu índice [i]
                Console.WriteLine($"{i + 1}. {tarefas[i]}");
            }
        }
        Console.WriteLine("---------------------------------------------");
    }
}

```

**Saída no console**

Ao executar o código acima, você verá o seguinte resultado:

```bash

Categorias de tarefas disponíveis:
- Trabalho
- Estudo
- Pessoal
- Compras
---------------------------------------------

Adicionando novas tarefas à lista...

### Minhas Tarefas Pendentes ###
Total de tarefas: 4
1. [Trabalho] - Preparar relatório mensal
2. [Estudo] - Estudar sobre Arrays e Listas
3. [Compras] - Comprar leite e pão
4. [Pessoal] - Ligar para o médico
---------------------------------------------

Concluindo a tarefa 'Comprar leite e pão'...
Tarefa concluída e removida da lista!

### Minhas Tarefas Pendentes Atualizadas ###
Total de tarefas: 3
1. [Trabalho] - Preparar relatório mensal
2. [Estudo] - Estudar sobre Arrays e Listas
3. [Pessoal] - Ligar para o médico
---------------------------------------------

```

**🔎 Análise:**

🔹 **Array `categoriasValidas`:** Foi a escolha perfeita para as categorias porque elas são um conjunto de dados **conhecido e imutável**. Não precisamos da flexibilidade de adicionar ou remover categorias, e o array garante essa estrutura de forma simples e eficiente.       
🔹 **Lista `minhasTarefas`:** Foi essencial para gerenciar as tarefas. No início, a lista estava vazia (`new List<Tarefa>()`). Conforme o programa rodou, **adicionamos** 4 novas tarefas com o método `.Add()`. Depois, **removemos** uma tarefa com o método `.Remove()`. A lista se ajustou perfeitamente a essas mudanças, diminuindo seu tamanho (`.Count`) de 4 para 3. Se usássemos um array para as tarefas, seria muito mais complexo e ineficiente gerenciá-las.

> Este exemplo demonstra o "mundo real" da programação, onde diferentes ferramentas são usadas para resolver diferentes partes de um problema. Compreender quando usar a rigidez eficiente de um **Array** e quando usar a flexibilidade de uma **Lista** é um passo crucial para se tornar um bom desenvolvedor C#.

---

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)