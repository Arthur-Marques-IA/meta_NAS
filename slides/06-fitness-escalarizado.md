# Slide 6 — Fitness Escalarizado (Single-Objective)

**Duração:** 1min

---

## Combinando múltiplos objetivos em uma nota única

**Fórmula:**
```
fitness = accuracy - (params / MAX_PARAMS) × 20 + ((MAX_PARAMS - params) / MAX_PARAMS) × 2 - 20 (se acc < 90%)
```

**Componentes:**
- Valor base = acurácia
- Penalidade para redes grandes (> 500k params)
- Penalidade para redes pouco precisas (< 90%)
- Bônus residual para redes compactas

**Problema:** os pesos são arbitrários — mudar λ muda a "melhor" solução

**Motivação para multiobjetivo:** entregar um conjunto de soluções ao invés de uma

---

## Fala sugerida

Para as abordagens single-objective, precisávamos de uma nota única. Criamos essa função de fitness que combina acurácia com penalidades para redes grandes e bonificações para redes leves. O problema é: quem decidiu que a acurácia vale X e o número de parâmetros vale Y? Essa é uma decisão arbitrária. É por isso que também implementamos a abordagem multiobjetiva.
