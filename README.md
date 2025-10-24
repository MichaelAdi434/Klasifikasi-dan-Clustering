# Klasifikasi dan Segmentasi Data Pelanggan

Proyek ini merupakan **Klasifikasi** dan **Clustering** menggunakan data pelanggan.

## 📁 Struktur Proyek

| File | Deskripsi |
| :--- | :--- |
| **Notebook** | |
| `[Klasifikasi]_Submission_Akhir_BMLP_...ipynb` | Notebook yang berisi proses **Klasifikasi**. Mencakup *preprocessing*, pemodelan dengan berbagai algoritma, evaluasi, dan pemilihan model terbaik. |
| `[Clustering]_Submission_Akhir_BMLP_...ipynb` | Notebook yang berisi proses **Clustering/Segmentasi**. Mencakup *preprocessing* (termasuk normalisasi/scaling), penerapan K-Means, dan analisis Principal Component Analysis (PCA). |
| **Data** | |
| `data_clustering.csv` | Dataset yang telah di-preprocessing dan dinormalisasi, khusus digunakan untuk tugas Clustering. |
| **Model Klasifikasi (Classification Models)** | |
| `Support Vector Machine_classification.h5` | Model klasifikasi terlatih menggunakan algoritma **Support Vector Machine (SVM)**. |
| `decision_tree_model.h5` | Model klasifikasi terlatih menggunakan algoritma **Decision Tree**. |
| `K-Nearest Neighbors_classification.h5` | Model klasifikasi terlatih menggunakan algoritma **K-Nearest Neighbors (KNN)**. |
| `Naive Bayes_classification.h5` | Model klasifikasi terlatih menggunakan algoritma **Naive Bayes (GaussianNB)**. |
| `Random Forest_classification.h5` | Model klasifikasi terlatih menggunakan algoritma **Random Forest**. |
| **Model Clustering (Clustering Models)** | |
| `model_clustering.h5` | Model Clustering (**K-Means**) yang telah dilatih pada data. |
| `PCA_model_clustering.h5` | Model Clustering (**K-Means**) yang dilatih pada data yang telah direduksi dimensinya menggunakan **PCA**. |

***

## 📋 Detail 

### 1. Tugas Klasifikasi

Tujuannya adalah memprediksi variabel target dari data.

* **Algoritma yang Diuji:** K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Decision Tree, Random Forest, dan Naive Bayes.
* **Proses Utama:** Data *preprocessing*, *feature engineering*, *model training* dan *hyperparameter tuning*, serta evaluasi kinerja model (menggunakan *Accuracy*, *Precision*, *Recall*, *F1-Score*).
* **Output Hasil:** Model terbaik dan ringkasan metrik disimpan.

### 2. Tugas Clustering 

Tujuannya adalah mengelompokkan pelanggan berdasarkan fitur numerik tanpa label target yang ditentukan sebelumnya.

* **Metode Utama:** **K-Means Clustering**.
* **Reduksi Dimensi:** Penerapan **Principal Component Analysis (PCA)** untuk memvisualisasikan data dan mungkin untuk meningkatkan efisiensi clustering.
* **Proses Utama:** *Data preparation*, penentuan jumlah cluster optimal (menggunakan *Elbow Method*), pemodelan, dan interpretasi karakteristik setiap cluster.

***

## 🔑 Penggunaan Model

Model-model yang disimpan dalam format `.h5` dapat dimuat dan digunakan kembali untuk prediksi data baru tanpa perlu melatih ulang:

```python
import joblib # Jika model disimpan dengan joblib

# Untuk model Klasifikasi
model_knn = joblib.load('K-Nearest Neighbors_classification.h5')

# Untuk model Clustering
model_kmeans = joblib.load('model_clustering.h5')
