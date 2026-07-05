# 💜 Mermaid Showcase

---

# 1️⃣ Minimal Pipeline

```mermaid
%%{init: {
'theme':'base',
'themeVariables':{
'primaryColor':'#F3E8FF',
'primaryBorderColor':'#8B5CF6',
'primaryTextColor':'#2E1065',
'lineColor':'#8B5CF6'
}}}%%

flowchart LR

A["📊 Dataset"]
-->B["🔢 Vectors"]
-->C["🧮 Matrices"]
-->D["📐 Geometry"]
-->E["🌟 Eigen"]
-->F["📦 LU"]
-->G["📉 SVD"]
-->H["📊 PCA"]
-->I["🎯 LDA"]
-->J["💡 Insights"]
```

---

# 2️⃣ Dashboard Architecture

```mermaid
flowchart TB

subgraph DATA
A["📊 Student Dataset"]
end

subgraph MATHEMATICS
B["🔢 Vectors"]
C["🧮 Matrices"]
D["📐 Geometry"]
E["🌟 Eigen Analysis"]
end

subgraph MACHINE LEARNING
F["📦 LU"]
G["📉 SVD"]
H["📊 PCA"]
I["🎯 LDA"]
end

subgraph OUTPUT
J["💡 Insights"]
end

A --> B
B --> C
C --> D
D --> E
E --> F
F --> G
G --> H
H --> I
I --> J

style DATA fill:#F5F3FF,stroke:#8B5CF6
style MATHEMATICS fill:#F3E8FF,stroke:#8B5CF6
style MACHINE\ LEARNING fill:#EDE9FE,stroke:#8B5CF6
style OUTPUT fill:#DDD6FE,stroke:#6D28D9
```

---

# 3️⃣ Gradient Cards

```mermaid
flowchart LR

A["① Dataset"]
-->B["② Vectors"]
-->C["③ Matrix"]
-->D["④ Eigen"]
-->E["⑤ LU"]
-->F["⑥ SVD"]
-->G["⑦ PCA"]
-->H["⑧ LDA"]
-->I["⑨ Insights"]

style A fill:#FAF5FF
style B fill:#F3E8FF
style C fill:#E9D5FF
style D fill:#DDD6FE
style E fill:#C4B5FD
style F fill:#A78BFA
style G fill:#8B5CF6,color:#fff
style H fill:#7C3AED,color:#fff
style I fill:#6D28D9,color:#fff
```

---

# 4️⃣ Mind Map

```mermaid
mindmap
  root((🧮 Linear Algebra))

    Dataset

    Vectors
      Norms
      Dot Product
      Cross Product
      Projection

    Matrices
      Addition
      Multiplication
      Determinant
      Inverse

    Geometry
      Line
      Plane
      Hyperplane

    Decomposition
      LU
      SVD

    Dimensionality Reduction
      PCA
      LDA

    Insights
```

---

# 5️⃣ Timeline

```mermaid
timeline

title Student Performance Analysis

Dataset : Import Excel Dataset

Vectors : Norms
        : Dot Product
        : Projection

Matrices : Matrix Operations

Geometry : Hyperplane

Eigen : Eigenvalues

LU : Matrix Factorization

SVD : Singular Values

PCA : Reduce Dimensions

LDA : Classification

Insights : Final Conclusions
```

---

# 6️⃣ Sequence Diagram

```mermaid
sequenceDiagram

participant Dataset
participant Matrix
participant Eigen
participant PCA
participant LDA
participant Insight

Dataset->>Matrix: Create Matrix
Matrix->>Eigen: Compute Eigenvalues
Eigen->>PCA: Reduce Dimensions
PCA->>LDA: Classify Students
LDA->>Insight: Generate Insights
```

---

# 7️⃣ Circular Workflow

```mermaid
flowchart LR

Dataset --> Vectors

Vectors --> Matrix

Matrix --> Eigen

Eigen --> PCA

PCA --> LDA

LDA --> Insights

Insights -. Feedback .-> Dataset
```

---

# 8️⃣ Decision Flow

```mermaid
flowchart TD

A["📊 Dataset"]

A --> B{"Mathematical Analysis"}

B --> C["Vectors"]

C --> D["Matrices"]

D --> E["Eigen"]

E --> F["PCA"]

F --> G["LDA"]

G --> H["Insights"]
```

---

# 9️⃣ Research Pipeline

```mermaid
flowchart TB

A["📂 Input"]

B["📊 Student Dataset"]

C["🔢 Vector Analysis"]

D["🧮 Matrix Operations"]

E["📐 Geometry"]

F["🌟 Eigen"]

G["📦 LU"]

H["📉 SVD"]

I["📊 PCA"]

J["🎯 LDA"]

K["💡 Results"]

A --> B --> C --> D --> E --> F --> G --> H --> I --> J --> K
```

---

# 🔟 Metro Style

```mermaid
flowchart TB

A((Dataset))
|
B((Vectors))
|
C((Matrices))
|
D((Geometry))
|
E((Eigen))
|
F((LU))
|
G((SVD))
|
H((PCA))
|
I((LDA))
|
J((Insights))
```
