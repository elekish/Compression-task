# Compression
Submission of task.
# **Analysis Report**

## **Overview**
This project uses **Float16 and BitPack24** methods.  
Compression quality is assessed by measuring **Mean Squared Error (MSE)** and comparing **statistical properties** (Mean, Standard Deviation, Skewness, Kurtosis) between the original and compressed datasets.

Analysis performed on:
- **Uniform, Gaussian, and Exponential Distributions**  
- **Two parameter sets: Previous vs. Adjusted**
- **Side-by-side comparison for Float16 and BitPack24**

---

## **Results Comparison**
### **1️⃣ Previous Distributions**
| Distribution | Method | MSE | Mean (Original) | Mean (Compressed) | Std (Original) | Std (Compressed) | Skew (Original) | Skew (Compressed) | Kurtosis (Original) | Kurtosis (Compressed) |
|-------------|--------|------|----------------|----------------|----------------|----------------|----------------|----------------|------------------|------------------|
| **Uniform**  | Float16  | 0.0117 | 500.3345 | 500.33453 | 288.59097 | 288.5911 | -0.0007 | -0.0007 | -1.1994 | -1.1994 |
| **Uniform**  | BitPack24 | 333619.34 | 500.3345 | 9.75e-39 | 288.59097 | 0.0 | -0.0007 | NaN | -1.1994 | NaN |
| **Gaussian** | Float16  | 0.0122 | 499.80466 | 499.80463 | 100.10974 | 100.10982 | 0.0004 | 0.0004 | 0.0021 | 0.0020 |
| **Gaussian** | BitPack24 | 259826.68 | 499.80466 | 1.15e-38 | 100.10974 | 0.0 | 0.0004 | NaN | 0.0021 | NaN |
| **Exponential** | Float16  | 0.0034 | 200.1206 | 200.12077 | 199.64941 | 199.6497 | 1.9757 | 1.9757 | 5.7504 | 5.7504 |
| **Exponential** | BitPack24 | 79908.16 | 200.1206 | 1.11e-38 | 199.64941 | 0.0 | 1.9757 | NaN | 5.7504 | NaN |

---

### **2️⃣ Adjusted Distributions**
| Distribution | Method | MSE | Mean (Original) | Mean (Compressed) | Std (Original) | Std (Compressed) | Skew (Original) | Skew (Compressed) | Kurtosis (Original) | Kurtosis (Compressed) |
|-------------|--------|------|----------------|----------------|----------------|----------------|----------------|----------------|------------------|------------------|
| **Uniform**  | Float16  | 1.5876 | 4996.6284 | 4996.6284 | 2887.7085 | 2887.7104 | 0.0012 | 0.0012 | -1.2006 | -1.2006 |
| **Uniform**  | BitPack24 | 33305156.00 | 4996.6284 | 1.14e-38 | 2887.7085 | 0.0 | 0.0012 | NaN | -1.2006 | NaN |
| **Gaussian** | Float16  | 0.0526 | 1000.3719 | 1000.3724 | 499.82144 | 499.82205 | 0.0025 | 0.0025 | -0.0060 | -0.0060 |
| **Gaussian** | BitPack24 | 1250565.37 | 1000.3719 | 1.20e-38 | 499.82144 | 0.0 | 0.0025 | NaN | -0

