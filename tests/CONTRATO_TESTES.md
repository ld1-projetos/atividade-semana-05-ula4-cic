# CONTRATO_TESTE v0.4 — LD1 (Lógica Digital 1)

**Grupo:** G02 - ULA4 CIC  
**Integrantes presentes:** Ana Clara Santana Silva, Giselly Jahel Dias, Hannah França Nascimento, Matheus Santiago Dutra e Nicolas Anunciação Santos  
**Data:** 2026-04-12
**Repositório/Commit base:** https://github.com/ld1-projetos/atividade-semana-05-ula4-cic
**Arquivo Logisim:** ULA4_core.circ  
**Milestone da semana:** M3 - Unidade de Controle e Minimização com Mapa de Karnaugh (K-map)
---

## 0) Objetivo deste contrato

Padronizar o registro de casos de teste para a validação da unidade de controle da ULA. [cite_start]O foco desta versão é a otimização da lógica combinacional utilizando o Mapa de Karnaugh (K-map), que é um método gráfico para minimização. O objetivo é obter expressões com menos termos e menos variáveis por termo [cite: 20][cite_start], trazendo o benefício de reduzir o custo e a complexidade do controle (op_select).

## 1) Interface do curso (fixa)

* **Subcircuito principal:** `ULA4_core`
* **Entradas:** `A [3:0]`, `B [3:0]`, `OP [2:0]`
* **Saídas:** `F [7:0]`, `C`, `V`, `Z`, `valid_OP`

## 2) Convenções de representação (v0.5)

* **A e B (4 bits):** 1 dígito hexadecimal em MAIÚSCULAS (0..F).
* **OP (3 bits):** Valor inteiro (0..7) ou binário para conferência de mintermos.
* **F (8 bits):** 2 dígitos hexadecimais em MAIÚSCULAS (00..FF).
* **C, V, Z, valid_OP:** bits de status (0 ou 1).
* **Status:** PASS (Sucesso), FAIL (Falha) ou ASD (A Ser Definido).

## 3) Arquitetura e Rastreabilidade (S05)

* **ULA4_core utiliza:** `op_select_SOP`, `op_select_POS`, `logic4_v2`.
* **Minimização Aplicada (Mapa de Karnaugh):** * **1. Módulo op_select_SOP:** A lógica de decodificação foi projetada e agrupada através de Mapas de Karnaugh para mapear cada mintermo exclusivo das operações de forma simplificada.
  * **2. Módulo op_select_POS:** O K-map foi utilizado para obter o mínimo SOP e mínimo POS da mesma função, ajudando a escolher a implementação "mais barata" (com menos portas). A análise revelou que a variável `OP[0]` não altera o resultado. A lógica foi otimizada para o uso de apenas **1 porta XOR** entre `OP[1]` e `OP[2]`, substituindo 5 portas básicas e reduzindo o custo de hardware.

## 4) Tabela de casos de teste (Controle SOP e POS)
