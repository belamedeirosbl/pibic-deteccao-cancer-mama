# Classificação de Câncer de Mama com Transfer Learning e CNNs 🎗️

> **Projeto de Iniciação Científica (PIBIC) - UNICAP**

Este repositório contém um estudo comparativo e prático sobre a aplicação de Inteligência Artificial no diagnóstico de câncer de mama utilizando a base de dados **MIAS**.

O projeto apresenta duas abordagens distintas em formato de **Jupyter Notebooks**, servindo como um tutorial para aplicação de técnicas de Deep Learning e Machine Learning clássico em imagens médicas.

- 📜 [Ler Relatório Técnico Completo (PDF)](docs/Relatório-Final-PIBIC-2025.pdf)
- 📊 [Ver Slides da Apresentação Final (PDF)](docs/JornadaCientificaPIBIC.pdf)

## Documentação

## Conteúdo dos Notebooks

O projeto está dividido em duas etapas principais de experimentação:

### 1. Comparativo Geral (`1_comparativo_geral.ipynb`)

Uma abordagem inicial para estabelecer uma linha de base (_baseline_).

- **Foco:** Comparação direta entre arquiteturas.
- **Modelos:** CNN criada do zero vs. Extração de características com **VGG16** e **ResNet152V2**.
- **Classificadores:** Uso de vetores de características em SVM, KNN e Random Forest.
- **Objetivo:** Entender qual arquitetura se comporta melhor com o dataset padrão.

### 2. Abordagem Otimizada - DA+B (`2_abordagem_otimizada_dab.ipynb`)

Uma abordagem refinada focada em maximizar a performance e corrigir problemas comuns em datasets médicos.

- **Foco:** Tratamento de dados e generalização.
- **Técnicas Avançadas:**
  - **Data Augmentation (DA):** Transformações geométricas intensas (rotação, zoom, cisalhamento) para aumentar a variabilidade.
  - **Balanceamento de Classes (B):** Aplicação de pesos (`class_weights`) para penalizar erros na classe minoritária (imagens anormais).
  - **Fine-tuning:** Ajuste de hiperparâmetros nos classificadores clássicos e uso de _Early Stopping_ na CNN.

## Tecnologias Utilizadas

- **Linguagem:** Python
- **Deep Learning:** TensorFlow / Keras
- **Machine Learning:** Scikit-learn
- **Processamento de Imagem:** OpenCV / ImageDataGenerator
- **Estatística:** SciPy (para cálculo de Intervalos de Confiança)

## Como Executar

Os notebooks foram projetados para rodar nativamente no **Google Colab** ou em ambiente local com suporte a GPU.

### Opção 1: Google Colab (Recomendado)

1. Baixe os arquivos `.ipynb` da pasta `notebooks/`.
2. Faça upload para o seu Google Drive ou abra diretamente no Colab.
3. Altere o ambiente de execução para **T4 GPU**.
4. Execute as células sequencialmente. O código irá baixar o dataset automaticamente via `gdown`.
