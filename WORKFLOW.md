# 🚀 Usage Workflow

This guide explains how to replicate the study and run the `VirusID` analysis using Google Colab.

## 🛠 Prerequisites

-   **Google Account** (for Colab & Drive).
-   **Dataset**: You need the spectral data CSV files (`20210329_train.csv`, `20210329_test.csv`).
    -   *Note: Links to datasets are available in `README_OLD.md`.*

## 🏃‍♂️ Running the Analysis

### 1. Download Dataset
**Crucial Step**: You must first download the training and testing datasets.
-   The links for `20210329_train.csv` and `20210329_test.csv` are provided in the **[README_OLD.md](README_OLD.md)** file.
-   Download these files to your local machine or Google Drive.

### 2. Setup Google Drive (for Colab Users)
The notebook is configured to use Google Drive for data persistence.
1.  Create a folder in your Drive: `My Drive/AI/Colab`.
2.  Upload the `.csv` dataset files to this folder.

### 3. Open the Notebook
1.  Open `FANFAN_3.ipynb` in [Google Colab](https://colab.research.google.com/).
2.  *Alternative*: Upload the `.ipynb` file from this repository directly to Colab.

### 4. Mount Drive
The first cell includes code to mount your Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
```
Follow the authentication prompts in the browser.

### 5. Configure Paths
Ensure the path in the notebook matches your folder structure:
```python
%cd '/content/drive/MyDrive/AI/Colab'
```
*If you saved files elsewhere, update this line to match your path.*

### 6. Run All
Select **Runtime > Run all** from the menu.

## 💻 Local Execution

You can also train and test this model on your local machine (with GPU support recommended).

1.  **Clone the Repo**:
    ```bash
    git clone <repo-url>
    cd VirusID
    ```
2.  **Install Dependencies**:
    ```bash
    pip install tensorflow pandas numpy seaborn scikit-learn matplotlib
    ```
3.  **Download Data**:
    -   Download `20210329_train.csv` and `20210329_test.csv` using the links in [README_OLD.md](README_OLD.md).
    -   Place them in the `VirusID` directory (or wherever you are running the notebook).
4.  **Modify the Code**:
    -   Open `FANFAN_3.ipynb` in Jupyter Lab or VS Code.
    -   **Remove/Comment out** the Colab-specific blocks:
        ```python
        # from google.colab import drive
        # drive.mount('/content/drive')
        # %cd '/content/drive/MyDrive/AI/Colab'
        ```
    -   **Update File Paths**: Ensure the `pd.read_csv()` calls point to your local files:
        ```python
        data = pd.read_csv('20210329_train.csv') # Ensure this path is correct relative to the notebook
        ```
5.  **Run**: Execute the cells.
