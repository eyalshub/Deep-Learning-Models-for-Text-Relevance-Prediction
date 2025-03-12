# Deep Learning Models for Text Relevance Prediction

This repository contains implementations and performance evaluations of various deep learning and machine learning models designed to predict text relevance. The models include Siamese Networks, LSTMs, Linear Regression, Random Forest, and BERT, applied at both the character and word levels.

## Models Overview

### 1. **Naive Model**
- **Runtime**: 1 second
- **Performance**:
  - **Validation RMSE**: 0.545
  - **Test RMSE**: 0.548
  - **Train MAE**: 0.447
  - **Test MAE**: 0.446
- A baseline model that predicts a constant relevance score of 2.5, serving as a simple benchmark.

### 2. **Linear Regression**
- **Character-Level**:
  - **Runtime**: 11.83 seconds
  - **Performance**:
    - **Train RMSE**: 0.53
    - **Test RMSE**: 7.73
    - **Train MAE**: 0.435
    - **Test MAE**: 7.703
- **Word-Level**:
  - **Runtime**: 3.66 seconds
  - **Performance**:
    - **Test RMSE**: 0.32
    - **Test MAE**: 0.44
    - **Best performing model overall with minimal complexity.**

### 3. **Random Forest**
- **Character-Level**:
  - **Runtime**: 40.51 seconds
  - **Performance**:
    - **Test RMSE**: 2.07
    - **Test MAE**: 1.46
- **Word-Level**:
  - **Runtime**: 58.17 seconds
  - **Performance**:
    - **Test RMSE**: 0.33
    - **Test MAE**: 0.445
    - **Competitive performance but not as efficient as word-level linear regression.**

### 4. **Siamese Networks**
- **Character-Level**:
  - **Simple Siamese Network**:
    - **Runtime**: 156 seconds
    - **Performance**:
      - **Test RMSE**: 1.48
      - **Test MAE**: 1.38
- **Siamese LSTM + Embedding**:
  - **Runtime**: ~3.96 hours
  - **Performance**:
    - **Test RMSE**: 0.613
    - **Test MAE**: 0.553
- **Word-Level**:
  - **Siamese LSTM + Embedding**:
    - **Runtime**: ~3.5 hours
    - **Performance**:
      - **Test RMSE**: 0.547
      - **Test MAE**: 0.445
- **Siamese BERT**:
  - **Runtime**: ~1.23 hours
  - **Performance**:
    - **Test RMSE**: 0.5278
    - **Test MAE**: 0.436

### 5. **Shared Network**
- **Runtime**: 358 seconds
- **Performance**:
  - **Test RMSE**: 1.48
  - **Test MAE**: 1.38
  - **Moderate errors, does not outperform simpler methods.**

## Key Findings

### Word-Level Models Dominate:
- **Word-level Linear Regression** and **Word-level Random Forest** showed the best performance with significantly lower runtime compared to deep learning methods.

### Deep Learning Trade-offs:
- **Siamese Networks** (both character-level and word-level) and **BERT** require significant runtime but offer marginal performance improvements over simpler methods, making them less suitable for rapid development when efficiency is crucial.

### Best Performing Model:
- **Word-level Linear Regression** emerges as the optimal choice, offering the best balance between runtime (3.66 seconds) and performance (Test RMSE = 0.32).

## Conclusion

- **For efficient and fast models**, word-level linear regression is the best option.
- **For higher complexity and improved results**, deep learning models like Siamese Networks (LSTM + Embedding) and BERT can be considered, but they come with trade-offs in runtime and computational cost.

## Requirements
- Python 3.x
- Libraries: `TensorFlow`, `Keras`, `scikit-learn`, `gensim`, `transformers`
  
## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/repositoryname.git
   cd repositoryname
