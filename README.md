# Cats-and-Dogs
Transfer Learning para Classificação de Gatos e Cachorros
Este projeto utiliza técnicas de Transfer Learning para classificar imagens de gatos e cachorros, implementado em Python com TensorFlow/Keras. O código foi otimizado para execução no Google Colab com acesso a datasets armazenados no Google Drive.

# 📌 Visão Geral
O objetivo deste projeto é criar um modelo de classificação de imagens que distingue entre gatos e cachorros usando:

* Modelos pré-treinados (VGG16, ResNet50, MobileNetV2)
* Técnicas de Transfer Learning e Fine-Tuning
* Data augmentation para melhor generalização
* Otimização para execução no Google Colab

# 📊 Dataset
O dataset utilizado é o Cats vs Dogs da Microsoft, com as seguintes características:

* Origem: https://www.microsoft.com/en-us/download/details.aspx?id=54765
* Tamanho do download: 786.67 MiB
* Tamanho do dataset: 1.04 GiB
* Total de imagens: 23,262 (após remoção de 1,738 imagens corrompidas)
* Classes: Gatos e Cachorros

Estrutura do dataset:

    PetImages
    ├── Cat/ (Contém imagens de gatos)
    └── Dog/ (Contém imagens de cachorros)

# 🛠️ Configuração Técnica
Pré-requisitos
* Python 3.x
* TensorFlow 2.x
* Keras
* OpenCV
* Google Colab (para execução como notebook)

Instalação:

    pip install tensorflow opencv-python matplotlib seaborn scikit-learn

Hiperparâmetros Principais (python)

    IMG_SIZE = (224, 224)       # Tamanho das imagens de entrada
    BATCH_SIZE = 32             # Tamanho do lote
    EPOCHS = 20                 # Número de épocas para treinamento inicial
    LEARNING_RATE = 0.0001      # Taxa de aprendizado inicial

# 🚀 Como Executar
1. Preparação do Ambiente:
* Faça upload do dataset para seu Google Drive na estrutura MyDrive/PetImages/{Cat,Dog}
* Execute o notebook no Google Colab

2. Fluxo de Execução:
* Configuração do Google Drive
* Verificação e limpeza do dataset
* Criação de geradores de dados com augmentation
* Construção do modelo com Transfer Learning
* Treinamento inicial
* Fine-tuning (opcional)
* Avaliação do modelo
* Salvamento do modelo treinado

# 🧠 Arquitetura do Modelo
O projeto oferece três opções de modelos base:
1. ResNet50 (padrão)
2. VGG16
3. MobileNetV2

A arquitetura completa adiciona ao modelo base:
* Global Average Pooling
* Batch Normalization
* Camadas Dense com Dropout
* Camada de saída com ativação sigmoid

# 📈 Métricas de Performance
O modelo é avaliado usando:
* Accuracy
* Loss
* Matriz de Confusão
* Relatório de Classificação (precision, recall, f1-score)

# 📂 Estrutura do Código
Principais funções:

    configurar_google_drive(): Configura acesso ao dataset
    criar_data_generators_otimizado(): Prepara os dados para treinamento
    criar_modelo_transfer_learning(): Constroi o modelo
    treinar_modelo(): Executa o treinamento
    fine_tuning(): Ajuste fino do modelo
    avaliar_modelo(): Métricas finais de performance

# 📚 Referências
Dataset original: Microsoft Research - Cats vs Dogs

Documentação TensorFlow: tfds catalog - cats_vs_dogs

Artigo científico:

    bibtex
    @Inproceedings{asirra-a-captcha-that-exploits-interest-aligned-manual-image-categorization,
      author = {Elson, Jeremy and Douceur, John (JD) and Howell, Jon and Saul, Jared},
      title = {Asirra: A CAPTCHA that Exploits Interest-Aligned Manual Image Categorization},
      booktitle = {Proceedings of 14th ACM Conference on Computer and Communications Security (CCS)},
      year = {2007},
      month = {October},
      publisher = {Association for Computing Machinery, Inc.},
      url = {https://www.microsoft.com/en-us/research/publication/asirra-a-captcha-that-exploits-interest-aligned-manual-image-categorization/},
      edition = {Proceedings of 14th ACM Conference on Computer and Communications Security (CCS)},
    }

# 🎯 Resultados Esperados

O modelo deve alcançar uma accuracy satisfatória na tarefa de classificação, demonstrando a eficácia das técnicas de Transfer Learning mesmo com recursos computacionais limitados.

🤝 Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests com melhorias.
