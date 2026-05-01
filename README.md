# Network Intrusion Detection System (NIDS)

A deep learning-based **Network Intrusion Detection System** that classifies network traffic into multiple threat categories using a fully connected neural network built with Keras and TensorFlow.

---

## Project Overview

This project applies machine learning techniques to the problem of network security monitoring. By training a multi-layer neural network on labeled network traffic data, the model is able to distinguish between normal traffic and different types of cyber attacks.

### Key Steps
- **Data Preprocessing** — Null value inspection, label encoding, and feature scaling with `StandardScaler`
- **Dimensionality Reduction** — PCA applied to reduce features to the 10 most significant components
- **Model Architecture** — A Sequential neural network with 4 dense layers (128 → 64 → 32 → 3)
- **Training & Evaluation** — Trained with the Adam optimizer and evaluated on a held-out test set

---

## Model Architecture

| Layer | Units | Activation |
|-------|-------|------------|
| Input Dense | 128 | ReLU |
| Hidden Dense | 64 | ReLU |
| Hidden Dense | 32 | ReLU |
| Output Dense | 3 | Softmax |

- **Loss Function:** Sparse Categorical Crossentropy  
- **Optimizer:** Adam  
- **Metrics:** Accuracy

---

## Project Structure

```
project_CI_Sec/
│
├── project_CI_Sec.ipynb   # Main Jupyter Notebook
├── dataset.csv            # Network traffic dataset (not included — see Data section)
├── requirements.txt       # Python dependencies
├── .gitignore             # Files and folders excluded from version control
└── README.md              # Project documentation
```

---

## Dataset

The model expects a CSV file named `dataset.csv` with the following structure:

- All columns except `Target` are treated as numerical features
- The `Target` column contains the class label (e.g., Normal, Attack Type A, Attack Type B)

> **Note:** The dataset is not included in this repository. Place your `dataset.csv` file in the project root directory before running the notebook.

---

## Installation

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/project_CI_Sec.git
cd project_CI_Sec
```

### 2. Create a Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

---

## Usage

1. Place your `dataset.csv` in the project root directory
2. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
3. Open `project_CI_Sec.ipynb` and run all cells sequentially

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `scikit-learn` | Preprocessing, PCA, train-test split |
| `keras` / `tensorflow` | Neural network definition and training |
| `jupyter` | Interactive notebook environment |

---

## Results

The model is evaluated using accuracy on the test set after 10 training epochs with a batch size of 128. Further improvements can be achieved by tuning hyperparameters, adding dropout layers, or experimenting with different architectures.

---

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

---

## License

This project is licensed under the [MIT License](LICENSE).
