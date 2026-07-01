# Slide 15 — Conclusão e Trabalhos Futuros

**Duração:** 1min

---

## Conclusões

- Todas as metaheurísticas superaram 96% no MNIST com redes compactas
- Single-objective (Optuna): melhor acurácia individual — **98.74%**
- Multiobjetivo (NSGA-II): soluções que **dominam baselines manuais** em acc × params
- Não existe método universalmente superior — diferentes compromissos para diferentes cenários

## Trabalhos Futuros

- Dataset mais complexo (CIFAR-10, Fashion-MNIST)
- Mais épocas de treino para avaliações mais justas
- Expansão do espaço de busca (batch norm, dropout, kernel size variável)
- Comparação com SPEA-II e MOEA/D

## Referências

- Deb, K. et al. (2002). A fast and elitist multiobjective genetic algorithm: NSGA-II. IEEE Transactions on Evolutionary Computation.
- Akiba, T. et al. (2019). Optuna: A Next-generation Hyperparameter Optimization Framework. KDD.

---

## Fala sugerida

Para concluir: todas as metaheurísticas encontraram boas arquiteturas automaticamente, com destaque para o Optuna no single-objective e o NSGA-II no multiobjetivo. O NSGA-II provou que é possível encontrar redes que dominam baselines manuais — mesma acurácia com muito menos parâmetros. Como trabalhos futuros, sugerimos testar em datasets mais complexos, expandir o espaço de busca e comparar com SPEA-II. Obrigado!
