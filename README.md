# Gerador de Combinações da Mega-Sena em C

Programa em C que gera **todas as combinações possíveis de 6 números entre 1 e 60** (sem repetição e em ordem crescente), como na Mega-Sena, e confere se o total gerado bate com o valor matemático esperado.

## Como funciona

O programa usa **6 laços `for` aninhados**, um para cada dezena sorteada (`a`, `b`, `c`, `d`, `e`, `f`). Cada laço começa um valor acima do anterior, o que garante duas coisas:

- **Sem repetição:** nenhum número aparece duas vezes na mesma combinação.
- **Sem permutações:** `01 02 03 04 05 06` e `06 05 04 03 02 01` contam como a mesma combinação, então só a primeira é gerada.

Os limites superiores dos laços (55, 56, 57, 58, 59 e 60) garantem que sempre sobrem números suficientes para completar a combinação.

## Verificação matemática

O total de combinações é dado pela fórmula de combinação simples:

```
C(60, 6) = 60! / (6! × 54!) = 50.063.860
```

Ao final, o programa compara o contador com esse valor (`TOTAL = 50063860`) e exibe `OK` ou `ERRO`.

## Saída do programa

Para não imprimir 50 milhões de linhas, a saída é resumida:

| O que é exibido | Quando |
|---|---|
| As **20 primeiras** combinações | `contador <= 20` |
| As **5 últimas** combinações | `contador > TOTAL - 5` |
| Uma linha de **progresso** | a cada 10.000.000 de combinações |
| Um **resumo final** com a conferência | ao término da execução |

### Exemplo de saída

```
       1: 01 02 03 04 05 06
       2: 01 02 03 04 05 07
       ...
      20: 01 02 03 04 05 25
10000000: 03 07 15 41 52 58 (progresso)
...
50063860: 55 56 57 58 59 60

Total de combinacoes geradas: 50063860
Valor esperado C(60,6)......: 50063860
Conferencia: OK
```

> Os valores exatos das linhas de progresso podem ser diferentes dos mostrados acima.

## Como compilar e executar

Requisitos: um compilador C, como o **GCC**.

```bash
gcc -O2 -o combinacoes combinacoes.c
./combinacoes
```

No Windows (PowerShell ou CMD):

```bash
gcc -O2 -o combinacoes.exe combinacoes.c
combinacoes.exe
```

A flag `-O2` ativa otimizações e acelera bastante a execução, já que são mais de 50 milhões de iterações.

## Conceitos praticados

- Laços aninhados (`for`)
- Combinação simples (análise combinatória)
- Formatação de saída com `printf` (`%02d`, `%8ld`)
- Operador ternário
- Constantes (`const`) e tipo `long`
- Validação de resultado com valor teórico

## Estrutura do projeto

```
.
├── combinacoes.c
└── README.md
```

## Autor

Projeto desenvolvido para fins de estudo em lógica de programação e análise combinatória.
