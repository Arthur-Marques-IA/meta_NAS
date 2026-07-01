# Slide 14 — Discussão de Trade-offs

**Duração:** 1min

---

## Single-Obj vs Multi-Obj: quando usar o quê?

**Single-Objective (AG, PBIL, Optuna):**
- Entrega UMA boa solução
- Depende dos pesos λ na função de fitness
- Mais simples de implementar e interpretar

**Multiobjetivo (NSGA-II):**
- Entrega o MAPA COMPLETO dos compromissos
- Permite escolha posterior conforme o cenário

**Guia de decisão:**

| Cenário | Escolha recomendada | Por quê |
|---------|---------------------|---------|
| Servidor sem restrição | NSGA-II(↑Acc) ou Baseline Large | Máxima acurácia |
| Dispositivo móvel / embarcado | NSGA-II(↓Params) | 20k params (10× menor que Large) |
| Aplicação em tempo real | NSGA-II(↓Inf) | 0.26ms — mais rápido de todos |

**Vantagem do MO:** roda uma vez, escolhe depois — sem reformular o problema

---

## Fala sugerida

A grande vantagem do multiobjetivo é a flexibilidade. No single-objective, você recebe uma resposta que reflete os pesos que alguém escolheu arbitrariamente. No multiobjetivo, você recebe um conjunto de soluções e escolhe conforme o contexto. Precisa de acurácia máxima? Pegue o ponto de maior acurácia. Precisa rodar num celular? Pegue o menor. Precisa de resposta em tempo real? Pegue o mais rápido. Tudo isso da mesma execução.
