# 🏦 Home Credit Default Prediction using Machine Learning

Project-Based Internship — **Rakamin Academy x Home Credit Indonesia**  
Author: **Muhammad Tri Wahyudi**

---

## 📌 Deskripsi

Proyek ini dibuat sebagai bagian dari **Project-Based Internship Rakamin x Home Credit Indonesia**.  
Tujuan utama project ini adalah membangun model machine learning untuk memprediksi **risiko gagal bayar (default)** pada peminjam.  
Dengan model ini, perusahaan dapat melakukan **credit scoring lebih efektif, mengurangi potensi kerugian**, serta meningkatkan proses pengambilan keputusan.

---

## 📊 Dataset

Dataset terdiri dari beberapa tabel terpisah yang saling berelasi:

| File | Deskripsi |
|---|---|
| `application_train.csv` | Dataset utama dengan label default |
| `application_test.csv` | Dataset untuk submission prediksi |
| `bureau.csv` | Riwayat kredit nasabah pada lembaga eksternal |
| `previous_application.csv` | Riwayat pengajuan pinjaman sebelumnya |
| `installments_payments.csv` | Riwayat pembayaran cicilan |
| `credit_card_balance.csv` | Aktivitas saldo kartu kredit |
| `POS_CASH_balance.csv` | Riwayat POS/CASH balance |

📌 Train data: **307.511 rows × 122 features**  
📌 Data imbalanced → default hanya sekitar **8%**

---

## 🔎 Tahapan Proyek

1. **Data Understanding**
2. **EDA — Exploratory Data Analysis**
3. **Feature Engineering (penggabungan multi-table)**
4. **Preprocessing (missing value, encoding, imputasi)**
5. **Modeling**
   - Logistic Regression
   - Random Forest
   - Gradient Boosting
   - **LightGBM (Hyperparameter Tuning — Model Akhir)**
6. **Evaluation**
7. **Submission CSV Output**

---

## 🤖 Model Performance

| Model | AUC | Recall Default |
|---|---|---|
| Logistic Regression | 0.64 | 0.06 |
| Random Forest | 0.74 | 0.55 |
| Gradient Boosting | 0.76 | 0.80 |
| **LightGBM Tuned (Final)** | **0.773** | 0.03 |

📌 **LightGBM menghasilkan AUC tertinggi**  
📌 **Gradient Boosting unggul dalam recall untuk mendeteksi default**

---

## 📈 Visualisasi

- Confusion Matrix
- <img width="453" height="380" alt="Screenshot 2025-12-29 095414" src="https://github.com/user-attachments/assets/f9c6809e-9ffd-4af2-8ec2-152a4cf1d57f" />

- ROC Curve
- <img width="488" height="394" alt="Screenshot 2025-12-29 095512" src="https://github.com/user-attachments/assets/0026b16c-094f-40e6-8eb1-0c2cb4d5a94e" />

- Feature Importance  
<img width="878" height="850" alt="image" src="https://github.com/user-attachments/assets/c9710db9-3a29-4647-888a-b717b825a0c4" />


---

## 📝 Business Insight

- Nasabah dengan **riwayat keterlambatan pembayaran tinggi** berpotensi default
- **Income rendah + unsecured loan** memiliki risiko default lebih tinggi
- **Riwayat previous loan refused** berkorelasi dengan kegagalan kredit
- Feature penting terlihat pada *feature importance model*

| Feature Penting                      | Insight                                                                 |
| ------------------------------------ | ----------------------------------------------------------------------- |
| **EXT_SOURCE_1/2/3**                 | Skor eksternal paling berpengaruh → skor rendah = risiko default tinggi |
| **AMT_CREDIT**                       | Nominal pinjaman besar meningkatkan risiko gagal bayar                  |
| **DAYS_BIRTH**                       | Nasabah lebih muda → tingkat default lebih tinggi                       |
| **CC_BALANCE_MEAN**                  | Saldo kartu kredit tinggi → potensi cashflow ketat                      |
| **AMT_ANNUITY & PAYMENT_RATIO_MEAN** | Besaran cicilan & rasio pembayaran berpengaruh pada kemampuan bayar     |
| **PREV/REFUSED RATIO**               | Riwayat penolakan kredit sebelumnya menunjukkan potensi risiko          |

📌 Model mampu membantu identifikasi calon peminjam berisiko sejak awal.

---

## 🚀 Rekomendasi Implementasi

- Gunakan **LightGBM sebagai baseline credit scoring**
- Lakukan **threshold tuning** untuk meningkatkan recall default
- Use case bisnis:
  - Auto flag high-risk borrower
  - Manual verification untuk borderline cases
  - Pemberian limit lebih rendah untuk nasabah berisiko tinggi
- Next improvement:
  - SMOTE balancing
  - Feature selection
  - XGBoost optimization
  - Threshold tuning strategy

---
