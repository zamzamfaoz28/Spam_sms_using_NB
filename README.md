# 📩 SMS Spam Detection using Naive Bayes

This project builds an SMS spam classification system using the **Naive Bayes** algorithm. The goal is to distinguish between legitimate (ham) and unwanted (spam) messages using text preprocessing and machine learning techniques. This project is implemented in Python using Jupyter Notebook and can classify SMS messages both from a dataset and real-time user input.

---

## 📁 Dataset

The dataset used is `spam.csv`, which contains SMS messages labeled as:
- `spam` — Unwanted promotional or fraudulent messages
- `ham` — Legitimate messages

Before modeling, unused columns are dropped and the remaining are renamed to:
- `label`: spam or ham
- `pesan`: SMS content

---

## 🔄 Preprocessing Steps

1. **Data Cleaning**  
   - Dropped unnecessary columns  
   - Renamed columns for clarity  

2. **Text Preprocessing**  
   - **Tokenizing** using NLTK  
   - **Stopword Removal**  
   - **Stemming** using NLTK’s `PorterStemmer`

3. **Vectorization**  
   - Applied **TF-IDF** vectorization with a custom analyzer

---

## ⚙️ Model Training

- Model: `MultinomialNB` from Scikit-learn
- Train/Test Split: 80/20 using `train_test_split`
- Feature extraction: `CountVectorizer`
- Target: SMS labeled as spam or ham

---

## 📊 Evaluation Metrics

- **Accuracy**: 97.85%  
- **Precision**: 91.44%  
- **Recall**: 92.66%  
- **F1 Score**: 92.05%  

Also includes a **Confusion Matrix** visualization using Seaborn to better understand classification performance.

---

## 🧪 Real-Time Message Classification

A simple terminal-based input loop allows the user to:
- Enter any SMS message
- Receive instant prediction: `spam` or `ham`
- Option to continue testing or exit

```python
while True:
    user_input = input("Masukkan pesan: ")
    print(model.predict(cv.transform([user_input])))
    response = input("Apakah Anda ingin memasukkan pesan lagi? (y/n): ")
    if response.lower() != 'y':
        break
```
---

## 👨‍💻 Author

Zamzam Miftahul Faoz
Final-year Informatics Student at Universitas Ahmad Dahlan
LinkedIn : www.linkedin.com/in/zamzam-miftahul-faoz
Email: zamzammiftahulfaoz@gmail.com
