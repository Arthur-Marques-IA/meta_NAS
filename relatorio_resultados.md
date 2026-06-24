# Relatório Técnico de Resultados — Neural Architecture Search Leve (SO)

Este relatório apresenta a análise de desempenho do algoritmo de **Neural Architecture Search (NAS)** mono-objetivo (Single-Objective) para a tarefa de classificação de dígitos manuscritos (**MNIST**), correspondendo à **Entrega 1 (Modelagem Completa)** da disciplina **INF0415 — Heurísticas e Modelagem Multiobjetivo** (UFG).

---

## 1. Configuração dos Experimentos

* **Dispositivo de Hardware**: GPU Nvidia T4 (Google Colab)
* **Dataset**: MNIST (60.000 imagens de treino, 10.000 de teste)
* **Algoritmo de Busca**: Algoritmo Genético Mono-objetivo (AG SO)
* **Configurações Evolutivas**:
  - Tamanho da População (`POP_SIZE`): 12 indivíduos
  - Número de Gerações (`GENERATIONS`): 5 gerações
  - Taxa de Mutação: 20%
  - Seleção: Torneio binário com Elitismo de 1 indivíduo
  - Número de Sementes: 5 execuções independentes (seeds 1 a 5)
* **Treinamento das Redes**: Otimizador Adam, taxa de aprendizado de 0.001, treinado por 1 época.

---

## 2. Baseline de Referência (CNN Estática)

Como linha de base para comparação, foi definida uma CNN estática convencional projetada manualmente:
* **Arquitetura**: 2 camadas convolucionais (32 e 64 filtros de $3\times3$), seguidas de Max Pooling ($2\times2$) e ativação ReLU. Camada linear de saída mapeando para as 10 classes.
* **Complexidade (Parâmetros)**: 50.186 parâmetros treináveis
* **Desempenho (Acurácia)**: **97.93%**
* **Tempo de Treinamento**: 21.12 segundos
* **Tempo Médio de Inferência**: 1.10 ms

---

## 3. Resultados das 5 Sementes da Busca Evolutiva

Os resultados obtidos de forma autônoma para cada uma das 5 sementes do Algoritmo Genético foram os seguintes:

| Semente | Acurácia (%) | Parâmetros | Fitness Final | Configuração da CNN (Filtros, Camadas, Ativação) |
| :---: | :---: | :---: | :---: | :--- |
| **1** | 98.21% | 116,874 | 100.31 | `{'n_layers': 3, 'filters': [32, 128, 64], 'activation': 'ReLU'}` |
| **2** | **98.52%** | **43,370** | 100.36 | `{'n_layers': 3, 'filters': [64, 32, 64], 'activation': 'ReLU'}` |
| **3** | **98.71%** | 67,626 | 100.53 | `{'n_layers': 3, 'filters': [64, 32, 128], 'activation': 'LeakyReLU'}` |
| **4** | 98.68% | 67,626 | 100.53 | `{'n_layers': 3, 'filters': [64, 32, 128], 'activation': 'LeakyReLU'}` |
| **5** | 98.15% | 62,442 | 100.33 | `{'n_layers': 3, 'filters': [128, 32, 64], 'activation': 'LeakyReLU'}` |

---

## 4. Análise Estatística Combinada

A análise consolidada das 5 execuções independentes do algoritmo de busca evolutiva apresenta as seguintes métricas estatísticas:

* **Acurácia Média**: **98.45%** (Desvio Padrão: 0.23%)
* **Acurácia Máxima**: **98.71%** (Semente 3) | **Acurácia Mínima**: **98.15%** (Semente 5)
* **Média de Parâmetros**: **71.588** (Desvio Padrão: 24.340)
* **Fitness Médio**: **100.41** (Desvio Padrão: 0.10)

---

## 5. Discussão de Trade-offs e Insights

1. **Superioridade sobre o Design Manual (Baseline)**:
   * **Todas as 5 execuções autônomas** superaram a acurácia de teste obtida pelo Baseline projetado manualmente (97.93%).
   * A acurácia média da busca evolutiva foi de **98.45%** (+0.52% em relação à linha de base).
   * O baixíssimo desvio padrão da acurácia (**0.23%**) evidencia a **robustez e estabilidade** do algoritmo, indicando que a heurística converge de forma consistente para boas soluções sob diferentes sementes.

2. **Descoberta de Arquiteturas Mais Compactas (Semente 2)**:
   * A **Semente 2** obteve uma otimização topológica notável: encontrou uma rede com acurácia de **98.52%** (+0.59% superior ao baseline) consumindo apenas **43.370 parâmetros**.
   * Isso representa uma **redução de 13.5% em tamanho** comparado ao baseline (50.186 parâmetros), provando que o algoritmo de busca evolutiva conseguiu otimizar simultaneamente acurácia e compressão, superando o baseline em ambos os aspectos.

3. **Convergência Duplicada e Ótimo Local (Sementes 3 e 4)**:
   * As **Sementes 3 e 4** convergiram de forma independente para a **exata mesma estrutura de rede**: 3 camadas convolucionais com filtros `[64, 32, 128]` e ativação `LeakyReLU`.
   * A diferença decimal na acurácia (98.71% vs 98.68%) é decorrente apenas da inicialização randômica dos pesos na época única de treino. A descoberta duplicada desse ótimo local demonstra a forte capacidade de exploração e convergência do algoritmo genético.

4. **Preferência por Redes de 3 Camadas**:
   * O espaço de busca permite de 1 a 4 camadas convolucionais. Todas as 5 melhores soluções convergiram para **3 camadas**. A ativação **LeakyReLU** sobressaiu-se na maioria dos melhores indivíduos (Sementes 3, 4 e 5), indicando que essa ativação ajuda a manter um melhor fluxo de gradiente em redes ligeiramente mais profundas para o MNIST.

---

## 6. Conclusão

Os experimentos da **Entrega 1** foram concluídos com sucesso. A modelagem dinâmica de redes, as rotinas de treino e a metaheurística genética provaram-se funcionais e estatisticamente estáveis. O algoritmo evolutivo foi capaz de otimizar a estrutura das CNNs superando o design manual em acurácia e eficiência de parâmetros, servindo como uma linha de base sólida para os futuros experimentos multiobjetivo da disciplina.
