# KNN_SVC-Classification
This project trains and evaluates multiple classification models (including **K-Nearest Neighbors** and **Support Vector Machines**) on the *Social_Network_Ads* dataset.
It covers data preprocessing (label encoding, scaling), exploratory analysis, model training, and visual evaluation.
The notebook is fully self-contained and can be executed **locally**, in **Google Colab**, or through **VS Code using a Colab kernel**.

---

## Features

* Dataset ingestion and cleaning
* Exploratory visualizations (matplotlib + seaborn)
* Label encoding and Min-Max scaling
* Model training:
  * KNN
  * SVC (linear / polynomial / RBF, depending on your notebook)
* Performance evaluation
* Notes on class imbalance and metric reliability

---

## Repository Structure

```
.
├── notebook.ipynb
├── data/
│   └── Social_Network_Ads.csv
└── README.md
```

---

## 1. Running in Google Colab (Recommended)

### **Method A — Upload directly**

1. Go to [https://colab.research.google.com](https://colab.research.google.com)
2. Upload `notebook.ipynb`
3. Upload `Social_Network_Ads.csv` manually or mount Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

### **Method B — Clone GitHub repo in Colab**

```python
!git clone https://github.com/<your-username>/<your-repo>.git
%cd <your-repo>
```

Run the notebook normally.

---

## 2. Running Locally

### **Prerequisites**

* Python ≥ 3.8
* Recommended: virtual environment (`venv` or `conda`)

### **Install dependencies**

```bash
pip install -r requirements.txt
```

OR

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### **Start Jupyter Notebook**

```bash
jupyter notebook
```

Open `notebook.ipynb` and run all cells.

---

## 3. Running in VS Code Using a Google Colab Server

This allows VS Code to use Colab's GPU/TPU while you code locally.

Because this runtime is still Google Colab, it cannot access files on your local machine.
Your CSV must therefore be provided via Google Drive, manual upload, or stored inside your GitHub repo and cloned in the notebook.

### **Steps**

1. Install extension:
   **VS Code Marketplace → "Google Colab"**
2. In VS Code, open the notebook (`notebook.ipynb`)
3. Command Palette →
   **“Connect to Google Colab”**
4. Authenticate via the popup
5. Select a Colab runtime (CPU / GPU / TPU)
6. Execute cells directly in VS Code with Colab as your execution backend

You get Colab hardware acceleration without leaving your IDE but remember that local files are not accessible—your dataset must be uploaded, in Drive, or in your repo.

---

## Dataset

The project uses **Social_Network_Ads.csv**, which includes:

* Gender
* Age
* Estimated Salary
* Purchased (target)

Scaling & encoding are applied appropriately before model training.

---

## Reproducibility

To ensure consistent runs:

* Random seeds can be set in model constructors
* Scaling is always fitted only on training data
* Encoders are persisted inside the notebook pipeline

---

