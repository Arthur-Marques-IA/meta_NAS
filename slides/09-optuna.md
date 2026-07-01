# Slide 9 — Diferencial: Optuna / TPE

**Duração:** 1min

---

## Hyperparameter Optimization com State-of-Art

**Optuna** — framework de otimização de hiperparâmetros

**Método:** TPE (Tree-structured Parzen Estimator) — otimização bayesiana

**Funcionamento:**
- 12 trials sequenciais
- A cada trial, sugere a arquitetura mais promissora baseado nos resultados anteriores
- **Pruning** automático: descarta trials de redes muito pesadas (> 500k params)

**Vantagem sobre buscas cegas:** aprende com trials anteriores para focar em regiões promissoras

**Diferencial do projeto (D3)**

**Resultado:**
- Acurácia: 98.74% (melhor SO)
- Parâmetros: 67.626
- Tempo de inferência: 0.55ms

---

## Fala sugerida

O Optuna é nosso diferencial de HPO — Hyperparameter Optimization. Enquanto o AG e PBIL são métodos de população, o Optuna usa otimização bayesiana: a cada trial, ele aprende com os resultados anteriores e sugere a próxima arquitetura mais promissora. Com apenas 12 trials, superou o AG e o PBIL em acurácia, chegando a 98.74%.
