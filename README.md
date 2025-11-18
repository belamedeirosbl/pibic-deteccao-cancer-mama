# Classificação de Câncer de Mama usando Aprendizado de Máquina

> **Projeto de Iniciação Científica (PIBIC) - UNICAP 2024/2025**

Este repositório contém a implementação de uma análise comparativa entre modelos de Deep Learning e Machine Learning clássico para o diagnóstico de câncer de mama, utilizando a base de dados **MIAS**.

O projeto implementa um pipeline completo: desde o download automático dos dados, passando pelo pré-processamento e _data augmentation_, até o treinamento e avaliação estatística dos modelos.

## Modelos Implementados

1.  **Abordagem Deep Learning Puro:**

    - **CNN Customizada:** Uma rede neural convolucional criada do zero com 3 blocos de convolução, camadas de _Dropout_ (0.25 e 0.5) e otimizada com _Early Stopping_.

2.  **Abordagem Híbrida (Transfer Learning + ML Clássico):**
    - **Extrator de Características:** Utiliza a arquitetura **ResNet152V2** (pré-treinada na ImageNet) para transformar as imagens em vetores de características.
    - **Classificadores:** Esses vetores alimentam modelos supervisionados:
      - **Random Forest (RF)** (Otimizado com _class_weight='balanced'_)
      - **Support Vector Machine (SVM)** (Kernel linear)
      - **K-Nearest Neighbors (KNN)** (Métrica Euclidiana)

## Resultados Obtidos

Os modelos foram avaliados com métricas de acurácia e intervalos de confiança (95%).

| Modelo                         | Acurácia (Validação) | Intervalo de Confiança (95%) |
| :----------------------------- | :------------------: | :--------------------------: |
| **CNN Personalizada**          |      **97,73%**      |         [0.97, 0.99]         |
| **SVM (via ResNet)**           |      **97,72%**      |         [0.96, 0.99]         |
| **Random Forest (via ResNet)** |      **97,72%**      |         [0.96, 0.99]         |
| **KNN (via ResNet)**           |      **97,72%**      |         [0.96, 0.99]         |

_Os resultados indicam que o uso de Transfer Learning permitiu que classificadores clássicos atingissem a mesma performance de uma rede neural profunda dedicada._

## Pré-requisitos e Instalação

O projeto foi desenvolvido em **Python 3**. Para executar, siga os passos:

1.  Clone o repositório:

    ```bash
    git clone [https://github.com/seu-usuario/pibic-deteccao-cancer-mama.git](https://github.com/seu-usuario/pibic-deteccao-cancer-mama.git)
    cd pibic-deteccao-cancer-mama
    ```

2.  Instale as dependências:
    ```bash
    pip install -r requirements.txt
    ```

## Como Executar

O script principal foi projetado para ser autossuficiente. Ele irá automaticamente:

1. Baixar o dataset (arquivo zip) via `gdown`.
2. Extrair e organizar as pastas de treino e validação.
3. Aplicar _Data Augmentation_ (rotação, zoom, etc.).
4. Treinar os modelos e gerar os gráficos comparativos.

Para rodar:

```bash
python src/main.py
```
