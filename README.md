# Tabelas Verdade - Semana 05

### 1. Unidade de Controle: op_select (SOP)

| OP[2] | OP[1] | OP[0] | sel0 | sel1 | sel2 | sel3 | sel4 | sel5 | sel6 | sel7 |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | **1** | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | **1** | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | **1** | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 | **1** | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | **1** | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | **1** | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | **1** | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | **1** |

### 2. Validação de Instrução: valid_OP (POS)

| OP[2] | OP[1] | OP[0] | valid_OP |
|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 1 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | 0 |

---

## Mapa de Karnaugh (K-Map)

Após a análise do Mapa de Karnaugh para o sinal `valid_OP`, identificamos que o bit **OP[0]** não influencia o resultado, permitindo a simplificação do circuito.

**Expressão Booleana Minimizada:**
`valid_OP = (NOT OP[2] AND OP[1]) OR (OP[2] AND NOT OP[1])`

Esta expressão corresponde logicamente a uma porta **XOR** entre OP[2] e OP[1].*

## Justificativa de Minimização e Custo (SOP vs POS)

A análise do Mapa de Karnaugh para o sinal `valid_OP` revelou que a variável $OP_0$ não afeta o resultado final.

* **SOP (Soma de Produtos):** $valid\_OP = (\overline{OP_1} \cdot OP_2) + (OP_1 \cdot \overline{OP_2})$
* **POS (Produto de Somas):** $valid\_OP = (OP_1 + OP_2) \cdot (\overline{OP_1} + \overline{OP_2})$

Se implementadas exclusivamente com portas lógicas básicas (AND, OR, NOT), ambas as formas exigiriam um total de 5 portas. No entanto, nota-se que ambas as expressões booleanas representam matematicamente a função lógica **Ou Exclusivo (XOR)**. Sendo assim, a implementação final adotada no Logisim utilizou apenas **1 porta XOR** conectada aos bits $OP_1$ e $OP_2$. Essa decisão garante a maior otimização possível, entregando o menor custo de componentes e a menor complexidade de roteamento de fios para a Unidade de Controle.
