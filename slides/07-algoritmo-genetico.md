# Slide 7 — Algoritmo Genético (AG)

**Duração:** 1min

---

## Evolução biológica aplicada à busca de arquiteturas

**Parâmetros:** população = 6, gerações = 4

**Operadores:**
- Seleção por **torneio binário**
- **Crossover:** combina n_layers, filtros e ativação dos pais
- **Mutação:** 20% de chance de alterar cada gene
- **Elitismo:** o melhor da geração passa direto para a próxima

**Resultado:**
- Acurácia: 98.18%
- Parâmetros: 68.938
- Tempo de inferência: 0.38ms

---

## Fala sugerida

O AG funciona como evolução biológica. Começamos com uma população aleatória, avaliamos cada indivíduo, selecionamos os melhores via torneio, geramos filhos por crossover e mutação, e repetimos. O elitismo garante que não perdemos a melhor solução encontrada. Resultado: acurácia de 98% com cerca de 69 mil parâmetros.
