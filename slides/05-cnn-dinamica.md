# Slide 5 — CNN Dinâmica (DynamicCNN)

**Duração:** 1min

---

## Do Cromossomo à Rede Neural

`DynamicCNN` constrói a rede automaticamente a partir do cromossomo:

**Estrutura por camada:**
- Conv2d(kernel=3×3, padding=1) → Ativação → MaxPool2d(2×2)

**Auto-dimensionamento:**
- Dummy input `zeros(1, 1, 28, 28)` passa pela rede para calcular o tamanho do Flatten automaticamente
- Evita erros de dimensão para qualquer configuração

**Camada de saída:** Linear(N_flat, 10)

---

## Fala sugerida

A classe DynamicCNN recebe o cromossomo e constrói a rede automaticamente. Cada camada convolucional tem um kernel 3×3 com padding, seguida de ativação e MaxPool. Um truco importante: passamos um tensor dummy pela rede para calcular o tamanho do flatten — assim nenhuma configuração quebra o código, independente de quantas camadas ou filtros tenhamos.
