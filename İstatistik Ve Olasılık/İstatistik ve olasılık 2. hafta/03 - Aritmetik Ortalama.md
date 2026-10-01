# 03 - Aritmetik Ortalama ($\bar{X}$)

← [[02 - Kapsamlı Frekans Tablosu Örneği (80 Öğrenci)|02 - 80 Kişilik Örnek Tablo]] | [[00 - 2. Hafta Çalışma Rehberi (MOC)|Rehbere Dön]] | Sonraki: [[04 - Medyan ve Çeyreklikler (Q1, Q2, Q3)|04 - Medyan ve Çeyreklikler →]]

---

## 1. Giriş: Merkezi Eğilim vs. Merkezi Dağılım

* **Merkezi Eğilim Ölçüleri:** Verilerin hangi merkezi değer etrafında toplandığını gösterir (Aritmetik Ortalama, Medyan, Mod, Geometrik Ortalama, Harmonik Ortalama). *(AI ekledi)*
* **Merkezi Dağılım (Yayılım) Ölçüleri:** Verilerin bu merkez etrafında ne kadar saçıldığını gösterir (Ranj, Varyans, Standart Sapma). *(AI ekledi)*

> [!NOTE]
> **Ders İçi Not:** Hoca bu istatistiksel analizlerin bilgisayar ortamında uygulanması için ilerleyen derslerde **R / RStudio** programını göstereceğini belirtti.

---

## 2. Aritmetik Ortalama Formülleri

Veri kümesindeki gözlemlerin toplamının toplam gözlem sayısına bölünmesiyle elde edilen en temel merkezi eğilim ölçüsüdür.

### A) Ham (Sınıflandırılmamış) Veriler İçin:
$$\bar{X} = \frac{\sum_{i=1}^n X_i}{n} = \frac{X_1 + X_2 + \dots + X_n}{n}$$

### B) Sınıflandırılmış Veriler (Frekans Tabloları) İçin:
> **Önemli Kural:** Sınıflandırılmış verilerde ham veriler tek tek bilinmediğinden, her sınıfı temsilen o sınıfın **orta noktası / sınıf değeri ($S_i$)** kullanılır. *(AI ekledi)*

$$\bar{X} = \frac{\sum_{i=1}^k (f_i \cdot S_i)}{n} = \frac{\sum_{i=1}^k (f_i \cdot S_i)}{\sum_{i=1}^k f_i}$$

* $k$: Sınıf sayısı
* $S_i$: $i$. sınıfın orta değeri ($\frac{A_s + U_s}{2}$)
* $f_i$: $i$. sınıfın frekansı
* $n$: Toplam gözlem sayısı ($n = \sum f_i$)
* *(Alternatif olarak göreli frekansla: $\bar{X} = \sum_{i=1}^k (P_i \cdot S_i)$)* *(AI ekledi)*

---

## 3. Dersteki Uygulama: Örnek 1.7 (Slayt / Tahta Örneği)

*(Örnek 1.4'te verilen sınıflandırılmış frekans tablosundaki verilerin aritmetik ortalaması)*

![[IMG_20260923_110649.jpg]]

| $i$ (Sınıf No) | Sınıf Aralığı | Sınıf Değeri ($S_i$) | Frekans ($f_i$) | $S_i \cdot f_i$ |
| :---: | :---: | :---: | :---: | :---: |
| **1** | $[0, 20)$ | 10 | 100 | $10 \cdot 100 = 1000$ |
| **2** | $[20, 40)$ | 30 | 350 | $30 \cdot 350 = 10500$ |
| **3** | $[40, 60)$ | 50 | 250 | $50 \cdot 250 = 12500$ |
| **4** | $[60, 80)$ | 70 | 200 | $70 \cdot 200 = 14000$ |
| **5** | $[80, 100]$ | 90 | 100 | $90 \cdot 100 = 9000$ |
| **Toplam** | — | — | **$n = 1000$** | **$\sum (S_i \cdot f_i) = 47000$** |

**Notların Aritmetik Ortalaması:**
$$\bar{X} = \frac{\sum_{i=1}^k (S_i \cdot f_i)}{n} = \frac{47000}{1000} = \mathbf{47}$$

> [!NOTE]
> **Tahtadaki Ek Not:** Görselin sağ tarafındaki beyaz tahtada sınıf sayısı kuralı ($\sqrt{n} \le k$) ve 1. sınıfın göreli frekansı ($P_1 = \frac{f_1}{n} = \frac{100}{1000} = 0.10$) formülü yer almaktadır.

---

## 🔗 İlgili Bağlantılar
* Bu tablonun Medyan hesabı için: [[04 - Medyan ve Çeyreklikler (Q1, Q2, Q3)]]
* Bu tablonun Mod hesabı ve çarpıklık karşılaştırması için: [[05 - Mod (Tepe Değer)]]
