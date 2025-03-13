# Compression
Submission of task.
# **Analysis Report**

## **Overview**
This project uses **Float16** method.  
Compression quality is assessed by measuring **Mean Squared Error (MSE)** and comparing **statistical properties** (Mean, Standard Deviation, Skewness, Kurtosis) between the original and compressed datasets.

Analysis performed on:
- **Uniform, Gaussian, and Exponential Distributions**  
- **Two parameter sets: Previous vs. Adjusted**

---

## **Results Comparison**
### **1️⃣ Previous Distributions**
#### **Uniform: [0, 1000] Gaussian: μ=500, σ=100 Exponential: β=200 (scale parameter)**
| Distribution | Method | MSE | Mean (Original) | Mean (Compressed) | Std (Original) | Std (Compressed) | Skew (Original) | Skew (Compressed) | Kurtosis (Original) | Kurtosis (Compressed) |
|-------------|--------|------|----------------|----------------|----------------|----------------|----------------|----------------|------------------|------------------|
| **Uniform**  | Float16  | 0.0117 | 500.3345 | 500.33453 | 288.59097 | 288.5911 | -0.0007 | -0.0007 | -1.1994 | -1.1994 |
| **Gaussian** | Float16  | 0.0122 | 499.80466 | 499.80463 | 100.10974 | 100.10982 | 0.0004 | 0.0004 | 0.0021 | 0.0020 |
| **Exponential** | Float16  | 0.0034 | 200.1206 | 200.12077 | 199.64941 | 199.6497 | 1.9757 | 1.9757 | 5.7504 | 5.7504 |

---

### **2️⃣ Adjusted Distributions**
#### **Uniform: [0, 10000] Gaussian: μ=1000, σ=500 Exponential: β=50 (scale parameter)**
| Distribution | Method | MSE | Mean (Original) | Mean (Compressed) | Std (Original) | Std (Compressed) | Skew (Original) | Skew (Compressed) | Kurtosis (Original) | Kurtosis (Compressed) |
|-------------|--------|------|----------------|----------------|----------------|----------------|----------------|----------------|------------------|------------------|
| **Uniform**  | Float16  | 1.5876 | 4996.6284 | 4996.6284 | 2887.7085 | 2887.7104 | 0.0012 | 0.0012 | -1.2006 | -1.2006 |
| **Gaussian** | Float16  | 0.0526 | 1000.3719 | 1000.3724 | 499.82144 | 499.82205 | 0.0025 | 0.0025 | -0.0060 | -0.0060 |
| **Exponential** | Float16  | 0.0002 | 50.014774 | 50.014755 | 50.018337 | 50.01832 | 1.9969 | 1.9969 | 5.9878 | 5.9879 |

