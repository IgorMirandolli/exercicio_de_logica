# Resolucao do exercicio de logica proposicional

Notacao usada:

- `¬` = negacao
- `∧` = conjuncao
- `∨` = disjuncao
- `→` = condicional
- `↔` = bicondicional
- `⊢` = "prova-se que"

Nas provas, uso as regras usuais de introducao e eliminacao: `∧I`, `∧E`, `∨I`, `∨E`, `→I`, `→E`, `↔I`, `↔E`, `¬I`, `¬E`. Quando aparece `RAA`, trata-se da forma classica de eliminacao da negacao: prova por absurdo.

---

## 1. Interpretacao sentencial

Interpretacao:

- `C`: esta chovendo.
- `N`: esta nevando.

| # | Sentenca | Forma |
|---|---|---|
| 1 | Esta chovendo. | `C` |
| 2 | Nao esta chovendo. | `¬C` |
| 3 | Esta chovendo ou nevando. | `C ∨ N` |
| 4 | Esta chovendo e nevando. | `C ∧ N` |
| 5 | Esta chovendo, mas nao esta nevando. | `C ∧ ¬N` |
| 6 | Nao e o caso que esta chovendo e nevando. | `¬(C ∧ N)` |
| 7 | Se nao esta chovendo, entao esta nevando. | `¬C → N` |
| 8 | Nao e o caso que se esta chovendo entao esta nevando. | `¬(C → N)` |
| 9 | Nao e o caso que se esta nevando entao esta chovendo. | `¬(N → C)` |
| 10 | Esta chovendo se e somente se nao esta nevando. | `C ↔ ¬N` |
| 11 | Nao e o caso que esta chovendo ou nevando. | `¬(C ∨ N)` |
| 12 | Se esta nevando e chovendo, entao esta nevando. | `(N ∧ C) → N` |
| 13 | Se nao esta chovendo, entao nao e o caso que esta nevando e chovendo. | `¬C → ¬(N ∧ C)` |
| 14 | Ou esta chovendo, ou esta nevando e chovendo. | `C ∨ (N ∧ C)` |
| 15 | Ou esta chovendo e nevando, ou esta nevando mas nao esta chovendo. | `(C ∧ N) ∨ (N ∧ ¬C)` |

Observacao: no calculo proposicional basico, `∨` costuma ser inclusivo. Se o professor exigir "ou exclusivo", o item 14 ficaria `((C ∨ (N ∧ C)) ∧ ¬(C ∧ (N ∧ C)))`.

---

## 2. Formalizacao de enunciados

Interpretacao:

- `P`: Paula vai.
- `Q`: Quincas vai.
- `R`: Richard vai.
- `S`: Sara vai.

| # | Enunciado | Forma |
|---|---|---|
| 1 | Paula nao vai. | `¬P` |
| 2 | Paula vai, mas Quincas nao. | `P ∧ ¬Q` |
| 3 | Se Paula for, entao Quincas tambem ira. | `P → Q` |
| 4 | Paula ira, se Quincas for. | `Q → P` |
| 5 | Paula ira, somente se Quincas for. | `P → Q` |
| 6 | Paula ira, se e somente se Quincas for. | `P ↔ Q` |
| 7 | Nem Paula nem Quincas irao. | `¬P ∧ ¬Q` |
| 8 | Paula e Quincas nao irao. | `¬P ∧ ¬Q` |
| 9 | Ou Paula vai ou Quincas nao vai. | `P ∨ ¬Q` |
| 10 | Paula nao ira se Quincas for. | `Q → ¬P` |
| 11 | Ou Paula ira, ou Richard e Quincas irao. | `P ∨ (R ∧ Q)` |
| 12 | Se Paula for, entao Richard e Quincas irao. | `P → (R ∧ Q)` |
| 13 | Paula nao ira, mas Richard e Quincas irao. | `¬P ∧ (R ∧ Q)` |
| 14 | Se Richard for, entao se Paula nao for, Quincas ira. | `R → (¬P → Q)` |
| 15 | Se nem Richard nem Quincas forem, entao Paula ira. | `(¬R ∧ ¬Q) → P` |
| 16 | Richard ira somente se Paula e Quincas nao forem. | `R → (¬P ∧ ¬Q)` |
| 17 | Richard e Quincas vao, apesar de Paula e Quincas nao irem. | `(R ∧ Q) ∧ (¬P ∧ ¬Q)` |
| 18 | Se Richard ou Quincas for, entao Paula ira e Sara nao ira. | `(R ∨ Q) → (P ∧ ¬S)` |
| 19 | Richard e Quincas irao se e somente se Paula ou Sara for. | `(R ∧ Q) ↔ (P ∨ S)` |
| 20 | Se Sara for, entao Richard ou Paula irao, e se Sara nao for, entao Paula e Quincas irao. | `(S → (R ∨ P)) ∧ (¬S → (P ∧ Q))` |

Observacao sobre o item 8: se a frase fosse entendida como "Paula e Quincas nao irao ambos", a forma seria `¬(P ∧ Q)`. Pela leitura literal em portugues, fica `¬P ∧ ¬Q`.

---

## 3. Formulas bem formadas

| # | Formula | E fbf? | Justificativa |
|---|---|---|---|
| 1 | `¬` | Nao | A negacao precisa operar sobre uma formula. |
| 2 | `(¬P)` | Sim | `P` e atomica; `¬P` e formula; parenteses externos sao permitidos. |
| 3 | `P - Q` | Nao | `-` nao e conectivo da linguagem. |
| 4 | `(P P)` | Nao | Faltou conectivo entre as duas ocorrencias de `P`. |
| 5 | `P P` | Nao | Duas formulas justapostas nao formam uma formula. |
| 6 | `¬¬(¬P ∧ Q)` | Sim | `¬P` e `Q` sao formulas; `¬P ∧ Q` tambem; duas negacoes preservam fbf. |
| 7 | `((P → Q))` | Sim | `P → Q` e formula; parenteses extras nao atrapalham. |
| 8 | `¬(P ∧ Q) ∧ ¬R` | Sim | Conjuncao de duas formulas bem formadas. |
| 9 | `(P ↔ (P ↔ (P ↔ P)))` | Sim | Bicondicionais binarios corretamente formados. |
| 10 | `(P(Q(R ∧ S)))` | Nao | A linguagem nao tem aplicacao de formulas como funcoes; faltam conectivos. |
| 11 | `(P(Q ∨ R ∨ S))` | Nao | Falta conectivo entre `P` e o bloco seguinte; alem disso, `Q ∨ R ∨ S` exige associacao explicita. |

---

## 4. Argumentos

Interpretacao:

- `C`: a conclusao deste argumento e verdadeira.
- `P`: as premissas deste argumento sao verdadeiras.
- `S`: este argumento e correto.
- `V`: este argumento e valido.

Uso:

- "incorreto" = `¬S`
- "invalido" = `¬V`
- "nem todas as premissas sao verdadeiras" = `¬P`
- "conclusao nao verdadeira" = `¬C`

### 4.1

Forma: `¬¬S ⊢ S`

Prova:

1. `¬¬S` premissa  
2. `S` por `¬E` em 1

### 4.2

Forma: `S ⊢ ¬¬S`

Prova:

1. `S` premissa  
2. Suponha `¬S`  
3. Contradicao entre 1 e 2  
4. `¬¬S` por `¬I`

### 4.3

Forma: `S → V, ¬V ⊢ ¬S`

Prova:

1. `S → V` premissa  
2. `¬V` premissa  
3. Suponha `S`  
4. `V` por `→E`, 1 e 3  
5. Contradicao entre 2 e 4  
6. `¬S` por `¬I`

### 4.4

Forma: `S → ¬¬V, S ⊢ V`

Prova:

1. `S → ¬¬V` premissa  
2. `S` premissa  
3. `¬¬V` por `→E`, 1 e 2  
4. `V` por `¬E`, 3

### 4.5

Forma: `S → ¬¬V ⊢ ¬V → ¬S`

Prova:

1. `S → ¬¬V` premissa  
2. Suponha `¬V`  
3. Suponha `S`  
4. `¬¬V` por `→E`, 1 e 3  
5. Contradicao entre 2 e 4  
6. `¬S` por `¬I`  
7. `¬V → ¬S` por `→I`

### 4.6

Forma: `S ∧ V ⊢ S ∨ ¬V`

Prova:

1. `S ∧ V` premissa  
2. `S` por `∧E`, 1  
3. `S ∨ ¬V` por `∨I`, 2

### 4.7

Forma: `¬(S ∧ ¬V), S ⊢ V`

Prova:

1. `¬(S ∧ ¬V)` premissa  
2. `S` premissa  
3. Suponha `¬V`  
4. `S ∧ ¬V` por `∧I`, 2 e 3  
5. Contradicao entre 1 e 4  
6. `V` por RAA

### 4.8

Forma: `S ↔ P, ¬P ⊢ ¬S`

Prova:

1. `S ↔ P` premissa  
2. `¬P` premissa  
3. Suponha `S`  
4. `S → P` por `↔E`, 1  
5. `P` por `→E`, 3 e 4  
6. Contradicao entre 2 e 5  
7. `¬S` por `¬I`

### 4.9

Forma: `¬C → ¬S ⊢ ¬(S ∧ ¬C)`

Prova:

1. `¬C → ¬S` premissa  
2. Suponha `S ∧ ¬C`  
3. `S` por `∧E`, 2  
4. `¬C` por `∧E`, 2  
5. `¬S` por `→E`, 1 e 4  
6. Contradicao entre 3 e 5  
7. `¬(S ∧ ¬C)` por `¬I`

### 4.10

Forma: `(¬S ∧ V) → ¬P, P, V ⊢ S`

Prova:

1. `(¬S ∧ V) → ¬P` premissa  
2. `P` premissa  
3. `V` premissa  
4. Suponha `¬S`  
5. `¬S ∧ V` por `∧I`, 4 e 3  
6. `¬P` por `→E`, 1 e 5  
7. Contradicao entre 2 e 6  
8. `S` por RAA

### 4.11

Forma: `(V ∧ P) → S, S → C, P ⊢ V → C`

Prova:

1. `(V ∧ P) → S` premissa  
2. `S → C` premissa  
3. `P` premissa  
4. Suponha `V`  
5. `V ∧ P` por `∧I`, 4 e 3  
6. `S` por `→E`, 1 e 5  
7. `C` por `→E`, 2 e 6  
8. `V → C` por `→I`

### 4.12

Forma: `¬S ∨ (V ∧ P) ⊢ ¬S ∨ V`

Prova:

1. `¬S ∨ (V ∧ P)` premissa  
2. Caso `¬S`: obtenha `¬S ∨ V` por `∨I`  
3. Caso `V ∧ P`: obtenha `V` por `∧E`, depois `¬S ∨ V` por `∨I`  
4. `¬S ∨ V` por `∨E`, 1, 2 e 3

### 4.13

Forma: `S ↔ (V ∧ P), ¬P ⊢ ¬S`

Prova:

1. `S ↔ (V ∧ P)` premissa  
2. `¬P` premissa  
3. Suponha `S`  
4. `S → (V ∧ P)` por `↔E`, 1  
5. `V ∧ P` por `→E`, 3 e 4  
6. `P` por `∧E`, 5  
7. Contradicao entre 2 e 6  
8. `¬S` por `¬I`

### 4.14

Forma: `S ↔ (V ∧ P) ⊢ V → (P → S)`

Prova:

1. `S ↔ (V ∧ P)` premissa  
2. `(V ∧ P) → S` por `↔E`, 1  
3. Suponha `V`  
4. Suponha `P`  
5. `V ∧ P` por `∧I`, 3 e 4  
6. `S` por `→E`, 2 e 5  
7. `P → S` por `→I`  
8. `V → (P → S)` por `→I`

### 4.15

Forma: `¬S → (¬P ∨ ¬V), V ∧ P ⊢ S`

Prova:

1. `¬S → (¬P ∨ ¬V)` premissa  
2. `V ∧ P` premissa  
3. `V` por `∧E`, 2  
4. `P` por `∧E`, 2  
5. Suponha `¬S`  
6. `¬P ∨ ¬V` por `→E`, 1 e 5  
7. Caso `¬P`: contradicao com 4  
8. Caso `¬V`: contradicao com 3  
9. Contradicao por `∨E`, 6, 7 e 8  
10. `S` por RAA

---

## 5. Validade de formas de argumento

### 5.1

Forma: `P → Q, Q → R ⊢ P → R`

Prova: suponha `P`; de `P → Q`, obtenha `Q`; de `Q → R`, obtenha `R`; logo `P → R`.

### 5.2

Forma: `P ↔ Q ⊢ ¬P ↔ ¬Q`

Prova: de `P ↔ Q`, obtenha `P → Q` e `Q → P`.  
Para `¬P → ¬Q`: suponha `¬P`; suponha `Q`; por `Q → P`, obtenha `P`, contradicao; logo `¬Q`.  
Para `¬Q → ¬P`: suponha `¬Q`; suponha `P`; por `P → Q`, obtenha `Q`, contradicao; logo `¬P`.  
Portanto, `¬P ↔ ¬Q`.

### 5.3

Forma: `¬P ∨ Q ⊢ ¬(P ∧ ¬Q)`

Prova: suponha `P ∧ ¬Q`. Entao `P` e `¬Q`. Pela premissa, casos: se `¬P`, ha contradicao com `P`; se `Q`, ha contradicao com `¬Q`. Logo `¬(P ∧ ¬Q)`.

### 5.4

Forma: `P → Q, P → ¬Q ⊢ ¬P`

Prova: suponha `P`; obtenha `Q` pela primeira premissa e `¬Q` pela segunda. Contradicao. Logo `¬P`.

### 5.5

Forma: `(P → Q) ∧ (P → R) ⊢ P → (Q ∧ R)`

Prova: extraia `P → Q` e `P → R`; suponha `P`; obtenha `Q` e `R`; conclua `Q ∧ R`; logo `P → (Q ∧ R)`.

### 5.6

Forma: `P → Q ⊢ (P ∧ R) → (Q ∧ R)`

Prova: suponha `P ∧ R`; extraia `P` e `R`; de `P → Q`, obtenha `Q`; conclua `Q ∧ R`.

### 5.7

Forma: `P → Q ⊢ (P ∨ R) → (Q ∨ R)`

Prova: suponha `P ∨ R`. Por casos: se `P`, entao `Q`, logo `Q ∨ R`; se `R`, logo `Q ∨ R`. Portanto, `(P ∨ R) → (Q ∨ R)`.

### 5.8

Forma: `¬P → P ⊢ P`

Prova: suponha `¬P`; pela premissa, obtenha `P`; contradicao. Por RAA, conclua `P`.

### 5.9

Forma: `¬P ⊢ P → Q`

Prova: suponha `P`; ha contradicao com `¬P`; por explosao, obtenha `Q`; logo `P → Q`.

### 5.10

Forma: `P ∧ Q ⊢ P → Q`

Prova: suponha `P`; de `P ∧ Q`, obtenha `Q`; logo `P → Q`.

---

## 6. Teoremas

### 6.1

Teorema: `⊢ P → P`

Prova: suponha `P`; conclua `P`; logo `P → P`.

### 6.2

Teorema: `⊢ P → (Q → (P ∧ Q))`

Prova: suponha `P`; suponha `Q`; forme `P ∧ Q`; logo `Q → (P ∧ Q)`; logo `P → (Q → (P ∧ Q))`.

### 6.3

Teorema: `⊢ ¬(P ↔ ¬P)`

Prova: suponha `P ↔ ¬P`. Entao `P → ¬P` e `¬P → P`.  
Suponha `P`; obtenha `¬P`; contradicao; logo `¬P`.  
De `¬P → P`, obtenha `P`; contradicao.  
Logo `¬(P ↔ ¬P)`.

### 6.4

Teorema: `⊢ (P → Q) → (¬Q → ¬P)`

Prova: suponha `P → Q`; suponha `¬Q`; suponha `P`; obtenha `Q`; contradicao com `¬Q`; logo `¬P`; portanto `¬Q → ¬P`; portanto `(P → Q) → (¬Q → ¬P)`.

### 6.5

Teorema: `⊢ (P ∧ Q) ∨ (¬P ∨ ¬Q)`

Prova: use terceiro excluido para `P`.  
Se `¬P`, conclua `¬P ∨ ¬Q`, logo a disjuncao maior.  
Se `P`, use terceiro excluido para `Q`: se `Q`, conclua `P ∧ Q`; se `¬Q`, conclua `¬P ∨ ¬Q`. Em ambos os casos, conclua `(P ∧ Q) ∨ (¬P ∨ ¬Q)`.

### 6.6

Teorema: `⊢ Q → (P ∨ ¬P)`

Prova: suponha `Q`; pelo terceiro excluido, `P ∨ ¬P`; logo `Q → (P ∨ ¬P)`.

### 6.7

Teorema: `⊢ (P ∧ ¬P) → Q`

Prova: suponha `P ∧ ¬P`; obtenha `P` e `¬P`; por explosao, conclua `Q`; logo `(P ∧ ¬P) → Q`.

### 6.8

Teorema: `⊢ P ∨ (P → Q)`

Prova: pelo terceiro excluido, `P ∨ ¬P`.  
Se `P`, conclua `P ∨ (P → Q)`.  
Se `¬P`, suponha `P`; contradicao; por explosao, `Q`; logo `P → Q`; conclua `P ∨ (P → Q)`.

### 6.9

Teorema: `⊢ ¬P ∨ (Q → P)`

Prova: pelo terceiro excluido, `P ∨ ¬P`.  
Se `¬P`, conclua `¬P ∨ (Q → P)`.  
Se `P`, suponha `Q`; conclua `P`; logo `Q → P`; conclua `¬P ∨ (Q → P)`.

### 6.10

Teorema: `⊢ (P → Q) ∨ (Q → P)`

Prova: pelo terceiro excluido, `P ∨ ¬P`.  
Se `P`, suponha `Q`; conclua `P`; logo `Q → P`; conclua a disjuncao.  
Se `¬P`, suponha `P`; contradicao; por explosao, `Q`; logo `P → Q`; conclua a disjuncao.

---

## 7. Equivalencias

Atencao: os itens 7.1 e 7.4, exatamente como aparecem no enunciado enviado, nao sao teoremas. Nao ha prova valida para formulas que nao sao tautologias.

### 7.1

Formula enviada: `⊢ ¬(P ∧ Q) ↔ ¬(¬P ∨ ¬Q)`

Status: nao e teorema.

Contraexemplo: tome `P = V` e `Q = F`.

- `¬(P ∧ Q)` fica verdadeira.
- `¬(¬P ∨ ¬Q)` fica falsa.

Portanto, a bicondicional e falsa nessa avaliacao.

Provavel correcao: `⊢ ¬(P ∧ Q) ↔ (¬P ∨ ¬Q)`.

### 7.2

Teorema: `⊢ (P ∨ Q) ↔ ¬(¬P ∧ ¬Q)`

Prova abreviada:

- De `P ∨ Q`, suponha `¬P ∧ ¬Q`; se `P`, contradicao com `¬P`; se `Q`, contradicao com `¬Q`; logo `¬(¬P ∧ ¬Q)`.
- De `¬(¬P ∧ ¬Q)`, por RAA, se `¬(P ∨ Q)`, entao `¬P` e `¬Q`; logo `¬P ∧ ¬Q`, contradicao. Portanto `P ∨ Q`.
- Conclua a bicondicional por `↔I`.

### 7.3

Teorema: `⊢ (P ∧ Q) ↔ ¬(P → ¬Q)`

Prova abreviada:

- De `P ∧ Q`, extraia `P` e `Q`. Se `P → ¬Q`, entao `¬Q`, contradicao. Logo `¬(P → ¬Q)`.
- De `¬(P → ¬Q)`, obtenha `P`; pois, se `¬P`, entao `P → ¬Q` por prova condicional e explosao, contradicao. Obtenha tambem `Q`; pois, se `¬Q`, entao `P → ¬Q`, contradicao. Logo `P ∧ Q`.
- Conclua por `↔I`.

### 7.4

Formula enviada: `⊢ ¬(P ∨ Q) ↔ ¬P → Q`

Status: nao e teorema.

Contraexemplo: tome `P = F` e `Q = F`.

- `¬(P ∨ Q)` fica verdadeira.
- `¬P → Q` fica falsa.

Logo, a bicondicional e falsa.

Provavel correcao: `⊢ ¬(P ∨ Q) ↔ (¬P ∧ ¬Q)`.

### 7.5

Teorema: `⊢ P ↔ ((P ∧ Q) ∨ (P ∧ ¬Q))`

Prova abreviada:

- De `P`, use terceiro excluido `Q ∨ ¬Q`. Se `Q`, forme `P ∧ Q`; se `¬Q`, forme `P ∧ ¬Q`; em ambos os casos, conclua `(P ∧ Q) ∨ (P ∧ ¬Q)`.
- De `(P ∧ Q) ∨ (P ∧ ¬Q)`, por casos, extraia `P` em qualquer lado.
- Conclua por `↔I`.

### 7.6

Teorema: `⊢ ¬(P → Q) ↔ (P ∧ ¬Q)`

Prova abreviada:

- De `¬(P → Q)`, prove `P` por RAA: se `¬P`, entao `P → Q`, contradicao. Prove `¬Q`: se `Q`, entao `P → Q`, contradicao. Logo `P ∧ ¬Q`.
- De `P ∧ ¬Q`, se `P → Q`, obtenha `Q`, contradicao com `¬Q`; logo `¬(P → Q)`.
- Conclua por `↔I`.

### 7.7

Teorema: `⊢ (P ↔ Q) ↔ ((P ∧ Q) ∨ (¬P ∧ ¬Q))`

Prova abreviada:

- De `P ↔ Q`, use terceiro excluido em `P`. Se `P`, obtenha `Q` e forme `P ∧ Q`; se `¬P`, mostre `¬Q`, pois `Q` implicaria `P`; forme `¬P ∧ ¬Q`.
- De `((P ∧ Q) ∨ (¬P ∧ ¬Q))`, por casos, mostre `P → Q` e `Q → P`; conclua `P ↔ Q`.
- Conclua por `↔I`.

### 7.8

Teorema: `⊢ ¬(P ↔ Q) ↔ ((¬P ∧ Q) ∨ (P ∧ ¬Q))`

Prova abreviada:

- De `¬(P ↔ Q)`, use casos sobre `P` e `Q`. Os casos `P ∧ Q` e `¬P ∧ ¬Q` produziriam `P ↔ Q`, contradicao; restam `¬P ∧ Q` ou `P ∧ ¬Q`.
- De `((¬P ∧ Q) ∨ (P ∧ ¬Q))`, qualquer caso impede `P ↔ Q`: no primeiro, `Q → P` falha; no segundo, `P → Q` falha. Logo `¬(P ↔ Q)`.
- Conclua por `↔I`.

### 7.9

Teorema: `⊢ (P ↔ ¬P) ↔ (Q ∧ ¬Q)`

Prova abreviada:

- Ja foi provado em 6.3 que `¬(P ↔ ¬P)`. Assim, de `P ↔ ¬P`, segue contradicao; por explosao, obtenha `Q` e `¬Q`; logo `Q ∧ ¬Q`.
- De `Q ∧ ¬Q`, por explosao, obtenha as duas condicionais `P → ¬P` e `¬P → P`; logo `P ↔ ¬P`.
- Conclua por `↔I`.

### 7.10

Teorema: `⊢ (P ∨ ¬P) ↔ (Q ∨ ¬Q)`

Prova abreviada:

- Para `P ∨ ¬P → Q ∨ ¬Q`, suponha `P ∨ ¬P`; pelo terceiro excluido, conclua diretamente `Q ∨ ¬Q`.
- Para `Q ∨ ¬Q → P ∨ ¬P`, suponha `Q ∨ ¬Q`; pelo terceiro excluido, conclua diretamente `P ∨ ¬P`.
- Conclua por `↔I`.

