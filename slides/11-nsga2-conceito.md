# Slide 11 — NSGA-II: O Conceito Multiobjetivo

**Duração:** 1min

---

## Por que multiobjetivo?

Não há uma "nota única" correta — os pesos na função fitness são arbitrários.

## NSGA-II (Deb et al., 2002)

Algoritmo multiobjetivo mais usado na literatura.

**Conceito central — Dominância de Pareto:**
- Solução A domina B se é melhor em ≥ 1 objetivo e não pior em nenhum
- Frente de Pareto (rank 0) = soluções que ninguém domina

**Crowding Distance:**
- Dentro da mesma frente, prefere soluções mais isoladas
- Mantém diversidade na fronteira

**Resultado:** não UMA solução, mas um CONJUNTO de soluções não-dominadas

**Nossos 3 objetivos (todos minimizados internamente):**
- o₁ = 100 − acurácia (minimizar → maximiza acurácia)
- o₂ = num_params / MAX_PARAMS (minimizar → rede mais leve)
- o₃ = inf_time_ms (minimizar → mais rápida)

---

## Fala sugerida

É aqui que entra o NSGA-II. O conceito fundamental é a dominância de Pareto: uma solução domina outra se for melhor em pelo menos um objetivo e não pior em nenhum. O NSGA-II classifica toda a população por ranks de dominância e, dentro de cada rank, usa crowding distance para manter diversidade. O resultado não é uma única rede — é um conjunto de soluções na fronteira de Pareto, cada uma representando um compromisso diferente entre acurácia, tamanho e velocidade.
