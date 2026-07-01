# Slide 13 — Comparação Completa

**Duração:** 1min

---

## Baseline × Single-Objective × Multiobjetivo

**Gráfico:** `comparacao_completa.png` — 3 painéis de barras horizontais

| Método | Categoria | Acc (%) | Parâmetros | Inf (ms) |
|--------|-----------|:-------:|-----------:|---------:|
| Baseline Large | Baseline | 98.93 | 233.610 | 0.51 |
| Baseline Medium | Baseline | 98.70 | 137.226 | 0.58 |
| Baseline Tiny | Baseline | 96.28 | 31.530 | 0.27 |
| AG | Single-Obj | 98.18 | 68.938 | 0.38 |
| PBIL | Single-Obj | 98.34 | 104.202 | 0.49 |
| Optuna | Single-Obj | 98.74 | 67.626 | 0.55 |
| **NSGA-II (↑Acc)** | **Multi-Obj** | **98.73** | **62.442** | 0.48 |
| **NSGA-II (↓Params)** | **Multi-Obj** | 97.82 | **20.490** | 0.39 |
| **NSGA-II (↓Inf)** | **Multi-Obj** | 96.89 | 31.530 | **0.26** |

**Destaques:**
- NSGA-II(↑Acc): mesma acurácia do Large com **3.7× menos parâmetros**
- NSGA-II(↓Params): 20k params com 97.82% — rede muito compacta
- NSGA-II(↓Inf): mais rápido que **todos** os métodos (0.26ms)

---

## Fala sugerida

Nesta tabela unificada vemos a vantagem do multiobjetivo. O Baseline Large tem 98.93% mas custa 233 mil parâmetros. O NSGA-II encontra uma solução com 98.73% e apenas 62 mil — quase a mesma acurácia com um quarto do tamanho. Ele também encontra uma rede de apenas 20 mil parâmetros com 97.82%, e a mais rápida de todos com 0.26ms. O ponto chave: roda-se uma vez e escolhe-se depois conforme o contexto.
