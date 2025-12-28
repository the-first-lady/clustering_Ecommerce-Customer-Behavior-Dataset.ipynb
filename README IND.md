# Segmentasi Pelanggan & Analisis Churn pada E-Commerce  

## Ringkasan  
Proyek ini bertujuan untuk mengidentifikasi pola perilaku pelanggan e-commerce melalui metode clustering (unsupervised learning).  
Analisis dilakukan pada dataset berisi 50.000 pelanggan dengan 25 fitur demografi, engagement, dan transaksi. Fokus utama adalah memahami segmentasi pelanggan serta faktor yang memengaruhi churn (berhenti menggunakan layanan).  

---

## 1. Tujuan & Pertanyaan Riset  
**Tujuan:** Mengidentifikasi pola perilaku pelanggan e-commerce dan faktor yang mendorong churn.  

**Pertanyaan Riset:**  
- Apa karakteristik utama pelanggan yang churn vs tidak churn?  
- Bagaimana lifetime value, frekuensi login, dan cart abandonment memengaruhi loyalitas?  
- Segmen mana yang paling potensial untuk strategi retensi?  

---

## 2. Deskripsi Data  
**Sumber Data**  
- Dataset: *Ecommerce Customer Behavior Dataset*  
- Link: Kaggle – Ecommerce Customer Behavior Dataset  
- Jumlah Data: 50.000 pelanggan  
- Fitur: 25 kolom  
- Tipe Data: Campuran (numerik, kategorikal, objek)  
- Cakupan Geografis: Beberapa negara (USA, UK, Jerman, Kanada, India, Jepang, Prancis, Australia)  
- Periode Waktu: Mencakup perjalanan pelanggan dari pendaftaran hingga status terkini  

**Kualitas Data**  
- Terdapat missing values (NaN) pada beberapa kolom  
- Campuran nilai numerik kontinu (misalnya nilai pesanan, skor engagement)  
- Variabel kategorikal (Gender, Country, City, Payment methods)  
- Indikator biner (Churned: 0 = Aktif, 1 = Churned)  

---

## 3. Langkah Utama  
- **Data Cleaning:** Menangani missing values dengan imputasi (median, constant, KNN) serta outlier dengan metode capping (IQR).  
- **Feature Scaling:** Standardisasi fitur numerik agar kontribusi variabel setara dalam clustering.  
- **Exploratory Data Analysis (EDA):** Pairplot & heatmap untuk menemukan pola hubungan antar fitur (contoh: Lifetime Value berkorelasi dengan Total Purchases).  
- **Insight:** Setelah cleaning, semua fitur numerik bebas dari missing values dan outlier → siap untuk clustering.  

---

## 4. Metodologi & Algoritma  
- **Algoritma:** K-Means dengan K=4 (hasil Elbow Method).  
- **Alasan:** Cocok untuk dataset besar, interpretasi cluster mudah.  
- **Tambahan:** PCA digunakan untuk reduksi dimensi → visualisasi cluster dalam 2D.  

**Profil Cluster:**  
1. **High-Value Selective Shoppers** → Lifetime value tinggi, order besar, tetapi cart abandonment signifikan.  
2. **At-Risk / Low Engagement Shoppers** → Engagement rendah, lifetime value kecil, kandidat utama churn.  
3. **Highly Engaged Loyal Customers** → Login sering, sesi panjang, banyak pembelian, lifetime value tinggi.  
4. **Frequent but Budget Shoppers** → Sering belanja dengan nilai pesanan kecil, sensitif terhadap harga.  

---

## 5. Metrik Evaluasi  
- **Silhouette Score:** 0,1705 → menunjukkan adanya tumpang tindih antar cluster.  
- **Interpretasi:** Cluster cukup terpisah, namun dapat ditingkatkan dengan metode lain (DBSCAN, Hierarchical).  

---

## 6. Visualisasi & Dashboard  
- **Pairplot & Heatmap:** Menunjukkan korelasi kuat antara Lifetime Value, Total Purchases, dan Average Order Value.  
- **PCA Scatter Plot:** Memvisualisasikan 4 cluster dengan jelas.  
- **Boxplot:** Membandingkan distribusi fitur antara pelanggan churned vs non-churned.  

---

## 7. Keterbatasan & Tantangan  
- **Kualitas Data:** Outlier ekstrem (contoh: umur 200 tahun, cart abandonment >100%).  
- **Silhouette Score rendah:** Cluster belum sepenuhnya terpisah.  
- **Fitur kategorikal:** Belum diolah dengan encoding → berpotensi menambah insight.  

---

## 8. Pekerjaan Lanjutan / Rekomendasi  
- Mencoba algoritma lain (DBSCAN, Gaussian Mixture) untuk meningkatkan separasi cluster.  
- Menambahkan fitur kategorikal dengan One-Hot Encoding.  
- Membangun model prediksi churn berbasis supervised learning (misalnya Random Forest, XGBoost).  

---

## 9. Dampak Bisnis  
- **Cluster 2 (Highly Engaged Loyal Customers):** Dapat dijadikan ambassador brand.  
- **Cluster 1 (At-Risk Shoppers):** Target utama untuk program win-back.  
- **Cluster 0 (High-Value Selective Shoppers):** Fokus pada optimisasi checkout.  
- **Cluster 3 (Budget Shoppers):** Dorong upselling dengan bundling & diskon.  

---

## 10. Insight Strategis  
- **Retention Strategy:** Fokus pada cluster berisiko churn dengan promosi & re-engagement.  
- **Loyalty Programs:** Perkuat cluster loyal dengan benefit eksklusif.  
- **Upselling & Bundling:** Targetkan frequent budget shoppers dengan paket hemat.  
- **Conversion Optimization:** Kurangi cart abandonment pada high-value shoppers dengan insentif checkout.  

---

## 11. Tools & Environment  
**Python Libraries:**  
- `pandas` → data cleaning & preprocessing  
- `numpy` → perhitungan numerik  
- `matplotlib` & `seaborn` → visualisasi data (heatmap, boxplot, scatter plot)  
- `scikit-learn` → clustering (K-Means), PCA, evaluasi (Silhouette Score)  

**Environment:**  
- **Google Colab** → notebook interaktif untuk analisis  
- **Kaggle** → dataset hosting & eksplorasi awal  
