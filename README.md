# Projeto: Previsão da Estrutura Secundária de Proteínas Usando Redes Neurais

Os dados utilizados: [Protein Secondary Structure Dataset - CASP12, CB513, TS115](https://www.kaggle.com/datasets/tamzidhasan/protein-secondary-structure-casp12-cb513-ts115?select=test_secondary_structure_casp12.csv).
## Descrição

Este projeto tem como objetivo prever a estrutura secundária de proteínas (PSSP - *Protein Secondary Structure Prediction*) a partir de suas sequências de aminoácidos, utilizando técnicas de *Deep Learning*. A estrutura secundária das proteínas consiste em três elementos principais: hélices alfa (α-helix), folhas beta (β-sheet) e enrolamentos (*coils*). O modelo desenvolvido emprega redes neurais recorrentes, mais especificamente a arquitetura LSTM (*Long Short-Term Memory*), que é conhecida por lidar bem com sequências temporais e estruturadas, como as cadeias de aminoácidos.

A previsão da estrutura secundária é uma etapa fundamental para entender a forma tridimensional de uma proteína, que está diretamente ligada à sua função biológica. Este modelo tem como objetivo classificar cada aminoácido de uma proteína em uma das três estruturas secundárias mencionadas, acelerando assim o processo de análise de proteínas em larga escala e oferecendo insights valiosos para a biologia computacional e a descoberta de medicamentos.

## Etapas do Projeto

1. **Importação das Bibliotecas**:
    O projeto utiliza bibliotecas como Pandas e NumPy para manipulação de dados e TensorFlow e Scikit-learn para a criação e treinamento do modelo de redes neurais.

2. **Pré-processamento dos Dados**:
    - As sequências de aminoácidos são padronizadas para um comprimento fixo.
    - Utiliza-se a técnica de *one-hot encoding* para representar as sequências de aminoácidos como vetores binários.
    - As estruturas secundárias são convertidas em uma forma numérica para que possam ser utilizadas como rótulos de treinamento.

3. **Construção do Modelo**:
    - O modelo utiliza camadas LSTM, que são ideais para lidar com a dependência sequencial das entradas.
    - A camada final do modelo aplica a função de ativação *softmax* para prever qual estrutura secundária corresponde a cada aminoácido da sequência.

4. **Treinamento e Validação**:
    - O conjunto de dados é dividido em treinamento e validação, permitindo avaliar o desempenho do modelo em dados não vistos durante o treinamento.
    - O modelo é treinado usando a função de perda *sparse categorical crossentropy* e o otimizador Adam, que ajusta os pesos do modelo para minimizar o erro nas previsões.

5. **Avaliação do Modelo**:
    - Após o treinamento, o desempenho do modelo é avaliado usando a métrica de acurácia, que indica a porcentagem de previsões corretas feitas pelo modelo.

## Estrutura do Projeto

- `IA.py`: Script principal contendo a implementação do modelo de previsão de estrutura secundária de proteínas.
- `training_secondary_structure_train.csv`: Arquivo de dados de treinamento e teste.
  
## Resultados

Após o treinamento, o modelo alcançou uma acurácia de **83.31%** no conjunto de validação. Este resultado demonstra a capacidade do modelo em prever corretamente a estrutura secundária de proteínas com base na sequência de aminoácidos, sendo um indicador promissor para futuras aplicações na área de biologia computacional.

## Aplicações Potenciais

- **Descoberta de Medicamentos**: A previsão da estrutura secundária de proteínas pode auxiliar na identificação de alvos proteicos para o desenvolvimento de novos medicamentos.
- **Biologia Computacional**: Ferramentas automáticas de previsão de estruturas secundárias são fundamentais para análises em larga escala e fornecem insights sobre como as proteínas funcionam em nível molecular.