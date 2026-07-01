# Slide 2 — Motivação

**Duração:** 1min

---

## Por que Neural Architecture Search?

- Projetar redes neurais manualmente é **custoso e subjetivo**
- Engenheiros escolhem UMA arquitetura baseada em intuição e tentativa-erro
- Diferentes cenários exigem diferentes trade-offs (acurácia vs. tamanho vs. velocidade)
- **NAS** automatiza esse processo: explora o espaço de busca sistematicamente
- **Metaheurísticas** (AG, PBIL, Optuna, NSGA-II) guiam essa exploração de forma inteligente

---

## Fala sugerida

Projetar uma CNN é um processo manual e intuitivo — o engenheiro define número de camadas, filtros, funções de ativação por tentativa e erro. Mas e se pudéssemos automatizar isso? O NAS faz exatamente isso: usa algoritmos de otimização para explorar centenas de arquiteturas e encontrar as melhores. A pergunta é: como guiar essa busca? É isso que nosso projeto investiga.
