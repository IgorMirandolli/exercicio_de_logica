# Exercicios 2 - Logica proposicional

Notacao:

- `¬` = nao
- `∧` = e
- `∨` = ou
- `→` = se... entao
- `↔` = se e somente se
- `⊢` = portanto / prova-se que

Leitura adotada para "A, a menos que B": `¬B → A`.

---

## 1. Formalizacao e validade dos argumentos

### 1.1 Deus e significado da vida

Interpretacao:

- `D`: Deus existe.
- `S`: a vida tem significado.

Formalizacao:

1. `D → S`
2. `¬S`
3. Portanto, `¬D`

Forma: `D → S, ¬S ⊢ ¬D`

Validade: valido.

Justificativa: e um caso de modus tollens. Se `D` fosse verdadeiro, `S` seria verdadeiro; como `S` e falso, `D` tambem deve ser falso.

---

### 1.2 Garoa, neve e ceu claro

Interpretacao:

- `G`: esta garoando.
- `N`: esta nevando.
- `C`: o ceu esta claro.

Formalizacao:

1. `(G ∨ N) → ¬C`
2. `¬¬C`
3. Portanto, `¬(G ∨ N)`

Forma: `(G ∨ N) → ¬C, ¬¬C ⊢ ¬(G ∨ N)`

Validade: valido.

Prova curta:

1. `(G ∨ N) → ¬C` premissa
2. `¬¬C` premissa
3. `C` por eliminacao da dupla negacao em 2
4. Suponha `G ∨ N`
5. `¬C` por `→E`, 1 e 4
6. Contradicao entre 3 e 5
7. `¬(G ∨ N)` por `¬I`

---

### 1.3 Chuva e nuvens

Interpretacao:

- `C`: esta chovendo.
- `N`: ha nuvens no ceu.

Formalizacao:

1. `C → N`
2. `¬N`
3. Portanto, `¬C`

Forma: `C → N, ¬N ⊢ ¬C`

Validade: valido.

Justificativa: e outro caso de modus tollens.

---

### 1.4 Contraposicao

Interpretacao:

- `P`: P e verdadeiro.
- `Q`: Q e verdadeiro.

Formalizacao:

1. `P → Q`
2. Portanto, `¬Q → ¬P`

Forma: `P → Q ⊢ ¬Q → ¬P`

Validade: valido.

Prova curta:

1. `P → Q` premissa
2. Suponha `¬Q`
3. Suponha `P`
4. `Q` por `→E`, 1 e 3
5. Contradicao entre 2 e 4
6. `¬P` por `¬I`
7. `¬Q → ¬P` por `→I`

---

### 1.5 Paulo em Dublin

Interpretacao:

- `D`: Paulo vive em Dublin.
- `F`: Paulo esta feliz.
- `T`: Paulo gosta do seu trabalho.
- `B`: Paulo ira se dar bem no trabalho.
- `A`: Paulo se apaixona.

Formalizacao:

1. `D → F`
2. `(F ∧ T) → (¬A → B)`
3. `A → T`
4. Portanto, `D → B`

Forma: `D → F, (F ∧ T) → (¬A → B), A → T ⊢ D → B`

Validade: invalido.

Contraexemplo:

Considere:

- `D = V`
- `F = V`
- `A = V`
- `T = V`
- `B = F`

Verificacao:

- `D → F` e verdadeira.
- `(F ∧ T) → (¬A → B)` e verdadeira, pois `¬A` e falso.
- `A → T` e verdadeira.
- Mas `D → B` e falsa, pois `D` e verdadeiro e `B` e falso.

Logo, as premissas podem ser verdadeiras e a conclusao falsa. O argumento e invalido.

---

### 1.6 Espanha, Irlanda e Dinamarca

Interpretacao:

- `E`: a Espanha atingiu as finais da Copa do Mundo.
- `I`: a Irlanda cometeu erros.
- `D`: a Dinamarca jogou muito bem.

Formalizacao:

1. `E → (I ∨ D)`
2. `¬E → ¬I`
3. `¬D`
4. Portanto, `E ↔ I`

Forma: `E → (I ∨ D), ¬E → ¬I, ¬D ⊢ E ↔ I`

Validade: valido.

Prova curta:

1. `E → (I ∨ D)` premissa
2. `¬E → ¬I` premissa
3. `¬D` premissa
4. Suponha `E`
5. `I ∨ D` por `→E`, 1 e 4
6. Por casos em 5: se `I`, conclua `I`; se `D`, contradicao com 3, logo `I`
7. `E → I` por `→I`
8. Suponha `I`
9. Suponha `¬E`
10. `¬I` por `→E`, 2 e 9
11. Contradicao entre 8 e 10
12. `E` por RAA
13. `I → E` por `→I`
14. `E ↔ I` por `↔I`, 7 e 13

---

### 1.7 Joana e a formatura

Interpretacao:

- `G`: Joana ira se formar.
- `M`: Joana se matriculou como estudante de musica.
- `A`: Joana comparece a um numero satisfatorio de aulas.
- `E`: Joana tem exito em todas as provas.

Formalizacao:

1. `(M ∧ A) → G`
2. `¬E → ¬G`
3. `A → E`
4. `M`
5. Portanto, `G`

Forma: `(M ∧ A) → G, ¬E → ¬G, A → E, M ⊢ G`

Validade: invalido.

Contraexemplo:

Considere:

- `M = V`
- `A = F`
- `E = V`
- `G = F`

Verificacao:

- `(M ∧ A) → G` e verdadeira, pois `M ∧ A` e falso.
- `¬E → ¬G` e verdadeira, pois `¬E` e falso.
- `A → E` e verdadeira, pois `A` e falso.
- `M` e verdadeira.
- Mas `G` e falsa.

Logo, o argumento e invalido. Falta uma premissa afirmando que Joana compareceu a um numero satisfatorio de aulas.

---

### 1.8 Festa

Interpretacao:

- `B`: Barbara ira para a festa.
- `J`: Joana ira para a festa.
- `C`: Clara ira para a festa.
- `E`: Estevao ira para a festa.

Formalizacao:

1. `B ∧ J`
2. `J → (E → C)`
3. `J → E`
4. `C → J`
5. Portanto, `C`

Forma: `B ∧ J, J → (E → C), J → E, C → J ⊢ C`

Validade: valido.

Prova curta:

1. `B ∧ J` premissa
2. `J → (E → C)` premissa
3. `J → E` premissa
4. `C → J` premissa
5. `J` por `∧E`, 1
6. `E → C` por `→E`, 2 e 5
7. `E` por `→E`, 3 e 5
8. `C` por `→E`, 6 e 7

Observacao: a premissa `C → J` nao e necessaria para a conclusao, mas nao prejudica a validade.

---

## 2. Provas no calculo proposicional

### 2.1

Deducao: `(P ∧ Q) ∧ R ⊢ P ∧ (Q ∧ R)`

Prova:

1. `(P ∧ Q) ∧ R` premissa
2. `P ∧ Q` por `∧E`, 1
3. `R` por `∧E`, 1
4. `P` por `∧E`, 2
5. `Q` por `∧E`, 2
6. `Q ∧ R` por `∧I`, 5 e 3
7. `P ∧ (Q ∧ R)` por `∧I`, 4 e 6

---

### 2.2

Deducao: `(P ∧ Q) → R ⊢ P → (Q → R)`

Prova:

1. `(P ∧ Q) → R` premissa
2. Suponha `P`
3. Suponha `Q`
4. `P ∧ Q` por `∧I`, 2 e 3
5. `R` por `→E`, 1 e 4
6. `Q → R` por `→I`, 3-5
7. `P → (Q → R)` por `→I`, 2-6

---

### 2.3

Deducao: `¬P ∨ ¬Q ⊢ ¬(P ∧ Q)`

Prova:

1. `¬P ∨ ¬Q` premissa
2. Suponha `P ∧ Q`
3. `P` por `∧E`, 2
4. `Q` por `∧E`, 2
5. Caso `¬P`: contradicao com 3
6. Caso `¬Q`: contradicao com 4
7. Contradicao por `∨E`, 1, 5 e 6
8. `¬(P ∧ Q)` por `¬I`, 2-7

---

### 2.4

Deducao: `P → (Q → R) ⊢ (P ∧ Q) → R`

Prova:

1. `P → (Q → R)` premissa
2. Suponha `P ∧ Q`
3. `P` por `∧E`, 2
4. `Q` por `∧E`, 2
5. `Q → R` por `→E`, 1 e 3
6. `R` por `→E`, 5 e 4
7. `(P ∧ Q) → R` por `→I`, 2-6

---

### 2.5

Deducao: `P ∧ Q ⊢ Q ∧ P`

Prova:

1. `P ∧ Q` premissa
2. `P` por `∧E`, 1
3. `Q` por `∧E`, 1
4. `Q ∧ P` por `∧I`, 3 e 2

---

### 2.6

Deducao: `P ∨ Q, ¬P ⊢ Q`

Prova:

1. `P ∨ Q` premissa
2. `¬P` premissa
3. Caso `P`: contradicao com 2; por explosao, conclua `Q`
4. Caso `Q`: conclua `Q`
5. `Q` por `∨E`, 1, 3 e 4

---

### 2.7

Deducao: `P → Q ⊢ ¬Q → ¬P`

Prova:

1. `P → Q` premissa
2. Suponha `¬Q`
3. Suponha `P`
4. `Q` por `→E`, 1 e 3
5. Contradicao entre 2 e 4
6. `¬P` por `¬I`, 3-5
7. `¬Q → ¬P` por `→I`, 2-6

