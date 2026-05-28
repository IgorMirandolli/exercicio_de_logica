# Exercicios 3 - Logica proposicional

Notacao:

- `¬` = nao
- `∧` = e
- `∨` = ou
- `→` = se... entao
- `↔` = se e somente se
- `⊢` = portanto / prova-se que

---

## 1. Formalizacao e validade dos argumentos

### 1.1 Ligacao, e-mail e ficar em casa

Interpretacao:

- `L`: me ligaram.
- `E`: me mandaram um e-mail.
- `G`: estou gripado.
- `F`: tem um filme bom na TV.
- `C`: fiquei/fico em casa.

Formalizacao:

1. `(L ∨ E) → ¬C`
2. `G ∨ F`
3. `(G → C) ∧ (F → C)`
4. Portanto, `¬L`

Forma: `(L ∨ E) → ¬C, G ∨ F, (G → C) ∧ (F → C) ⊢ ¬L`

Validade: valido.

Prova:

1. `(L ∨ E) → ¬C` premissa
2. `G ∨ F` premissa
3. `(G → C) ∧ (F → C)` premissa
4. `G → C` por `∧E`, 3
5. `F → C` por `∧E`, 3
6. Caso `G`: de 4, conclua `C`
7. Caso `F`: de 5, conclua `C`
8. `C` por `∨E`, 2, 6 e 7
9. Suponha `L`
10. `L ∨ E` por `∨I`, 9
11. `¬C` por `→E`, 1 e 10
12. Contradicao entre 8 e 11
13. `¬L` por `¬I`, 9-12

Observacao: no enunciado, a premissa "ou estou gripado ou tem um filme bom na TV" aparece duas vezes. Uma ocorrencia ja basta para a prova.

---

### 1.2 Salario, geladeira e viagem

Interpretacao:

- `S`: meu salario e bom o suficiente.
- `G`: vou comprar uma geladeira.
- `A`: tive um aumento.
- `T`: tive bastante trabalho neste mes.
- `V`: vou viajar.

Formalizacao:

1. `S → G`
2. `A → S`
3. `T → S`
4. `A ∨ T`
5. `G → ¬V`
6. Portanto, `V`

Forma: `S → G, A → S, T → S, A ∨ T, G → ¬V ⊢ V`

Validade: invalido.

Contraexemplo:

Considere:

- `A = V`
- `T = F`
- `S = V`
- `G = V`
- `V = F`

Verificacao:

- `S → G` e verdadeira.
- `A → S` e verdadeira.
- `T → S` e verdadeira.
- `A ∨ T` e verdadeira.
- `G → ¬V` e verdadeira, pois `G` e verdadeiro e `¬V` tambem.
- A conclusao `V` e falsa.

Logo, as premissas podem ser verdadeiras e a conclusao falsa. O argumento e invalido.

Observacao: pelas premissas, seria possivel concluir `¬V`, isto e, "eu nao vou viajar".

---

### 1.3 Assassinato, suspeita e pista

Interpretacao:

- `A`: houve um assassinato.
- `S`: Samanta e suspeita do crime.
- `I`: Samanta sera interrogada.
- `M`: Marcos sera interrogado.
- `P`: teremos uma pista.
- `R`: Ricardo esta investigando.
- `J`: Jonas esta investigando.

Formalizacao:

1. `A → S`
2. `I ↔ S`
3. `(I ∨ M) → P`
4. Portanto, `(A ∧ R ∧ J) → P`

Forma: `A → S, I ↔ S, (I ∨ M) → P ⊢ (A ∧ R ∧ J) → P`

Validade: valido.

Prova:

1. `A → S` premissa
2. `I ↔ S` premissa
3. `(I ∨ M) → P` premissa
4. Suponha `A ∧ R ∧ J`
5. `A` por `∧E`, 4
6. `S` por `→E`, 1 e 5
7. `S → I` por `↔E`, 2
8. `I` por `→E`, 7 e 6
9. `I ∨ M` por `∨I`, 8
10. `P` por `→E`, 3 e 9
11. `(A ∧ R ∧ J) → P` por `→I`, 4-10

Observacao: `R` e `J` aparecem na conclusao, mas nao sao necessarios para chegar a `P`; eles sao apenas partes adicionais do antecedente.

---

### 1.4 Casa, exaustao, festa e dinheiro

Interpretacao:

- `C`: eu vou para casa.
- `E`: estou exausto.
- `F`: vou fazer muita festa.
- `G`: vou estar sem grana.

Formalizacao:

1. `C → E`
2. `F`
3. `E → C`
4. Portanto, `(C ↔ E) ∧ (F ∨ G)`

Forma: `C → E, F, E → C ⊢ (C ↔ E) ∧ (F ∨ G)`

Validade: valido.

Prova:

1. `C → E` premissa
2. `F` premissa
3. `E → C` premissa
4. `C ↔ E` por `↔I`, 1 e 3
5. `F ∨ G` por `∨I`, 2
6. `(C ↔ E) ∧ (F ∨ G)` por `∧I`, 4 e 5

Observacao: "Se eu for pra casa e porque estou exausto" foi formalizado como `C → E`, isto e, "vou para casa somente se estou exausto".

