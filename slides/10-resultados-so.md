# Slide 10 — Resultados Single-Objective

**Duração:** 1min

---

## Comparação AG vs PBIL vs Optuna

| Método | Acurácia (%) | Parâmetros | Inf. (ms) |
|--------|:------------:|-----------:|----------:|
| AG | 98.18 | 68.938 | 0.38 |
| PBIL | 98.34 | 104.202 | 0.49 |
| Optuna | **98.74** | **67.626** | 0.55 |

**Insights:**
- Optuna = melhor acurácia
- AG = mais rápido na inferência
- Todos superaram 98%
- Convergência: Optuna alcança fitness alto mais cedo nos trials

**Gráficos:** `convergencia.png` (convergência por geração/trial)

---

## Fala sugerida

Consolidando os resultados single-objective: o Optuna teve a melhor acurácia com 98.74% e relativamente poucos parâmetros. O AG foi o mais rápido na inferência. Todos superaram 98%, mostrando que qualquer metaheurística já supera um design ingênuo. Mas note: cada método entrega apenas UMA resposta. E se quisermos ver o mapa completo dos trade-offs?
