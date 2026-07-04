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

### Theory part 

<img width="800" height="420" alt="ezgif-2ef048b9399a16bb" src="https://github.com/user-attachments/assets/04ecbccb-d1a3-4f7a-8dd4-a3e88c4b1d8e" />

### Jupyter notebook 

<img width="800" height="420" alt="ezgif-1c1f29978ef62004" src="https://github.com/user-attachments/assets/415f9b3e-394f-4a27-931c-29f41d920d13" />

---

## 📗 Statistical Topics Covered

---

#### imported libraries

---

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

#### (a) Norm-1 and Norm-2 of vectors

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

