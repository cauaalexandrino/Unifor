
# UNIFOR
**Nome**: Cauã Alexandrino Araújo Basile <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (0,5 ponto)
```
1  ALGORTIMO verifica_par_impar
2  DECLARE numero, resto: INTEIRO
3  ESCREVA "Digite um número: "
4  INICIO
4  LEIA numero
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"
9    SENAO
10     ESCREVA "O número é impar!"
11   FIM_SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"
13  FIM_SE
13 FIM
```

#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um salário:}}
B --> C[\ㅤ Sa ㅤ\]
C --> D{S >= 500}
D --TRUE--> E[Sa * 1.1 = Sn]
D --FALSE--> F[Sa * 1.2 = Sn]
E --> G{{Sn}}
F --> G
G --> H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
1. ALGORITMO verificar_NOVO_SALARIO
2. DECLARE Sa, Sn NUMERICOS
3. ESCREVA "Digite seu salario atual: "
4. LEIA Sa
5. SE Sa >= 500 ENTAO
6. 	Sn = Sa * 1.1
7. SENAO
8. 	Sn = Sa * 1.2
9. ESCREVA "Seu novo salario é: ", Sn
10. FIM_ALGORITMO
```

#### Teste de mesa (1.0 ponto)

| Salário | Sa >= 500 | Saída |
|      --      |      --      |      --      |     
| 600     | V       | Sn = Sa * 1.1    |  
| 450   | F          | Sn = Sa * 1.2        | 

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite a primeira nota: }}
B --> C[/Nota1/]
C --> D{{Digite a segunda nota: }}
D --> E[/Nota2/]
E --> F[MEDIA == Nota1 + Nota2 / 2]
F --> G{MEDIA >= 5}
G --TRUE--> H[O aluno está aprovado com media: MEDIA]
G --FALSE--> I[O aluno está reprovado com media: MEDIA]
H --> J([FIM])
I --> J

```

#### Pseudocódigo (1 ponto)

```
1. Algoritmo ContaAprovacoes
2. DECLARE Nota1, Nota2, MEDIA
3. INICIO
4. ESCREVA "Digite a primeira nota:"
5. LEIA Nota1
6. ESCREVA "Digite a segunda nota:"
7. LEIA Nota2
8. MEDIA ← (Nota1 + Nota2) / 2
9. SE MEDIA >= 5 ENTÃO
10.     ESCREVA "O aluno está aprovado com média:", MEDIA
11. SENÃO
12.     ESCREVA "O aluno está reprovado com média:", MEDIA
13. FIM_ALGORITIMO

```

#### Teste de mesa (1 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO])--> B{{Declare uma idade}}
B --> C[/Idade/]
C --> D{Idade >= 18}
D --TRUE--> E{{Já pode retirar a CNH}}
D --FALSE--> F[TF = 18 - Idade]
F --> G{{Deve esperar o TF anos para poder tirar a CNH}}
E --> I([FIM])
G --> I

```  

#### Pseudocódigo (1.0 ponto)

```
1. Algoritmo ContaAprovacoes
2. DECLARE Idade, TF
3. INICIO
4. ESCREVA "Declare uma idade:"
5. LEIA Idade
6. SE Idade >= 18 ENTÃO
7.     ESCREVA "Você já pode tirar a CNH."
8. SENÃO
9.     TF ← 18 - Idade
10.    ESCREVA "Você deve esperar ", TF, " anos para poder tirar a CNH."
11. FIM_ALGORITMO

```

#### Teste de mesa (1.0 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |
