# Slide 12 — Fronteira de Pareto: Inicial vs Evoluída

**Duração:** 1min

---

## Evolução da fronteira ao longo das gerações

**Gráfico:** `pareto_fronts.png` — 3 painéis

### Painel 1: Acurácia × Parâmetros
- Fronteira inicial (população aleatória, vermelho): 5 soluções dispersas
- Fronteira evoluída (NSGA-II, azul): 6 soluções mais próximas do ideal (alto × esquerda)
- Baselines manuais (diamantes verdes) ficam dentro da fronteira
- Soluções SO (estrelas) na fronteira ou próximas

### Painel 2: Acurácia × Tempo de Inferência
- Mesma visualização, eixo X = tempo em ms

### Painel 3: Evolução do Hipervolume Proxy
- HV sobe a cada geração: 445.5 → 458.2 → 458.3 → 460.1
- Confirma melhoria consistente da fronteira

---

## Fala sugerida

Este gráfico mostra o poder do multiobjetivo. Os pontos vermelhos são a fronteira de Pareto da população aleatória inicial. Os azuis são a fronteira após 4 gerações do NSGA-II — claramente mais próxima do canto superior-esquerdo, que é o ideal (alta acurácia, poucos parâmetros). O hipervolume confirma: a qualidade da fronteira melhora a cada geração. As baselines manuais ficam dentro dessa fronteira — o que significa que o NSGA-II encontrou soluções que dominam as arquiteturas feitas à mão.
