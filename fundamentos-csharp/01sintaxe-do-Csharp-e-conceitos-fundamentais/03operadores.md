# Sintaxe do C# e Conceitos Fundamentais

![Badge](https://img.shields.io/badge/Fabio%20Zanneti%20da%20Silva-Profissional-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

![Badge](https://img.shields.io/badge/3._Operadores-blue?style=for-the-badge&logo=c-sharp&logoColor=white)

> Aprendizado estruturado para se tornar desenvolvedor .NET profissional, com foco em C#, ASP.NET Core, APIs e integração com Inteligência Artificial.

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/dev-profissional-dotnet)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/dev-profissional-dotnet?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/dev-profissional-dotnet?style=social)
![Linguagem](https://img.shields.io/badge/Linguagem-CSharp-black)
![Ambiente](https://img.shields.io/badge/Ambiente-.NET-black)
![Autor](https://img.shields.io/badge/Autor-fzanneti-black?style=flat-square&logo=github)

[![Compilador Online](https://img.shields.io/badge/🔗%20Compilador_Online-C%23-blue?style=for-the-badge)](https://www.mycompiler.io/pt/new/csharp)


---

No universo do desenvolvimento com a plataforma .Net e a linguagem C#, o domínio dos operadores é fundamental para a construção de lógicas de programação robustas, eficientes e legíveis. Como especialista na área, apresento de forma clara e objetiva os principais operadores, divididos em suas categorias, com exemplos práticos que ilustram seu funcionamento.

### 1️⃣ Operadores aritméticos: A base dos cálculos
Os operadores aritméticos são a espinha dorsal de qualquer operação matemática em seu código. Eles permitem realizar desde simples adições até cálculos mais complexos.

|**Operador**|**Descrição**|**Exemplo**|
|:---:|---|---|
|`+`|Adição|`int soma = 10 + 5;` (Soma será 15)|
|`-`|Subtração|`int diferenca = 10 - 5;` (Diferença será 5)|
|`*`|Multiplicação|`int produto = 10 * 5;` (Produto será 50)|
|`/`|Divisão|`int quociente = 10 / 5;` (Quociente será 2)|

> ⚠️ **Ponto de Atenção:** A divisão de números inteiros (`int`) em C# resultará em um número inteiro, descartando qualquer parte fracionária. Para obter um resultado com casas decimais, ao menos um dos operandos deve ser de um tipo de ponto flutuante, como `double` ou `float`.

**🧠 Exemplo:** 

```csharp

int divisaoInteira = 7 / 2; // O resultado será 3
double divisaoDecimal = 7.0 / 2; // O resultado será 3.5

```

---

### 2️⃣ Operadores de comparação: Tomando decisões
Os operadores de comparação são essenciais para o controle de fluxo do seu programa. Eles avaliam a relação entre dois operandos e retornam um valor booleano (true ou false), permitindo que seu código tome decisões.

|**Operador**|**Descrição**|**Exemplo**|
|:---:|---|---|
|`==`|Igual a|	`bool ehIgual = (5 == 5);` (ehIgual será `true`)|
|`!=`|Diferente de|	`bool ehDiferente = (5 != 10);` (ehDiferente será `true`)|
|`<`|Menor que|	`bool ehMenor = (5 < 10);` (ehMenor será `true`)|
|`>`|Maior que|	`bool ehMaior = (10 > 5);` (ehMaior será `true`)|
|`<=`|Menor ou igual a|	`bool ehMenorOuIgual = (5 <= 5);` (ehMenorOuIgual será `true`)|
|`>=`|Maior ou igual a|	`bool ehMaiorOuIgual = (10 >= 10);` (ehMaiorOuIgual será `true`)|

> Esses operadores são frequentemente utilizados em conjunto com estruturas condicionais como `if`, `else` e `switch`.

**🧠 Exemplo:** 

```csharp

int idade = 18;
bool possuiHabilitacao = true;

if (idade >= 18 && possuiHabilitacao == true)
{
    Console.WriteLine("Pode dirigir.");
}
else
{
    Console.WriteLine("Não pode dirigir.");
}

```

---

### 3️⃣ Operadores lógicos: Combinando condições
Os operadores lógicos permitem combinar múltiplas expressões booleanas para criar condições mais complexas e refinadas.

|**Operador**|**Descrição**|**Exemplo**|
|:---:|---|---|
|`&&`(E)|Retorna `true` se **ambas** as condições forem verdadeiras.|`bool resultado = (5 > 3 && 10 < 20);` (resultado será `true`)|
|`!`(Não)|Inverte o valor booleano de uma expressão.|`bool resultado = !(5 > 10);` (resultado será `true`, pois a condição original (`false`) foi negada)|

**Otimização com "Curto-Circuito":** Uma característica importante dos operadores && e || é a avaliação de "curto-circuito" (short-circuiting).

- No caso do `&&`, se a primeira condição for `false`, a segunda não será avaliada, pois o resultado final já será `false`.
- No caso do `||`, se a primeira condição for `true`, a segunda não será avaliada, pois o resultado final já será `true`.

Esse comportamento pode ser utilizado para otimizar o desempenho e evitar exceções em seu código.

**🧠 Exemplo:**

**Vamos criar um exemplo que utiliza os três tipos de operadores para determinar se um usuário tem acesso a um determinado recurso do sistema.**

```csharp

// Dados do usuário
int idadeUsuario = 25;
bool ehAssinante = true;
int nivelAcesso = 3;

// Regras de acesso
const int IDADE_MINIMA = 18;
const int NIVEL_ACESSO_NECESSARIO = 3;

// Verificação de acesso utilizando operadores
bool temIdadeSuficiente = idadeUsuario >= IDADE_MINIMA;
bool temNivelAcessoValido = nivelAcesso == NIVEL_ACESSO_NECESSARIO;

// Acesso é concedido se o usuário for assinante E tiver a idade mínima OU se tiver o nível de acesso necessário.
if ((ehAssinante && temIdadeSuficiente) || temNivelAcessoValido)
{
    Console.WriteLine("Acesso Concedido!");
}
else
{
    Console.WriteLine("Acesso Negado.");
}

// Exemplo com o operador de negação
bool naoEhAdmin = !(nivelAcesso == 5); // Verifica se o usuário NÃO é um administrador
if (naoEhAdmin)
{
    Console.WriteLine("Este usuário não é um administrador.");
}

```

> Dominar o uso e a combinação desses operadores é um passo crucial para escrever um código em C# que seja não apenas funcional, mas também eficiente e de fácil manutenção, características essenciais para um especialista em .Net.

---

##### ✍️ Seção criada por: *Fabio Zanneti da Silva* - 🎯 *C# / .Net*
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-000000?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)