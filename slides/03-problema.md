# Slide 3 — Definição do Problema

**Duração:** 1min

---

## Busca automática de arquiteturas CNN para o MNIST

**Dataset:** MNIST (60k treino / 10k teste, imagens 28×28, 10 classes)

**3 objetivos simultâneos:**
- f₁: Maximizar acurácia (%)
- f₂: Minimizar número de parâmetros (complexidade)
- f₃: Minimizar tempo de inferência (ms/lote)

**Restrição:** máximo de 500.000 parâmetros

---

## Fala sugerida

Nosso problema: classificar dígitos do MNIST, mas a arquitetura da rede não é fixa — ela é descoberta. Avaliamos cada arquitetura em três dimensões: quão precisa ela é, quão pesada ela é, e quão rápida ela é na inferência. Esses três objetivos entram em conflito, e é esse trade-off que as metaheurísticas precisam gerenciar.
