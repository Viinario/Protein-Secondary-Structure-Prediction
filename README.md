# Project: Protein Secondary Structure Prediction Using Neural Networks

Data Used: [Protein Secondary Structure Dataset - CASP12, CB513, TS115](https://www.kaggle.com/datasets/tamzidhasan/protein-secondary-structure-casp12-cb513-ts115?select=test_secondary_structure_casp12.csv)

## Description

This project aims to predict the secondary structure of proteins (PSSP - *Protein Secondary Structure Prediction*) from their amino acid sequences using *Deep Learning* techniques. Protein secondary structures consist of three main elements: alpha helices (α-helix), beta sheets (β-sheet), and coils. The developed model employs recurrent neural networks, specifically the LSTM (*Long Short-Term Memory*) architecture, known for effectively handling sequential and structured data, such as amino acid chains.

Predicting the secondary structure is a fundamental step in understanding the three-dimensional shape of a protein, which is directly linked to its biological function. This model aims to classify each amino acid in a protein into one of the three mentioned secondary structures, thus accelerating large-scale protein analysis and providing valuable insights for computational biology and drug discovery.

## Project Steps

1. **Library Imports**:  
   The project utilizes libraries like Pandas and NumPy for data manipulation, and TensorFlow and Scikit-learn for creating and training the neural network model.

2. **Data Preprocessing**:  
   - Amino acid sequences are standardized to a fixed length.  
   - The *one-hot encoding* technique is used to represent amino acid sequences as binary vectors.  
   - Secondary structures are converted into numeric formats to be used as training labels.  

3. **Model Construction**:  
   - The model employs LSTM layers, ideal for handling the sequential dependencies of the input data.  
   - The final layer applies the *softmax* activation function to predict the secondary structure corresponding to each amino acid in the sequence.

4. **Training and Validation**:  
   - The dataset is split into training and validation sets to evaluate the model’s performance on unseen data.  
   - The model is trained using the *sparse categorical crossentropy* loss function and the Adam optimizer, which adjusts the model's weights to minimize prediction errors.  

5. **Model Evaluation**:  
   - After training, the model's performance is assessed using the accuracy metric, which indicates the percentage of correct predictions.

## Project Structure

- `IA.py`: Main script containing the implementation of the protein secondary structure prediction model.  
- `training_secondary_structure_train.csv`: Dataset file for training and testing.

## Results

After training, the model achieved an accuracy of **83.31%** on the validation set. This result demonstrates the model's ability to accurately predict protein secondary structures based on amino acid sequences, serving as a promising indicator for future applications in computational biology.

## Potential Applications

- **Drug Discovery**: Predicting the secondary structure of proteins can aid in identifying protein targets for the development of new drugs.  
- **Computational Biology**: Automated secondary structure prediction tools are essential for large-scale analyses and provide insights into how proteins function at the molecular level.