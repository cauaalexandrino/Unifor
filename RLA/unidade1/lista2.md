
# UNIFOR
**Nome**: Cauã Alexandrino Araújo Basile <br>
**Disciplina**: Raciocínio lógico algorítimo <br>

## Exercício exemplo
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o adicional de salário de funcionário por cargo de uma empresa fictícia. Sabe-se que os funcionários de cargo técnico receberão reajuste de 50%, cargo de gerência, um reajuste de 30% e demais, um reajuste de 10%. 

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o salário e profissão}}
B --> C[\sal, prof\]
C --> D{prof == 'Tecnico'}
D --FALSE--> E{prof == 'Gerente'}
D --TRUE--> F[sal_reaj = 1.5 * sal]
E --FALSE--> H[sal_reaj = 1.1 * sal]
E --TRUE--> G[sal_reaj = 1.3 * sal]
G --> I([FIM])
F --> I
H --> J{{'Salário Reajustado = ', sal_reaj}}
J --> I
```

#### Pseudocódigo
```java
ALGORITMO calReajuste
DECLARE sal, sal_reaj: REAL, prof: CARACTERE

INICIO

    // Solicita ao usuário que digite o salário e a profissão
    LEIA sal, prof

    // Realiza a escolha do reajuste salarial com base na profissão
    ESCOLHA

        // Caso a profissão seja "Técnico"
        CASO prof == “Técnico”		
            // Calcula o novo salário com reajuste de 50%
            sal_reaj ← 1.5 * sal

        // Caso a profissão seja "Gerente"
        CASO prof = “Gerente”		
            // Calcula o novo salário com reajuste de 30%
            sal_reaj ← 1.3 * sal

    // Se a profissão não for "Técnico" nem "Gerente", aplica um reajuste de 10%
    SENÃO
        sal_reaj ← 1.1 * sal

    FIM_ESCOLHA

    // Exibe o salário reajustado
    ESCREVA “Salário Reajustado = “, sal_reaj

FIM

```

#### Teste
| sal | prof | prof == “Técnico” | prof = “Gerente” | sal_reaj | Saída |
| -- | -- | -- | -- | -- | -- |
| 1000 | Técnico | V | F | 1500 | “Salário Reajustado = 1500“ |
| 2000 | Gerente | F | V | 2600 | “Salário Reajustado = 2600“ |
| 9000 | Diretor | F | F | 9900 | “Salário Reajustado = 9900“ |

## Lista de exercícios 02

### Exercício 01 (2.5 pontos)
Calcule a média de quatro números inteiros dados.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite o número 1:"}}
B --> C[/num1/]
C --> D{{"Digite o número 2:"}}
D --> E[/num2/]
E --> F{{"Digite o número 3:"}}
F --> G[/num3/]
G --> H{{"Digite o número 2:"}}
H --> I[/num4/]
I --> J["media = (num1 + num2 + num3 + num4)/4"]
J --> K{{A média é, media}}
K --> L([FIM]) 
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORITMO Media
DECLARE num1, num2, num3, num4, media: REAL

INICIO

    // Solicita ao usuário que digite o número 1
    ESCREVA "Digite o número 1:"

    // Lê o número 1 fornecido pelo usuário e armazena em 'num1'
    LEIA num1

    // Solicita ao usuário que digite o número 2
    ESCREVA "Digite o número 2:"

    // Lê o número 2 fornecido pelo usuário e armazena em 'num2'
    LEIA num2

    // Solicita ao usuário que digite o número 3
    ESCREVA "Digite o número 3:"

    // Lê o número 3 fornecido pelo usuário e armazena em 'num3'
    LEIA num3

    // Solicita ao usuário que digite o número 4
    ESCREVA "Digite o número 4:"

    // Lê o número 4 fornecido pelo usuário e armazena em 'num4'
    LEIA num4

    // Calcula a média dos quatro números fornecidos
    media <- (num1 + num2 + num3 + num4)/4

    // Exibe a média calculada
    ESCREVA "A média é", media

FIM

```

#### Teste de mesa (0.5 ponto)

| num1 | num2 | num3 | num4 | saída | 
| --   | --   | --   | --   | --    | 
| 0.25 | 0.25 | 2.50 | 1.00 | 1.00  | 

### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a temperatura em Celisus:"}}
B --> C[/C/]
C --> D["F = (9/5) * C + 32"]
D --> E{{A temperatura em Fahrenheit é, F, graus}}
E --> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORITMO ConverteCelsiusFarenheit
DECLARE C, F: REAL

INICIO

    // Solicita ao usuário que digite a temperatura em Celsius
    ESCREVA "Digite a temperatura em Celsius:"

    // Lê a temperatura em Celsius fornecida pelo usuário e armazena em 'C'
    LEIA C

    // Converte a temperatura de Celsius para Fahrenheit usando a fórmula de conversão
    F <- (9/5) * C + 32

    // Exibe a temperatura convertida em Fahrenheit
    ESCREVA "A temperatura em Fahrenheit é", F, "graus"

FIM

```

#### Teste de mesa (0.5 ponto)

| C  | F  | saída                                  | 
| -- | -- | --                                     |
| 0  | 32 | A temperatura em Fahrenheit é 32 graus |

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Operações válidas: 1(soma), 2(subtração), 3(multiplicação) e 4(divisão)"}}
B --> C{{Digite uma operação:}}
C --> D[/op/]
D --> E{{Digite um número:}}
E --> F[/num1/]
F --> G{{Digite outro número:}}
G --> H[/num2/]
H --> I{op == 1}
I --FALSE--> J{op == 2}
J --FALSE--> L{op == 3}
L --FALSE--> O{op == 4}
O --FALSE--> Q{{Operação inválida!}}
Q --> R([FIM])
I --TRUE--> M[res = num1 + num2]
M --> S{{num1, + , num2, =, res}}
J --TRUE--> K[res = num1 - num2]
K --> T{{num1, - , num2, =, res}}
L --TRUE--> N[res = num1 * num2]
N --> U{{num1, * , num2, =, res}}
O --TRUE--> P{num2 != 0}
P --FALSE--> X{{Impossível dividir!}}
P --TRUE--> Z[res = num1 / num2]
Z --> V{{num1, / , num2, =, res}}
X --> R
S --> R
T --> R
U --> R
V --> R
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORITMO CalculadoraSimples
DECLARE op: INTEIRO; num1, num2, res: REAL

INICIO

    // Exibe as operações válidas para o usuário
    ESCREVA "Operações válidas: 1 (soma), 2 (subtração), 3 (multiplicação) e 4 (divisão)"

    // Solicita ao usuário que digite a operação desejada
    ESCREVA "Digite uma operação:"
    
    // Lê a operação fornecida pelo usuário e armazena em 'op'
    LEIA op

    // Solicita ao usuário que digite o primeiro número
    ESCREVA "Digite um número:"
    
    // Lê o primeiro número fornecido pelo usuário e armazena em 'num1'
    LEIA num1

    // Solicita ao usuário que digite o segundo número
    ESCREVA "Digite outro número:"
    
    // Lê o segundo número fornecido pelo usuário e armazena em 'num2'
    LEIA num2

    // Realiza a escolha da operação de acordo com o valor de 'op'
    ESCOLHA

        // Caso a operação escolhida seja soma (op = 1)
        CASO op == 1

            // Calcula a soma dos dois números
            res = num1 + num2

            // Exibe o resultado da soma
            ESCREVA num1, "+", num2, "=", res

        // Caso a operação escolhida seja subtração (op = 2)
        CASO op == 2

            // Calcula a subtração dos dois números
            res = num1 - num2

            // Exibe o resultado da subtração
            ESCREVA num1, "-", num2, "=", res

        // Caso a operação escolhida seja multiplicação (op = 3)
        CASO op == 3

            // Calcula a multiplicação dos dois números
            res = num1 * num2

            // Exibe o resultado da multiplicação
            ESCREVA num1, "*", num2, "=", res

        // Caso a operação escolhida seja divisão (op = 4)
        CASO op == 4

            // Verifica se o segundo número é diferente de zero para evitar divisão por zero
            SE num2 != 0 ENTAO

                // Calcula a divisão dos dois números
                res = num1 / num2

                // Exibe o resultado da divisão
                ESCREVA num1, "/", num2, "=", res

            // Se o segundo número for zero, exibe uma mensagem de erro
            SENAO
                ESCREVA "Impossível dividir!"

            FIM_SE

    // Se a operação escolhida não estiver nos casos válidos, exibe uma mensagem de erro
    SENAO
        ESCREVA "Operação inválida!"

    FIM_ESCOLHA

FIM

```

#### Teste de mesa (0.5 ponto)

| num1 | num2 | op | num2 != 0 | res | saída               | 
| --   | --   | -- | --        | --  | --                  |
| 1    | 0    | 1  |           | 1   | 1 + 0 = 1           |
| 1    | 0    | 2  |           | 1   | 1 - 0 = 1           |
| 1    | 0    | 3  |           | 0   | 1 * 0 = 0           |
| 1    | 0    | 4  | False     |     | Impossível dividir! |
| 1    | 2    | 4  | True      | 0.5 | 1 / 2 = 0,5         |
| 1    | 2    | 5  |           |     | Operação inválida!  |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a idade do aluno:"}}
B --> C[/idade/]
C --> D{idade >=5 <br>E <br>idade <= 7}
D --FALSE--> F{idade >=8 <br>E <br>idade <= 10}
F --FALSE--> G{idade >=11 <br>E <br>idade <= 13}
G --FALSE--> H{idade >=14 <br>E <br>idade <= 17}
H --FALSE--> I{idade >=18}
I --FALSE--> P{{"Digite uma idade válida!"}}
P --> Z([FIM])
D --TRUE--> Q{{Infantial A}}
F --TRUE--> K{{"Infantial B"}}
G --TRUE--> L{{Juvenil A}}
H --TRUE--> M{{Juvenil B}}
I --TRUE--> N{{Adulto}}
Q --> Z
K --> Z
L --> Z
M --> Z
N --> Z
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO ClassificaCategoria
DECLARE idade: INTEIRO

INICIO

    // Solicita ao usuário que digite a idade do aluno
    ESCREVA "Digite a idade do aluno:"
    
    // Lê a idade fornecida pelo usuário e armazena em 'idade'
    LEIA idade

    // Realiza a escolha da categoria com base na idade do aluno
    ESCOLHA

        // Caso a idade esteja entre 5 e 7 anos
        CASO idade >= 5 E idade <= 7

            // Exibe a categoria correspondente
            ESCREVA "Infantil A"

        // Caso a idade esteja entre 8 e 10 anos
        CASO idade >= 8 E idade <= 10

            // Exibe a categoria correspondente
            ESCREVA "Infantil B"

        // Caso a idade esteja entre 11 e 13 anos
        CASO idade >= 11 E idade <= 13

            // Exibe a categoria correspondente
            ESCREVA "Juvenil A"

        // Caso a idade esteja entre 14 e 17 anos
        CASO idade >= 14 E idade <= 17

            // Exibe a categoria correspondente
            ESCREVA "Juvenil B"

        // Caso a idade seja 18 anos ou mais
        CASO idade >= 18

            // Exibe a categoria correspondente
            ESCREVA "Adulto"

    // Se a idade não estiver nos casos válidos, exibe uma mensagem de erro
    SENAO

        // Exibe uma mensagem de erro
        ESCREVA "Digite uma idade válida!"

    FIM_ESCOLHA

FIM

```

#### Teste de mesa (0.5 ponto)

| idade | idade >=8 E idade <= 10 | idade >=11 E idade <= 13 | idade >=14 E idade <= 17 | idade >=18 | saída                       | 
| --    | --                      | --                       | --                       | --         | --                          |
| 4     | False                   | False                    | False                    | False      | Digite uma idade válida!    |
| -4    | False                   | False                    | False                    | False      | Digite uma idade válida!    |
| 8     | True                    | False                    | False                    | False      | Infantial A                 |
| 11    | False                   | True                     | False                    | False      | Infantial B                 |
| 17    | False                   | False                    | True                     | False      | Infantial C                 |
| 21    | False                   | False                    | False                    | True       | Adulto                      |
