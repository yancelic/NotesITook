# 06 - Geometrik ve Harmonik Ortalama

← [[05 - Mod (Tepe Değer)|05 - Mod (Tepe Değer)]] | [[00 - 2. Hafta Çalışma Rehberi (MOC)|Rehbere Dön]]

---

## 1. Geometrik Ortalama ($G$ veya $G.O.$)

Geometrik ortalama; oranlar, indeksler, faiz/enflasyon hesapları, büyüme hızları ve geometrik olarak artan seriler için kullanılan duyarlı bir merkezi eğilim ölçüsüdür. **Gözlemlerden en az biri sıfır veya negatif ise hesaplanamaz.** *(AI ekledi: tanım)*

### A) Ham (Sınıflandırılmamış) Veriler İçin:
Tüm verilerin çarpımının veri sayısı ($n$) derecesinden köküdür:
$$G = \sqrt[n]{X_1 \cdot X_2 \cdot \dots \cdot X_n} = \left( \prod_{i=1}^n X_i \right)^{1/n}$$

**Logaritma İle Hesaplama:**
Elle yüksek kök almak yerine logaritma özelliği kullanılır:
$$\log G = \frac{\sum_{i=1}^n \log X_i}{n} \implies G = 10^{\frac{\sum \log X_i}{n}}$$

### B) Sınıflandırılmış Veriler İçin:
Sınıf değerlerinin ($S_i$) frekans ($f_i$) kuvvetleri çarpılır:
$$G = \sqrt[n]{S_1^{f_1} \cdot S_2^{f_2} \cdot \dots \cdot S_k^{f_k}} = \left( \prod_{i=1}^k S_i^{f_i} \right)^{1/n}$$

**Logaritmik Formül:**
$$\log G = \frac{\sum_{i=1}^k (f_i \cdot \log S_i)}{n} \implies G = 10^{\log G}$$

---

## 2. Harmonik Ortalama ($H$ veya $H.O.$)

Gözlem değerlerinin çarpmaya göre terslerinin ($1/X$) aritmetik ortalamasının tersidir. Genellikle hız, birim zamanda yapılan iş, verimlilik ve maliyet hesaplamalarında tercih edilir. **Veriler içinde 0 bulunmamalıdır.** *(AI ekledi: tanım)*

### A) Ham (Sınıflandırılmamış) Veriler İçin:
$$H = \frac{n}{\sum_{i=1}^n \frac{1}{X_i}} = \frac{n}{\frac{1}{X_1} + \frac{1}{X_2} + \dots + \frac{1}{X_n}}$$

### B) Sınıflandırılmış Veriler İçin:
$$H = \frac{n}{\sum_{i=1}^k \frac{f_i}{S_i}} = \frac{\sum f_i}{\frac{f_1}{S_1} + \frac{f_2}{S_2} + \dots + \frac{f_k}{S_k}}$$

---

## 3. Uygulama: 80 Öğrencinin Kalp Atışı Verisinde $G$ ve $H$ Hesabı

[[02 - Kapsamlı Frekans Tablosu Örneği (80 Öğrenci)|80 Kişilik Nabız Verisi Tablosu]] değerleriyle:

| Sınıf No | Sınıf Aralığı | Sınıf Değeri ($S_i$) | Frekans ($f_i$) | $\log_{10}(S_i)$ | $f_i \cdot \log_{10}(S_i)$ | $f_i / S_i$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | 48 – 54 | 51.0 | 2 | 1.7076 | 3.4151 | 0.03922 |
| **2** | 55 – 61 | 58.0 | 4 | 1.7634 | 7.0537 | 0.06897 |
| **3** | 62 – 68 | 65.0 | 8 | 1.8129 | 14.5033 | 0.12308 |
| **4** | 69 – 75 | 72.0 | 18 | 1.8573 | 33.4320 | 0.25000 |
| **5** | 76 – 82 | 79.0 | 28 | 1.8976 | 53.1336 | 0.35443 |
| **6** | 83 – 89 | 86.0 | 12 | 1.9345 | 23.2140 | 0.13953 |
| **7** | 90 – 96 | 93.0 | 4 | 1.9685 | 7.8739 | 0.04301 |
| **8** | 97 – 103 | 100.0 | 3 | 2.0000 | 6.0000 | 0.03000 |
| **9** | 104 – 110 | 107.0 | 1 | 2.0294 | 2.0294 | 0.00935 |
| **Toplam** | — | — | **$n = 80$** | — | **$\sum = 150.6550$** | **$\sum = 1.05758$** |

### Geometrik Ortalama Sonucu:
* $\log G = \frac{150.6550}{80} \approx 1.8832$
* $$G = 10^{1.8832} \approx \mathbf{76.42\text{ bpm}}$$

### Harmonik Ortalama Sonucu:
* $$H = \frac{80}{1.05758} \approx \mathbf{75.64\text{ bpm}}$$

---

## 4. 🏆 Ortalamalar Arasındaki Altın Kural (Sınav Klasiği)

Pozitif sayılardan oluşan her veri setinde ortalamaların büyüklük sıralaması her zaman şöyledir: *(AI ekledi)*

$$H \le G \le \bar{X}$$
*(Harmonik Ortalama $\le$ Geometrik Ortalama $\le$ Aritmetik Ortalama)*

> **80 Kişilik Nabız Örneğimizdeki Doğrulama:**
> * $H = 75.64$
> * $G = 76.42$
> * $\bar{X} = 77.16$
> 
> $$75.64 \le 76.42 \le 77.16 \quad \checkmark$$

---

## 🔗 İlgili Bağlantılar
* Tüm konuların özet tablosu ve çalışma rehberi: [[00 - 2. Hafta Çalışma Rehberi (MOC)]]
* Aritmetik ortalama: [[03 - Aritmetik Ortalama]]
* Mod ve Medyan: [[04 - Medyan ve Çeyreklikler (Q1, Q2, Q3)]], [[05 - Mod (Tepe Değer)]]
