# NextWordPredictor_LSTM
Next Word Prediction on a small Dataset using LSTM
# Next Word Predictor using Website FAQ Dataset (LSTM)

This project builds a **Next Word Prediction model** using a small FAQ dataset from a website. The goal is to predict the most probable next word given an input sequence using an LSTM-based neural network.

---

## 📌 Dataset
- Dataset contains **FAQ text of a website** (available in repo).
- Small dataset used just for learning and experimentation.
- Will be extended later for larger IA / project use.

---

## 🔤 Tokenization & Text Processing

- Imported **Tokenizer** from TensorFlow Keras.
- Fitted tokenizer on full text data.
- Converted text into integer sequences.
- Printed **word_index** to see mapping of words → numbers.

### Sequence Generation Logic
- Created a function to:
  - Split text into sentences
  - For each sentence, generate incremental sequences

Example:
Sentence:  
`how to reset password`

These sequences are used to train next-word prediction.

---

## 📏 Padding

- All sequences had different lengths.
- Used **Keras pad_sequences** with **pre-padding** to make equal length.
- This ensures fixed-size input to the neural network.

---

## 🎯 Input–Output Split

- Split padded sequences into:
  - **X (input words)**
  - **y (next word / target)**

Rule:
- Last word → target (y)
- All previous words → input (X)

Example:

These sequences are used to train next-word prediction.

---

## 📏 Padding

- All sequences had different lengths.
- Used **Keras pad_sequences** with **pre-padding** to make equal length.
- This ensures fixed-size input to the neural network.

---

## 🎯 Input–Output Split

- Split padded sequences into:
  - **X (input words)**
  - **y (next word / target)**

Rule:
- Last word → target (y)
- All previous words → input (X)

Example:


Input: how to reset
Target: password


---

## 🔢 Vocabulary & Shapes

- Total unique words ≈ **282**
- Final padded vocab size used: **313**
- y converted into categorical using **to_categorical**

Shapes:

---

## 🧠 Model Architecture

Built a Sequential deep learning model:

1. **Embedding Layer**
   - Input dim: 313
   - Output dim: 100
   - Converts sparse word index → dense vectors

2. **LSTM Layer**
   - 150 units
   - Learns sequence patterns

3. **Dense Output Layer**
   - 313 neurons
   - Softmax activation
   - Multi-class word prediction

---

## ⚙️ Training

- Loss: categorical crossentropy
- Optimizer: adam
- Trained for **100 epochs**
- Dataset is small so training is fast.

---

## 🔮 Prediction Process

To predict next word:

1. Take input phrase
2. Tokenize it
3. Pad to required length
4. Pass into model
5. Get probability distribution
6. Select word with **highest probability**

Example:

---

## 🧠 Model Architecture

Built a Sequential deep learning model:

1. **Embedding Layer**
   - Input dim: 313
   - Output dim: 100
   - Converts sparse word index → dense vectors

2. **LSTM Layer**
   - 150 units
   - Learns sequence patterns

3. **Dense Output Layer**
   - 313 neurons
   - Softmax activation
   - Multi-class word prediction

---

## ⚙️ Training

- Loss: categorical crossentropy
- Optimizer: adam
- Trained for **100 epochs**
- Dataset is small so training is fast.

---

## 🔮 Prediction Process

To predict next word:

1. Take input phrase
2. Tokenize it
3. Pad to required length
4. Pass into model
5. Get probability distribution
6. Select word with **highest probability**

Example:
Input: "for"
Predicted next word: "mail"


---

## 🔁 Multi-Word Generation

- Ran loop to predict next **10 words**
- Each predicted word appended back to input
- Model produced sequence consistent with dataset patterns

---

## 📊 Observations

- Model works correctly on small dataset
- Predictions match FAQ style text
- Limited vocabulary → limited creativity
- Good proof of concept for next-word prediction

---

## 🚀 Future Improvements

- Use larger dataset
- Add more FAQ or document text
- Increase embedding size
- Use stacked LSTM layers
- Try GRU / Transformer later
- Integrate into IA / chatbot project

---


Generated sequences:

