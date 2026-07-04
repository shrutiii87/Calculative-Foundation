# Calculative Foundation

## Overview
This project applies vector and matrix concepts to a student performance dataset using Python and NumPy. It demonstrates how to represent student marks as vectors, calculate norms, compute dot products, measure angles, and explore cross products in a practical data-analysis setting.

## Tools and Libraries
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

## Project Files
| File | Description |
|---|---|
| `Student_Performance.xlsx` | Dataset used for analysis |
| `README.md` | Project documentation |
| `Notebook` | Python code for vector and matrix operations |

## Dataset Summary
The dataset contains 50 student records with the following columns:

| Column | Type | Description |
|---|---|---|
| `Student_ID` | Categorical | Unique student identifier |
| `Math` | Numerical | Math score |
| `Physics` | Numerical | Physics score |
| `Chemistry` | Numerical | Chemistry score |
| `English` | Numerical | English score |
| `Computer` | Numerical | Computer score |
| `Category` | Categorical | Performance category |

## Data Snapshot
```python
import pandas as pd
import numpy as np

df = pd.read_excel("Student_Performance.xlsx")
print("read excel file succesfully !")
df.head()
```

## Code in Question
### Q1. Represent each student’s subject scores as a vector.
```python
# Select only subject columns
data = df[["Math", "Physics", "Chemistry", "English", "Computer"]].values

# Student vectors
v1 = data[0]   # S01
v2 = data[1]   # S02

print("Student 1 (S01) Vector:", v1)
print("Student 2 (S02) Vector:", v2)
```

### Q2. Compute Norm-1 and Norm-2 of vectors.
```python
l1 = np.linalg.norm(v1, ord=1)
l2 = np.linalg.norm(v1, ord=2)

print("
L1 Norm:", l1)
print("L2 Norm:", l2)
```

### Q2(b). Compute dot product and angle between two students’ score vectors.
```python
dot = np.dot(v1, v2)

angle = np.arccos(dot / (np.linalg.norm(v1) * np.linalg.norm(v2)))
angle_deg = np.degrees(angle)

print("
Dot Product:", dot)
print("Angle (Degrees):", angle_deg)
```

### Q2(c). Compute cross product for selected 3D subjects.
```python
A3 = df.loc[df["Student_ID"]=="S01", ["Math","Physics","Chemistry"]].values.flatten()
B3 = df.loc[df["Student_ID"]=="S02", ["Math","Physics","Chemistry"]].values.flatten()

cross_product = np.cross(A3, B3)

print("Student S01 :",A3)
print("Student S02 :",B3)
print("
Cross Product =")
print(cross_product)
```

## Key Results
The analysis shows that S01 has a higher overall score magnitude than S02, while both students have a very similar performance pattern. The small angle between their vectors indicates that their subject-wise score direction is almost the same.

The cross product is non-zero, which confirms that the two 3D subject vectors are not parallel.

## Insights
This project shows how linear algebra can be used to compare students quantitatively. Vectors help represent marks compactly, norms summarize performance size, dot product measures similarity, and cross product checks directional difference in 3D space.

## Conclusion
The notebook is a simple but effective demonstration of vector and matrix fundamentals in a real academic dataset. It is useful for understanding both mathematical concepts and their practical data-analysis application.
