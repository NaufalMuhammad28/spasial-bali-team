# 🗺️ Analisis Spasial Gerai Indomaret & Alfamart di Bali

Proyek tugas kelompok Statistika Spasial yang menguji tren dan korelasi spasial dari **675 gerai minimarket** (378 Indomaret dan 297 Alfamart) di Pulau Bali menggunakan metodologi *Spatial Point Pattern Analysis*.

🌐 **Web Simulation Live:** [Buka Simulasi Interaktif](https://nama-akun-kelompok.github.io/nama-repo/) *(Ganti link ini dengan link GitHub Pages kelompok kalian)*

---

## 📌 Ringkasan Metode & Temuan Utama

1. **Momen Pertama (Spatial Trend):**
   * Persebaran gerai terbukti **menolak asumsi acak merata (CSR)** ($p < 0{,}05$).
   * Intensitas gerai ($\lambda(u)$) dipengaruhi secara signifikan oleh faktor lingkungan: jarak ke jalan utama/arteri, kepadatan penduduk, dan tutupan lahan terbangun. Area Denpasar–Badung menjadi pusat konsentrasi terbesar (puncak intensitas $\approx 4{,}81\text{ gerai/km}^2$).

2. **Momen Kedua (Spatial Correlation):**
   * Menggunakan fungsi $L(r) - r$ (*Centered L-function*) untuk memudahkan pembacaan penyimpangan pola pada skala jarak dekat.
   * Setelah pengaruh variabel lingkungan dinetralkan ($L_{\text{inhom}}$), gerai sesama merek masih menunjukkan sisa pengelompokan (*residual clustering*).
   * Interaksi antar-merek (Cross-$K$ / *Random Labelling*) menunjukkan indikasi kedekatan pada skala mikro ($r < 1\text{ km}$), namun bukti statistiknya tergolong lemah ($p = 0{,}07$).

---

## 📊 Cara Membaca Grafik di Simulasi Web

Web simulasi interaktif ini menyediakan pengujian visual berdasarkan fungsi $L(r) - r$:

* 📈 **Mengelompok (*Clustered*):** Kurva berada **di atas** pita abu-abu *envelope* ($> 0$). Rata-rata tetangga lebih banyak dibanding harapan acak.
* ➡️ **Acak (*CSR / Independent*):** Kurva berada **di dalam** pita abu-abu *envelope* ($\approx 0$). Pola sebaran tidak dapat dibedakan dari proses acak.
* 📉 **Teratur (*Regular / Inhibited*):** Kurva berada **di bawah** pita abu-abu *envelope* ($< 0$). Titik-titik cenderung saling menjauh.

> **Catatan Pembanding Hipotesis Nol ($H_0$):**
> - **Acak Merata (CSR):** Membandingkan data murni dengan sebaran acak homogen (menunjukkan efek kombinasi Tren + Korelasi).
> - **Acak Mengikuti Tren ($L_{\text{inhom}}$):** Membandingkan data setelah efek jalan & penduduk dinetralkan (menunjukkan murni Korelasi/Interaksi).

---

## 🛠️ Stack & Metodologi

* **Bahasa & Library Analisis:** R (`spatstat`), Python (`geopandas`, `shapely`)
* **Koreksi Tepi & Test:** Edge Correction (Translation), Global Envelope (Rank 5 dari 99 Simulasi, $\alpha = 0{,}05$)
* **Visualisasi Web:** HTML5 Canvas, Vanilla JavaScript, CSS Grid

---

## 📖 Referensi Utama

1. **Baddeley, A., Rubak, E., & Turner, R. (2015).** *Spatial Point Patterns: Methodology and Applications with R*. CRC Press.
2. **Besag, J. (1977).** *Contribution to the discussion of Dr Ripley's paper*. Journal of the Royal Statistical Society: Series B, 39, 193–195.
3. **Myllymäki, M., et al. (2017).** *Global envelope tests for spatial processes*. Journal of the Royal Statistical Society: Series B, 79(2), 381–404.
