<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E1B4B,25:312E81,50:4C1D95,75:6D28D9,100:A855F7&height=220&section=header&text=Calculative%20Foundation&fontSize=52&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Exploring%20the%20Mathematics%20Behind%20Modern%20Data%20Analysis&descAlignY=58&descSize=20"/>


# 🔢 Calculative Foundation – Student Performance Analytics

[![Python](https://img.shields.io/badge/Python-3.9-blue?logo=python)](https://www.python.org/)  
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)  
[![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-lightblue?logo=numpy)](https://numpy.org/)  
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-yellow?logo=pandas)](https://pandas.pydata.org/)  
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-green?logo=plotly)](https://matplotlib.org/)  
[![SciPy](https://img.shields.io/badge/SciPy-Linear%20Algebra-red?logo=scipy)](https://scipy.org/)  
[![scikit-learn](https://img.shields.io/badge/scikit--learn-Machine%20Learning-orange?logo=scikitlearn)](https://scikit-learn.org/stable/)  

---

## 📋 Project Overview

A complete **Theory + Practical Linear Algebra & Statistics Project** analyzing a **Student Performance Dataset** of 50 records.  
This project blends **mathematical foundations** with **Python implementation** to explore vectors, matrices, eigen decomposition, LU & SVD factorization, PCA, and LDA classification.

---

## 🗂️ Project Files

| File | Description |
|------|-------------|
| 📓 **Calculative_Foundation.ipynb** | Jupyter Notebook — Python code, charts & insights |
| 📊 **Student_Performance.xlsx** | Dataset — 50 students × 5 subjects |
| 📄 **Theory_Foundation.pdf** | Theory document — definitions, formulas & diagrams |
| 📘 **README.md** | Project documentation (this file) |

---

## 🔬 Full Code & Insights

```python
# Import libraries
import pandas as pd
import numpy as np
from scipy.linalg import lu
from sklearn.decomposition import PCA
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
```
# Read dataset
df = pd.read_excel("Student_Performance.xlsx")

# Q1. Represent each student’s subject scores as a vector
data = df[["Math", "Physics", "Chemistry", "English", "Computer"]].values
v1 = data[0]   # S01
v2 = data[1]   # S02

# Q2. Norms, Dot Product, Angle, Cross Product
l1 = np.linalg.norm(v1, ord=1)
l2 = np.linalg.norm(v1, ord=2)
dot = np.dot(v1, v2)
angle = np.arccos(dot / (np.linalg.norm(v1) * np.linalg.norm(v2)))
angle_deg = np.degrees(angle)
A3 = df.loc[df["Student_ID"]=="S01", ["Math","Physics","Chemistry"]].values.flatten()
B3 = df.loc[df["Student_ID"]=="S02", ["Math","Physics","Chemistry"]].values.flatten()
cross_product = np.cross(A3,B3)

# Q3. Projection of one vector onto another
projection = (np.dot(v1, v2) / np.dot(v2, v2)) * v2

# Q4. Matrix Operations
A = data
add = A[:5] + A[:5]
mul = np.dot(A[:5], A[:5].T)
transpose = A[:5].T
B = A[:5,:]
inv = np.linalg.inv(B)
det = np.linalg.det(B)

# Q5. Line, Plane, Hyperplane
line = df[["Math"]]
plane = df[["Math", "Physics"]]
hyperplane = df[["Math", "Physics", "Chemistry", "English", "Computer"]]

# Q6. Dimensionality Growth
two_d = df[["Math", "Physics"]]
three_d = df[["Math", "Physics", "Chemistry"]]
five_d = df[["Math", "Physics", "Chemistry", "English", "Computer"]]

# Q7. Eigenvalues & Eigenvectors
cov_matrix = np.cov(data.T)
eigenvalues, eigenvectors = np.linalg.eig(cov_matrix)

# Q8. LU Decomposition
A5 = df[["Math","Physics","Chemistry","English","Computer"]].values[:5,:]
P, L, U = lu(A5)

# Q9. Singular Value Decomposition (SVD)
U_svd, S, VT = np.linalg.svd(data)

# Q10. Principal Component Analysis (PCA)
pca = PCA(n_components=2)
reduced = pca.fit_transform(data)

# Q11. Linear Discriminant Analysis (LDA)
X = df[["Math", "Physics", "Chemistry", "English", "Computer"]].values
y = df["Category"].map({"Above Average": 1, "Below Average": 0})
lda = LinearDiscriminantAnalysis(n_components=1)
lda_result = lda.fit_transform(X, y)
