

# Psychology AI Assistant 
**Student:** Shady Dandach
**Institution:** Lebanese American University (LAU)  
**Classification:** Junior CS Student 

## 📋 Project Overview
This project is an AI-powered psychology assistant that uses **Natural Language Processing (NLP)** and **Neural Networks** to provide relevant psychological advice. It works by converting human language into mathematical vectors and using a trained model to predict the most helpful response from a curated dataset.

## Technical Architecture
The system is built using a two-stage pipeline: **Embedding Generation** and **Vector Prediction**.

### 1. The Embedding Layer
We use the `all-MiniLM-L6-v2` Sentence Transformer to convert text into a 384-dimensional vector. This allows the AI to understand the *meaning* of words rather than just matching keywords.

### 2. The Neural Network (MLP)
The core "brain" is a Multi-Layer Perceptron (MLP) built in PyTorch with the following dimensions:
* **Input Layer:** 384 neurons
* **Hidden Layer 1:** 512 neurons (ReLU Activation)
* **Hidden Layer 2:** 256 neurons (ReLU Activation)
* **Output Layer:** 384 neurons
* **Optimization:** Adam Optimizer & MSE Loss

## 📁 Repository Structure
* `AI psychology.ipynb`: The primary notebook for training and execution.
* `psychology_model.pth`: The saved state dictionary of the trained model.
* `combined_dataset (1).json`: The psychology Q&A dataset used for training.

## 🚀 How to Run
1. **Prepare Google Drive:** Create a folder named `Aiproject` in your My Drive.
2. **Upload Data:** Place `combined_dataset (1).json` into that folder.
3. **Run Notebook:** Open the `.ipynb` file in Google Colab and run all cells.
4. **Auto-Load:** The script will automatically check for `psychology_model.pth`. If it exists, it loads it instantly; if not, it triggers a 20-epoch training cycle.
5. **Interactive Chat:** Once loaded, you can type your feelings or questions into the "You:" prompt. Type `exit` to stop.

## 📊 Methodology (Mathematics)
During inference, the model takes your input, predicts a target vector, and then uses **Cosine Similarity** to find the closest match in the dataset:

$$\text{similarity} = \cos(\theta) = \frac{\mathbf{A} \cdot \mathbf{B}}{\|\mathbf{A}\| \|\mathbf{B}\|}$$

This ensures that even if you phrase a question differently, the AI finds the correct semantic response.

---
*Note: This project was developed as part of academic coursework for CS students focusing on Deep Learning and NLP.*
