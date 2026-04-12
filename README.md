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
