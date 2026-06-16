# Hotel_Tips-using-DeepLearning

# 💰 Restaurant Tip Prediction Using Deep Learning

A Deep Learning regression model built with TensorFlow/Keras that predicts the tip amount a customer is likely to leave based on restaurant billing information and customer attributes.

This project uses the popular **Tips Dataset** from Seaborn and demonstrates how Artificial Neural Networks (ANNs) can be applied to regression problems.

---

## 📌 Project Overview

Restaurants often analyze customer behavior to understand tipping patterns. In this project, a Deep Learning model is trained to predict the expected tip amount using features such as:

- Total bill amount
- Gender
- Smoking preference
- Day of the week
- Time of meal
- Party size

The model learns relationships between these features and the tip amount, enabling accurate tip predictions for new customer data.

---

## 📊 Dataset

The dataset is loaded directly from Seaborn.

```python
import seaborn as sns

df = sns.load_dataset('tips')
```

### Dataset Information

- Total Records: 244
- Features: 6
- Target Variable: Tip Amount

### Features Used

| Feature | Description |
|----------|-------------|
| total_bill | Total bill amount |
| sex | Customer gender |
| smoker | Smoking status |
| day | Day of visit |
| time | Lunch or Dinner |
| size | Number of people in the group |

### Target

| Column |
|----------|
| tip |

---

## 🔄 Data Preprocessing

Since Neural Networks work with numerical values, categorical columns are converted into numeric labels.

### Gender Encoding

| Gender | Value |
|----------|--------|
| Female | 0 |
| Male | 1 |

### Smoker Encoding

| Smoker | Value |
|----------|--------|
| No | 0 |
| Yes | 1 |

### Day Encoding

| Day | Value |
|------|--------|
| Sun | 1 |
| Sat | 2 |
| Thur | 3 |
| Fri | 4 |

### Time Encoding

| Time | Value |
|-------|--------|
| Dinner | 0 |
| Lunch | 1 |

---

## 🧠 Deep Learning Model Architecture

The model is built using TensorFlow's Sequential API.

### Network Structure

| Layer | Neurons |
|---------|---------|
| Input Layer | 4 |
| Hidden Layer 1 | 32 |
| Hidden Layer 2 | 32 |
| Hidden Layer 3 | 64 |
| Hidden Layer 4 | 64 |
| Hidden Layer 5 | 128 |
| Hidden Layer 6 | 64 |
| Hidden Layer 7 | 64 |
| Output Layer | 1 |

### Output Layer

The output layer contains a single neuron because this is a **Regression Problem** where the goal is to predict a continuous numerical value (tip amount).

---

## ⚙️ Model Compilation

The model uses:

- Optimizer: Adam
- Loss Function: Mean Squared Error (MSE)
- Metric: Mean Squared Error

```python
model.compile(
    optimizer='adam',
    loss='mean_squared_error',
    metrics=['mean_squared_error']
)
```

---

## 🚀 Model Training

The model is trained for 50 epochs.

```python
model.fit(x, y, epochs=50)
```

During training, the network learns the relationship between customer attributes and the tip amount.

---

## 🔍 Sample Predictions

### Example 1

Input:

```python
[21.01, 1, 0, 1, 0, 3]
```

Meaning:

- Total Bill = $21.01
- Male
- Non-Smoker
- Sunday
- Dinner
- Group Size = 3

Predicted Tip:

```python
$3.30
```

---

### Example 2

Input:

```python
[24.59, 0, 0, 1, 0, 4]
```

Meaning:

- Total Bill = $24.59
- Female
- Non-Smoker
- Sunday
- Dinner
- Group Size = 4

Predicted Tip:

```python
$3.63
```

---

### Example 3

Input:

```python
[16.99, 0, 0, 1, 0, 2]
```

Meaning:

- Total Bill = $16.99
- Female
- Non-Smoker
- Sunday
- Dinner
- Group Size = 2

Predicted Tip:

```python
$2.59
```

---

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Seaborn
- Jupyter Notebook

---


## 📈 Results

The Deep Learning model successfully learns tipping patterns from restaurant customer data and predicts tip amounts based on billing and customer characteristics.

This project demonstrates:

- Data preprocessing
- Feature encoding
- Regression using Deep Learning
- Neural Network design with TensorFlow
- Real-world prediction workflow

---

## 🔮 Future Improvements

- Train-Test Split
- Feature Scaling
- Dropout Layers for Regularization
- Hyperparameter Tuning
- Early Stopping
- Model Evaluation Metrics (MAE, RMSE, R² Score)
- Streamlit Deployment
- Flask API Integration

---

## 🎯 Learning Outcomes

By completing this project, you will understand:

- Regression using Artificial Neural Networks
- TensorFlow/Keras model development
- Data preprocessing techniques
- Feature engineering
- Real-world machine learning workflows

---

## 👩‍💻 Author

**Lahari Grandhi**

If you found this project helpful, consider giving it a ⭐ on GitHub.
