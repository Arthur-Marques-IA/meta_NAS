# Slide 4 — Espaço de Busca e Cromossomo

**Duração:** 1min

---

## Representação das Arquiteturas (Cromossomo)

Cada arquitetura é codificada como um dicionário com três genes:

- `n_layers` ∈ {1, 2, 3, 4}
- `filters` ∈ {16, 32, 64, 128} por camada
- `activation` ∈ {ReLU, LeakyReLU}

**Exemplo:**
```
{n_layers: 3, filters: [64, 32, 128], activation: LeakyReLU}
```

Tamanho do espaço: milhares de combinações possíveis

---

## Fala sugerida

Cada arquitetura é codificada como um cromossomo: um dicionário com três genes — número de camadas, lista de filtros e função de ativação. Com 4 opções de camadas, 4 de filtros por camada e 2 ativações, temos milhares de combinações. Cada combinação gera uma CNN diferente.
