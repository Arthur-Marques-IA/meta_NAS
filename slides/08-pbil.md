# Slide 8 — PBIL (Population-Based Incremental Learning)

**Duração:** 1min

---

## Aprendizado de distribuição probabilística

**Diferença conceitual em relação ao AG:**
- Não mantém população explícita entre gerações
- Mantém um **vetor de probabilidades** que representa "o que funciona"

**Mecanismo:**
- A cada iteração: amostra população → avalia → atualiza probabilidades em direção ao melhor
- Learning rate = 0.1
- Mutação da distribuição = 0.05

**Vantagem:** convergência mais suave e estável que o AG

**Resultado:**
- Acurácia: 98.34%
- Parâmetros: 104.202
- Tempo de inferência: 0.49ms

---

## Fala sugerida

O PBIL é uma abordagem diferente. Em vez de manter indivíduos cruzando entre si, ele mantém um vetor de probabilidades — uma receita geral do que funciona. A cada iteração, amostra novas redes baseado nessa receita, avalia, e ajusta a receita em direção ao melhor. A vantagem é uma convergência mais suave. Conseguiu 98.34% de acurácia.
