# NAS Leve com Metaheurísticas

Projeto final da disciplina **INF0415 — Heurísticas e Modelagem Multiobjetivo** (UFG).

## Equipe
- Rayane Araújo
- Júlia Júnior
- Marcelo Soares
- João Pedro
- João Arthur

## Sobre o Projeto
O problema abordado é o **Neural Architecture Search (NAS) Leve**. Consiste em encontrar automaticamente arquiteturas eficientes e compactas de Redes Neurais Convolucionais (CNNs) para a tarefa de classificação de dígitos do dataset **MNIST**.

Em vez de projetar arquiteturas manualmente, o espaço de busca é explorado usando três diferentes abordagens metaheurísticas:
1. **Algoritmo Genético (AG)** - Single-Objective (Acurácia vs Parâmetros)
2. **Population-Based Incremental Learning (PBIL)** - Single-Objective
3. **Optuna (TPE)** - Single-Objective guiado pela acurácia (Tracking multiobjetivo posterior)

As abordagens consideram restrições rigorosas computacionais para viabilizar os experimentos sem o uso extensivo de GPUs de alta performance.

## Organização do Repositório
Todo o processo de definição das CNNs, rotinas de treino, funções objetivo e a implementação das metaheurísticas encontram-se reunidas de forma didática no Jupyter Notebook principal do projeto:

- `NAS.ipynb`: Notebook central com todas as classes, código e análises.

## Instruções de Uso
1. Clone o repositório.
2. Certifique-se de que os pacotes necessários estão instalados:
   ```bash
   pip install torch torchvision numpy
   ```
3. Abra o `NAS.ipynb` em seu editor (VSCode ou Jupyter Server).
4. Execute as células na ordem para instanciar as funções, treinar as populações e iniciar a busca do AG (e posteriormente PBIL/Optuna).

O dataset MNIST será baixado automaticamente na primeira execução para a pasta `/data` (ignorada no `.gitignore`).
