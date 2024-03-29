
# UNIFOR
**Nome**: Nome do estudante <br>
**Disciplina**: Raciocínio lógico algorítm

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
```
1  ALGORITMO calReajuste
2  DECLARE  sal, sal_reaj: real, prof: caractere
3  INICIO
4  LEIA sal, prof
5  ESCOLHA
6   CASO prof == “Técnico”		// caso 1
7     sal_reaj ← 1.5 * sal
8   CASO prof = “Gerente”		// caso 2
9     sal_reaj ← 1.3 * sal
10  SENÃO
11    sal_reaj ← 1.1 * sal
12 FIM_ESCOLHA
13 ESCREVA “Salário Reajustado = “, sal_reaj
14 FIM
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
A([INICIO]) --> B{{Digite quatro numeros inteiros:}}
B --> C[/N1, N2, N3, N4/]
C --> D[M = N1 + N2 + N3 + N4 / 4]
D --> E{{"A media é: " M}}
E --> F([FIM])

```

#### Pseudocódigo (1.0 ponto)

```
1. ALGORITMO Media
2. DECLARE N1, N2, N3, N4 INTEIROS
3. INICIO
4. ESCREVA "Digite quatro numeros inteiros: "
5. LEIA N1, N2, N3, N4
6. M = N1 + N2 + N3 + N4 / 4 
7. 	ESCREVA "A media é: " M
8. FIM_ALGORITIMO

```

#### Teste de mesa (0.5 ponto)

| N1 | N2 | N3 | N4 | M | SAIDA | 
|      --      |      --      |      --      |      --      |      --      |      --      | 
| 1  | 2 | 4  | 5 | 3 | "Média = 3" |
| 3  | 5 | 7  | 9 | 6 | "Média = 6" |


### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite uma temperatura em Celcius: }}
B --> C[/C/]
C --> D[F = 9 / 5 * C + 32]
D --> E{{"A temperatura em Fahrenheit é: " F}}
E --> F([FIM])

```

#### Pseudocódigo (1.0 ponto)

```
1. ALGORITMO ConverteCelsiusFarenheit
2. DECLARE C REAIS
3. INICIO
4. ESCREVA "Digite uma temperatura em Celcius: "
5. LEIA C
6. F = 9 / 5 * C + 32 ENTAO
7. 	ESCREVA "A temperatura em Fahrenheit é: " F
8. FIM_ALGORITIMO




```

#### Teste de mesa (0.5 ponto)

| Celcius | Fahrenheit | Saída | 
|      --      |      --      |      --      | 
| 24   |    75,2   | "A temperatura em Fahrenheit é 75,2"   |
| 15   |    59     | "A temperatura em Fahrenheit é 59 "    |

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
Algoritmo Calculadora
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite uma idade: }}
B --> C[/I1/]
C --> D{5 >= I1 <=7}
D --TRUE--> E{{Infantil A}}
E --> F([FIM])
D --FALSE--> G{8 >= I1 <= 10}
G --TRUE--> H{{Infantil B}}
H --> F
G --FALSE--> I{11 >= I1 <= 13}
I --TRUE--> J{{Juvenil A}}
J --> F
I --FALSE--> L{14 >= I1 <= 17}
L --TRUE--> K{{Juvenil B}}
K --> F
L --FALSE--> M{I1 >= 18}
M --> N{{Adulto}}
N --> F

```

#### Pseudocódigo (1.0 ponto)

```
1. Algoritmo ClassificaCategoria
2. DECLARE idade
3. INICIO
4. ESCREVA "Digite uma idade:"
5. LEIA idade
6. SE idade >= 5 E idade <= 7 ENTÃO
7.     ESCREVA "Infantil A"
8. SENÃO SE idade >= 8 E idade <= 10 ENTÃO
9.     ESCREVA "Infantil B"
10. SENÃO SE idade >= 11 E idade <= 13 ENTÃO
11.     ESCREVA "Juvenil A"
12. SENÃO SE idade >= 14 E idade <= 17 ENTÃO
13.     ESCREVA "Juvenil B"
14. SENÃO SE idade >= 18 ENTÃO
15.     ESCREVA "Adulto"
16. FIM_ALGORITMO

```

#### Teste de mesa (0.5 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |
