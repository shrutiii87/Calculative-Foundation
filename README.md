<div>
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:020617,8:0F172A,18:1E293B,30:312E81,42:4338CA,55:6D28D9,68:8B5CF6,80:A855F7,90:C026D3,100:F472B6&height=250&section=header&text=Calculative%20Foundation&fontSize=56&fontColor=ffffff&animation=twinkling&fontAlignY=34&desc=Exploring%20the%20Mathematical%20Foundations%20of%20Data%20Analysis&descAlignY=61&descSize=21"/>

</div>

This project applies **Linear Algebra** concepts to analyze a student performance dataset using both mathematical theory and practical implementation.

This project demonstrates the application of **Linear Algebra** on a student performance dataset. It covers vector and matrix operations, norms, dot products, cross products, vector projections, LU decomposition, SVD, PCA, LDA, and eigenvalue analysis. Using Python, Excel, and manual calculations, the project highlights how mathematical concepts are applied in Data Science, Machine Learning, and AI.


---

🎯 Objective

analyzing and transforming a dataset using Linear Algebra concepts to derive meaningful insights. The project integrates vectors, matrices, decompositions, and dimensionality reduction techniques to give students hands-on practice in mathematical foundations widely applied in Data Science, AI/ML, and Engineering.

---

## 🗂️ Project Files


| File                                   | Description                                                     |
| -------------------------------------- | --------------------------------------------------------------- |
| 📓 `calculative_foundation.ipynb`      | Complete Linear Algebra analysis and Python implementation      |
| 📊 `student_performance_dataset.xlsx`  | Student performance dataset                                     |
| 📄 `Calculative_Foundation_Report.pdf` | Theory, mathematical derivations, formulas, and interpretations |
| 🖼️ `Diagrams/`                        | Linear Algebra diagrams and visualizations                      |
| 📘 `README.md`                         | Project documentation                                           |

---

🛠️ Tools Used

<div>
  
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white"/>
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white"/>
<img src="https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white"/>
<img src="https://img.shields.io/badge/Linear_Algebra-6A1B9A?style=for-the-badge"/>
<img src="https://img.shields.io/badge/PCA-0EA5E9?style=for-the-badge"/>
<img src="https://img.shields.io/badge/LDA-EC4899?style=for-the-badge"/>
<img src="https://img.shields.io/badge/SVD-7C3AED?style=for-the-badge"/>
<img src="https://img.shields.io/badge/LU_Decomposition-059669?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Eigenvalues_&_Eigenvectors-F59E0B?style=for-the-badge"/>

</div>

---

# 🎬 Project Demo

[![Watch Demo](https://img.shields.io/badge/▶️%20Watch%20Demo-Google%20Drive-blue?style=for-the-badge&logo=google-drive)](https://drive.google.com/file/d/1V1D9kEmD8bw9lGKjR7WO2MhYfowj-BYg/view?usp=sharing)

📹 Click the badge above to watch the complete project demonstration.

---

### 📜 Theory part 

<img width="800" height="420" alt="ezgif-2ef048b9399a16bb" src="https://github.com/user-attachments/assets/04ecbccb-d1a3-4f7a-8dd4-a3e88c4b1d8e" />

### 📝 Jupyter notebook 

<img width="800" height="420" alt="ezgif-1c1f29978ef62004" src="https://github.com/user-attachments/assets/415f9b3e-394f-4a27-931c-29f41d920d13" />

---

## 📗 Statistical Topics Covered

---

#### 🛠️ imported libraries

```python
import pandas as pd
import numpy as np
from scipy.linalg import lu
from sklearn.decomposition import PCA
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
```

---

## 📏 PART :- A Vector & Matrix Fundamentals

### 🔢 Q1 Represent each student's subject scores as a vector.

```python
# Select only subject columns
data = df[["Math", "Physics", "Chemistry", "English", "Computer"]].values

# Student vectors
v1 = data[0]   # S01
v2 = data[1]   # S02

print("Student 1 (S01) Vector:", v1)
print("Student 2 (S02) Vector:", v2)
```
#### 🎯 Insight:
- Each student is now a 5-dimensional vector in the subject space. S01 = high performer 🏆, S02 = average performer.

---

### 🔢 Q2. Compute:

#### 🔷 (a) Norm-1 and Norm-2 of vectors

```python
l1 = np.linalg.norm(v1, ord=1)
l2 = np.linalg.norm(v1, ord=2)
print("\nL1 Norm:", l1)
print("L2 Norm:", l2)
```
#### 📏 Interpretation:
- L1 norm = 443 → total marks scored by S01 (sum of absolute values).
- L2 norm ≈ 198.54 → geometric length of the score vector in 5-D space.
- Both confirm S01 is a strong scorer overall. 🌟

---

#### 🔷 (b) Dot product and angle between two students’ score vectors.

```python
dot = np.dot(v1, v2)
angle = np.arccos(dot / (np.linalg.norm(v1) * np.linalg.norm(v2)))
angle_deg = np.degrees(angle)
print("\nDot Product:", dot)
print("Angle (Degrees):", angle_deg)
```

#### 📐 Insight:
- Angle between S01 and S02 is only ≈ 5.73° — extremely small ➡️ the two students’ score patterns point in almost the same direction in vector space 🎯.
-  They differ in magnitude (S01 > S02) but not in shape of performance.

---

#### 🔷 (c) Cross product (for 3D selected subjects).

```python
A3 = df.loc[df["Student_ID"]=="S01",
            ["Math","Physics","Chemistry"]].values.flatten()
B3 = df.loc[df["Student_ID"]=="S02",
            ["Math","Physics","Chemistry"]].values.flatten()
cross_product = np.cross(A3,B3)
print("Student S01 :",A3)
print("Student S02 :",B3)
print("\nCross Product =")
print(cross_product)
```

#### ✖️ Interpretation:
- The cross product [36, 126, -160] is a vector perpendicular to both S01 and S02 in the Math–Physics–Chemistry space.
-  A non-zero result confirms the two vectors are not parallel in 3D.

---

### 🔢 Q3. Find the projection of one vector onto another.

```python
projection = (np.dot(v1, v2) / np.dot(v2, v2)) * v2
print("Projection of S01 onto S02")
print(np.round(projection,2))
```

#### 🎯 Insight:
- The projection shows how much of S01 lies along the direction of S02.
-  Since the projected vector [89.21, 83.26, 85.64, 95.15, 88.02] is very close in magnitude to S01’s own values, S01 and S02 share a highly aligned performance direction. 🔗

---

## ⚙️ Part B: Matrix Operations

### 🔢  Q4. form a matrix of students × subjects. Perform:

```python
A = data
print("Matrix A (First 5 Students):")
print(A[:5])
```

#### 🧮 Interpretation:
- Matrix A stacks students as rows and subjects as columns — the fundamental structure used for every matrix operation below.

---

#### 🔷 (a) Matrix addition and multiplication.

```python
# Matrix Addition
add = A[:5] + A[:5]
# Matrix Multiplication
mul = np.dot(A[:5], A[:5].T)
print("Matrix Addition (A + A):")
print(add)
print("\nMatrix Multiplication (A × Aᵀ):")
print(mul)
```

####  ➕✖️ Insight:
- A + A simply doubles every score.
- A × Aᵀ produces the Gram matrix — diagonal entries (e.g. 39417 for S01) represent each student’s squared vector length, off-diagonals measure similarity between students. Larger value = more similar score pattern. 🔗

---

#### 🔷 (b) Transpose and Inverse (if possible).

```python
# Transpose
transpose = A[:5].T
print("\nTranspose of Matrix:")
print(transpose)
# First 5 students × 5 subjects (5×5 matrix)
B = A[:5, :]
print("\n5×5 Square Matrix:")
print(B)
# Inverse
inv = np.linalg.inv(B[:5])
print("\nInverse Matrix:")
print(inv)
```

#### 🔁 Interpretation:
- The transpose flips rows↔columns (subjects become rows).
- The inverse exists because the 5×5 matrix is non-singular
- meaning the 5 student vectors are linearly independent, spanning the full subject space. ✅

---

#### 🔷 (c) Determinant.

```python
# Determinant
det = np.linalg.det(B)
print("\nDeterminant:")
print(det)
```

#### 🧾 Insight: 
-  Determinant ≈ -88,346 (non-zero) ➡️ the matrix is invertible and the 5 student score vectors are linearly independent.
-  The negative sign indicates the transformation reverses orientation 🔄.

---

## 📊 Part C: Linear Transformations & Geometry

### 🔢  Q5. Explain line, plane, and hyperplane with respect to your dataset dimensions.

```python
# LINE (1D)
line = df[["Math"]]
print("Line (1D)")
print(line.head())
# PLANE (2D)
plane = df[["Math", "Physics"]]
print("\nPlane (2D)")
print(plane.head())
# HYPERPLANE (5D)
hyperplane = df[["Math", "Physics", "Chemistry", "English", "Computer"]]
print("\nHyperplane (5D)")
print(hyperplane.head())
```

#### 📐 Interpretation:
- Line (1D) → single subject (Math) — a number line.
- Plane (2D) → Math vs Physics — a flat 2-axis space.
- Hyperplane (5D) → all subjects — impossible to visualise but mathematically valid, where each student is a single point. 🌐

---

### 🔢 Q6. Show how dimensionality increases from 2D → 3D → higher dimensions with hyperplanes.

```python
# 2D
two_d = df[["Math", "Physics"]]
print("2D Shape:", two_d.shape)
# 3D
three_d = df[["Math", "Physics", "Chemistry"]]
print("3D Shape:", three_d.shape)
# 5D
five_d = df[["Math", "Physics", "Chemistry", "English", "Computer"]]
print("5D Shape:", five_d.shape)
```
#### 📈 Insight:
- As we add subjects, dimensionality grows 2D → 3D → 5D. Rows stay 50 (students) while columns (features) increase
- this is exactly why techniques like PCA/LDA later become necessary to compress high-D data. 🔽

---

## 📉 Part D: Eigenvalues & Decomposition

### 🔢 Q7.Compute the eigenvalues and eigenvectors of the covariance matrix.

```python
# Select subject columns
data = df[["Math","Physics","Chemistry","English","Computer"]]
# Covariance Matrix
cov_matrix = np.cov(data.T)
print("Covariance Matrix:")
print(cov_matrix)
# Eigenvalues and Eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(cov_matrix)
print("\nEigenvalues:")
print(eigenvalues)
print("\nEigenvectors:")
print(eigenvectors)
```

#### 🌟 Key Insight — Eigen Analysis:
- Eigenvalues: [665.8, 4.01, 2.23, 1.11, 1.38]
- The first eigenvalue dominates (~98.6% of total variance) ➡️ one principal direction explains almost the entire variation among students.
- Interpretation: students mostly differ along a single axis of overall academic ability 🎓, not across independent subject strengths.

---

### 🔢  Q8. Perform LU Decomposition of the dataset matrix.

```python
from scipy.linalg import lu
# Use first 5 students to form a 5×5 square matrix
A = df[["Math","Physics","Chemistry","English","Computer"]].values[:5,:]
# LU Decomposition
P, L, U = lu(A)
print("Matrix A:")
print(A)
print("\nPermutation Matrix (P):")
print(P)
print("\nLower Triangular Matrix (L):")
print(L)
print("\nUpper Triangular Matrix (U):")
print(U)
```

#### 🔺 Interpretation (LU): 
- Matrix A = P · L · U — decomposed into Permutation, Lower- and Upper-triangular parts.
- This factorisation makes solving linear systems and computing determinants much faster ⚡ and is numerically stable due to pivoting (P).

---

### 🔢  Q9. Perform Singular Value Decomposition (SVD) and explain its role in dimensionality reduction.

```python
# Dataset matrix
A = df[["Math","Physics","Chemistry","English","Computer"]].values
# Singular Value Decomposition
U, S, VT = np.linalg.svd(A)
print("Matrix U:")
print(U)
print("\nSingular Values:")
print(S)
print("\nMatrix Vᵀ:")
print(VT)
```

#### 🧩 Insight (SVD):
- SVD factorises the data as A = U · Σ · Vᵀ.
- Singular values (S) rank the importance of each direction.
- Keeping only the top-k singular values gives an optimal low-rank approximation
- the mathematical foundation of dimensionality reduction, compression, and noise removal 🎯.

---

## 📈 Part E: Dimensionality Reduction

### 🔢 Q10. Apply Principal Component Analysis (PCA) to reduce the dataset from multiple subjects to 2 dimensions.

```python
from sklearn.decomposition import PCA
pca = PCA(n_components=2)
reduced = pca.fit_transform(A)
print("Reduced Data (2D):\n", reduced[:5])
```

#### 🎨 Insight (PCA → 2D):
- The 5-D subject space is compressed to 2 components while preserving maximum variance.
- Notice how Above Average students get large positive PC1 values (e.g. 23.5, 19.8, 35.3)
- Below Average students get negative PC1 values (-11.2, -31.6). PC1 clearly encodes overall performance. 📉📈

---

### 🔢 Q11. Apply Linear Discriminant Analysis (LDA) to classify students into “Above Average” and “Below Average” categories.

```python
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
# Features
X = df[["Math", "Physics", "Chemistry", "English", "Computer"]].values
# Convert labels to numbers
y = df["Category"].map({
    "Above Average": 1,
    "Below Average": 0
})
# Create LDA object
lda = LinearDiscriminantAnalysis(n_components=1)
# Transform the data
lda_result = lda.fit_transform(X, y)
print("LDA Result:")
print(lda_result[:5])
```

#### 🧭 Insight (LDA):
- LDA projects the 5-D data onto one axis that best separates the two classes.
- Positive LDA scores → Above Average 🌟, negative → Below Average 📉.
- The clean sign-split (e.g. +4.28, +2.40, +3.50 vs −2.46, −1.79) shows the two groups are linearly separable — LDA is an excellent classifier for this dataset. ✅

---

## 🏁 Overall Conclusion & Key Takeaways

#### 📌 Dataset Summary :- 
- 50 students × 5 subjects — clean data, no missing values ✅
- Average performance is highest in Computer 💻 and most consistent in English 📖

#### 🔗 Vector & Matrix Findings :- 
- The first eigenvalue captures ≈ 98.6% of total variance — a single latent factor (overall academic ability 🎓) drives the dataset.
- Both PCA and LDA confirm this: PC1 and the LDA axis cleanly separate Above Average from Below Average students.

#### 🌟 Eigen / SVD / PCA Insights :- 
- The first eigenvalue captures ≈ 98.6% of total variance — a single latent factor (overall academic ability 🎓) drives the dataset.
- Both PCA and LDA confirm this: PC1 and the LDA axis cleanly separate Above Average from Below Average students.

#### 🧭 Practical Implications :- 
- The dataset is effectively 1-dimensional in nature — one score summarises a student well.
- LDA is a reliable classifier for the Above / Below Average label because the two classes are linearly separable.
- Techniques like PCA & SVD are ideal for compressing or visualising this multi-subject data without significant information loss. 🎯

#### ✅ Final Verdict :- 
- The mathematical foundation — vectors, matrices, eigen decomposition, SVD, PCA and LDA — collectively reveal that student performance across subjects is strongly correlated and low-dimensional in structure, making the data both well-behaved and highly predictable. 🚀

---

# 🚀 How to Run

Install the required libraries:

```bash
pip install pandas numpy scipy scikit-learn
```

Open Jupyter Notebook:

```bash
jupyter notebook
```

Run the notebook:

```text
Calculative_foundation.ipynb
```

---


## 👩‍💻 Shruti Bhawsar

📍 Ahmedabad | 

[![GitHub](https://img.shields.io/badge/GitHub-shrutiii87-181717?style=flat&logo=github)](https://github.com/shrutiii87)

---

⭐ **If You Like This Project**

Give this repository a ⭐ and feel free to fork or contribute!

📊 *Clean Models · Sharp DAX · Confident Insights*

