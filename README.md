# 🗺️ Analisis Spasial Gerai Indomaret & Alfamart di Pulau Bali

Proyek riset kelompok Statistika Spasial yang menguji tren dan korelasi spasial dari **675 gerai minimarket** (378 Indomaret dan 297 Alfamart) di daratan Pulau Bali ($5.380\text{ km}^2$) menggunakan metodologi *Spatial Point Pattern Analysis*.

🌐 **Simulasi Interaktif Web:** [Buka Web Simulation App](https://naufalmuhammad28.github.io/spasial-bali-team/)

---

## 📌 Ringkasan Metode & Temuan Utama

1. **Spatial Trend (Momen Pertama — $\rho(z)$):**
   * Persebaran gerai terbukti **menolak hipotesis acak merata (CSR)** ($p < 0{,}05$).
   * Intensitas gerai ($\hat{\lambda}(u)$) dipengaruhi secara signifikan oleh variabel lingkungan: jarak ke jalan utama/arteri, kepadatan penduduk, dan tutupan lahan terbangun. Area Denpasar–Badung menjadi pusat konsentrasi terbesar.

2. **Spatial Correlation (Momen Kedua — $L_{\text{inhom}}$):**
   * Menggunakan fungsi $L(r) - r$ (*Centered L-function*) untuk mendatarkan garis acuan $H_0$ di angka nol ($0$), sehingga penyimpangan pada jarak mikro ($r < 1\text{ km}$) lebih stabil dan mudah dibaca.
   * Setelah pengaruh variabel lingkungan dinetralkan ($L_{\text{inhom}}$ dengan bobot $1/\hat{\lambda}$), gerai sesama merek masih menunjukkan sisa pengelompokan (*residual clustering*).
   * Interaksi antar-merek (*Cross-K* / *Random Labelling*) menunjukkan indikasi kedekatan pada radius pendek ($0{,}1 \text{–} 1{,}2\text{ km}$), namun bukti statistiknya tergolong lemah ($p = 0{,}07$).

---

## 📊 Panduan Membaca Grafik di Simulasi Web

Aplikasi simulasi web menyediakan pengujian visual berbasis fungsi $L(r) - r$ terhadap pita *envelope*:

* 📈 **Mengelompok (*Clustered*):** Kurva berada **di atas** pita abu-abu *envelope* ($> 0$). Rata-rata tetangga lebih banyak daripada harapan acak.
* ➡️ **Acak (*CSR / Independent*):** Kurva berada **di dalam** pita abu-abu *envelope* ($\approx 0$). Pola sebaran tidak dapat dibedakan dari proses acak.
* 📉 **Teratur (*Regular / Inhibited*):** Kurva berada **di bawah** pita abu-abu *envelope* ($< 0$). Titik-titik gerai cenderung saling menjaga jarak.

> **Modus Pembanding Hipotesis Nol ($H_0$):**
> - **Acak Merata (CSR):** Membandingkan data murni dengan sebaran acak homogen (mengukur kombinasi Tren + Korelasi).
> - **Acak Mengikuti Tren ($L_{\text{inhom}}$):** Membandingkan data setelah efek jalan & penduduk dinetralkan (mengukur murni residual Korelasi/Interaksi).

---

## 🛠️ Spesifikasi Metodologi & Tools

* **Pengolahan Data & Pemodelan:** Python (`geopandas`, `shapely`), R (`spatstat`)
* **Pengujian Statistik:** Koreksi Tepi Translasi (*Translation Edge Correction*), Global Envelope Test Rank 5 dari 99 Simulasi ($\alpha = 0{,}05$, Seed 2026)
* **Frontend Interaktif:** HTML5 Canvas, Vanilla JavaScript, CSS Grid (Tanpa Dependensi External)

---

## 📖 Referensi Akademis Utama

1. **Baddeley, A., Rubak, E., & Turner, R. (2015).** *Spatial Point Patterns: Methodology and Applications with R*. Boca Raton: CRC Press.
2. **Besag, J. (1977).** *Contribution to the discussion of Dr Ripley's paper*. Journal of the Royal Statistical Society: Series B, 39, 193–195.
3. **Myllymäki, M., Mrkvička, T., Grabarnik, P., Seijo, H., & Hahn, U. (2017).** *Global envelope tests for spatial processes*. Journal of the Royal Statistical Society: Series B, 79(2), 381–404.
