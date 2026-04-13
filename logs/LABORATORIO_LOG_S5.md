# LOG_PROJETO - Semana 05 (LD1)

**Grupo:** G02 - ULA4 CIC  
**Integrantes presentes:** Ana Clara Santana Silva, Giselly Jahel Dias, Hannah França Nascimento, Matheus Santiago Dutra e Nicolas Anunciação Santos  
**Data:** 2026-04-12
**Repositório/Commit base:** [https://github.com/ld1-projetos/atividade-semana-05-ula4-cic]
**Arquivo Logisim:** ULA4_core.circ  
**Milestone da semana:** M3 - Unidade de Controle e Minimização com Mapa de Karnaugh (K-map)

---

## 1) Objetivo do encontro
* Utilizar o Mapa de Karnaugh como método gráfico para a minimização de expressões booleanas da unidade de controle.

## 2) O que foi feito
* Derivamos as expressões booleanas para a flag de controle `valid_OP` utilizando o Mapa de Karnaugh (K-map) de 3 variáveis.
* Substituímos o circuito complexo não otimizado por uma única porta XOR, reduzindo drasticamente o custo e os fios do projeto

## 3) O que foi testado

* Verificamos a saída da nova porta XOR comparando-a diretamente com a Tabela Verdade inicial.
* Rodamos vetores de teste modificando os pinos de entrada no Logisim (ex: `010` para saída 1, `111` para saída 0) para validar o comportamento.
* Confirmamos na prática que o bit `OP0` pode ficar desconectado sem afetar a precisão da flag de validação.

## 4) O que falhou

* **Sem falhas nesta semana:** a implementação seguiu o planejamento da tabela verdade e os subcircuitos funcionaram conforme esperado nos testes realizados.

## 5) Evidências

* Prints da tabela verdade, expressões SOP/POS justificadas no README, e capturas de tela das sondas do Logisim mostrando a porta XOR rodando os vetores de teste.

## 6) Decisões tomadas

* Optamos pela implementação com a porta XOR por ela sintetizar perfeitamente as equações SOP e POS, garantindo o menor custo de hardware possível (apenas 1 porta lógica).
* Padronizamos os nomes dos arquivos de imagem dos testes no computador local antes de fazer o commit para o GitHub, mantendo o repositório organizado.

## 7) Próximos passos

* Finalizar a implementação física no Logisim da versão minimizada.
* Preparar a demonstração rápida de 2-3 minutos explicando a relação entre um grupo do mapa e um termo da expressão final.
