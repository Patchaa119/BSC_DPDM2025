# Chapter 1: Introduction to Data Mining

## 🔹 Data Mining คืออะไร?
กระบวนการค้นหารูปแบบ (patterns), ความสัมพันธ์ (relationships) และความรู้จากข้อมูลจำนวนมาก

## 🔹 ขั้นตอนหลัก (KDD Process)
1. Data Cleaning
2. Data Integration
3. Data Selection
4. Data Transformation
5. Data Mining
6. Pattern Evaluation
7. Knowledge Presentation

## 🔹 งานหลักของ Data Mining
- Classification
- Regression
- Clustering
- Association Rule
- Anomaly Detection

## 🔹 Applications
- Marketing
- Healthcare
- Finance
- Recommendation Systems
----------------------------------------------------------------------------------------------------

# Chapter 2: Getting to Know Your Data

## 🔹 Data Objects & Attributes
- Data object = entity (row)
- Attribute = feature (column)

## 🔹 Types of Attributes
- Nominal (สี)
- Binary (0/1)
- Ordinal (อันดับ)
- Numeric
  - Interval
  - Ratio

## 🔹 Data Types
- Record data
- Graph data
- Time-series
- Spatial data

## 🔹 Basic Statistics
- Mean
- Median
- Mode
- Variance
- Standard Deviation

## 🔹 Visualization
- Histogram
- Boxplot
- Scatter plot

## 🔹 Similarity / Distance
- Euclidean
- Manhattan
- Cosine similarity

📌 ใช้สำหรับ preprocessing และเข้าใจข้อมูล :contentReference[oaicite:0]{index=0}
---------------------------------------------------------------------------------------------------

# Chapter 3: Data Preprocessing

## 🔹 ทำไมต้อง preprocessing?
ข้อมูลจริงมี noise, missing, inconsistent

## 🔹 ขั้นตอนหลัก

### 1. Data Cleaning
- Missing value
- Noise
- Outlier

### 2. Data Integration
- รวมหลาย dataset

### 3. Data Transformation
- Normalization (Min-Max, Z-score)
- Aggregation

### 4. Data Reduction
- Feature selection
- Dimensionality reduction

### 5. Discretization
- Continuous → categorical

📌 สำคัญมากก่อนเข้า ML
----------------------------------------------------------------------------------------------------

# Chapter 6: Classification

## 🔹 คืออะไร?
การทำนาย class label

## 🔹 Models สำคัญ

### 🌳 Decision Tree
- ใช้ Entropy + Information Gain
- Top-down, recursive

### 📊 Naive Bayes
- ใช้ Bayes Theorem
- สมมติ independence

### 📏 KNN
- ดูเพื่อนบ้านใกล้สุด

### 🤖 Perceptron
- Linear classifier

---

## 🔹 Evaluation

- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-score

---

## 🔹 Overfitting
- แก้ด้วย pruning
---------------------------------------------------------------------------------------------------

# Chapter 6: Classification

## 🔹 ความหมาย
Classification คือการสร้างโมเดลเพื่อทำนาย class label (เช่น rain / no_rain)

---

## 🔹 ขั้นตอนของ Classification
1. Training: สร้าง model จาก training data  
2. Testing: ทดสอบกับ test data  
3. Evaluation: วัดประสิทธิภาพ  

---

## 🔹 Decision Tree

### แนวคิด
- ใช้การแบ่งข้อมูลเป็นลำดับขั้น
- เลือก feature ที่ดีที่สุดด้วย Information Gain

### สูตร Entropy
H(D) = - Σ p_i log2(p_i)

### สูตร Information Gain
Gain(A) = H(D) - Σ (|D_v| / |D|) H(D_v)

---

### ขั้นตอน
1. คำนวณ Entropy ของ dataset  
2. คำนวณ Gain ของทุก feature  
3. เลือก feature ที่ Gain สูงสุด  
4. split data  
5. ทำซ้ำ (recursive)

---

### Stopping Condition
- Entropy = 0 (pure node)
- ถึง max_depth
- จำนวนข้อมูลน้อยเกินไป

---

### ข้อดี
- เข้าใจง่าย
- ไม่ต้อง normalize

### ข้อเสีย
- Overfitting
- Sensitive ต่อ noise

---

## 🔹 Naive Bayes

### แนวคิด
ใช้ Bayes theorem โดยสมมติว่า feature เป็นอิสระ

### สูตร
P(Y|X) ∝ P(Y) Π P(X_i|Y)

---

### ขั้นตอน
1. คำนวณ Prior  
2. คำนวณ Likelihood  
3. ใช้ Laplace Smoothing  
4. คำนวณ posterior  
5. เลือก class ที่ probability สูงสุด  

---

### Laplace Smoothing
P = (count + 1) / (N + k)

---

### ข้อดี
- เร็ว
- ใช้กับ categorical ได้ดี

### ข้อเสีย
- Independence assumption ไม่จริงเสมอ

---

## 🔹 K-Nearest Neighbors (KNN)

### แนวคิด
- ใช้ “เพื่อนบ้านที่ใกล้ที่สุด”  
- Majority vote

### Distance
- Euclidean:
d = sqrt(Σ (x_i - y_i)^2)

---

### ขั้นตอน
1. เลือก K  
2. คำนวณ distance  
3. เลือก K ตัวที่ใกล้ที่สุด  
4. vote class  

---

### ข้อดี
- ง่าย
- ไม่ต้อง train

### ข้อเสีย
- ช้า
- sensitive ต่อ scale

---

## 🔹 Perceptron

### แนวคิด
- Linear classifier
- ใช้ weight + bias

### สูตร
y = sign(w·x + b)

---

### Update Rule
w = w + η y x

---

## 🔹 Evaluation Metrics

### Confusion Matrix

|        | Pred + | Pred - |
|--------|--------|--------|
| Actual + | TP | FN |
| Actual - | FP | TN |

---

### Accuracy
Accuracy = (TP + TN) / Total

### Precision
Precision = TP / (TP + FP)

### Recall
Recall = TP / (TP + FN)

### F1-score
F1 = 2PR / (P + R)

---

## 🔹 Overfitting & Underfitting

- Overfitting: model ซับซ้อนเกิน
- Underfitting: model ง่ายเกิน

---

## 🔹 Model Selection
- ใช้ validation
- เปรียบเทียบหลาย model
---------------------------------------------------------------------------------------------------

# Chapter 8: Clustering

## 🔹 ความหมาย
Clustering คือการจัดกลุ่มข้อมูลโดยไม่มี label

---

## 🔹 ประเภท

- Partitioning
- Hierarchical
- Density-based

---

## 🔹 K-Means

### ขั้นตอน
1. เลือก K  
2. สุ่ม centroid  
3. assign cluster  
4. update centroid  
5. ทำซ้ำจน converge  

---

### Objective Function
Minimize:
Σ distance(point, centroid)

---

### ข้อดี
- เร็ว
- เข้าใจง่าย

### ข้อเสีย
- ต้องกำหนด K
- sensitive ต่อ outlier

---

## 🔹 Hierarchical Clustering

### แบบ
- Agglomerative (bottom-up)
- Divisive (top-down)

---

### Linkage
- Single
- Complete
- Average

---

## 🔹 DBSCAN

### แนวคิด
- ใช้ density

### Parameters
- eps
- minPts

---

### ข้อดี
- หา shape แปลก ๆ ได้
- ไม่ต้องกำหนด K

---

## 🔹 Evaluation

### Silhouette Score
ใกล้ 1 = ดี
---------------------------------------------------------------------------------------------------

# Chapter 9: Association Rule Mining

## 🔹 ความหมาย
ค้นหาความสัมพันธ์ เช่น A → B

---

## 🔹 Metrics

### Support
Support(A→B) = P(A ∩ B)

---

### Confidence
Confidence = P(B|A)

---

### Lift
Lift = Confidence / P(B)

---

## 🔹 Apriori Algorithm

### แนวคิด
- ถ้า itemset ไม่ frequent → subset ก็ไม่ frequent

---

### ขั้นตอน
1. หา frequent 1-itemset  
2. สร้าง candidate  
3. prune  
4. ทำซ้ำ  

---

## 🔹 FP-Growth
- เร็วกว่า Apriori
- ใช้ FP-tree
