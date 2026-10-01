# 02 - Kapsamlı Frekans Tablosu Örneği (80 Öğrenci)

← [[01 - Frekans Tablosu Oluşturma Adımları|01 - Tablo Oluşturma Adımları]] | [[00 - 2. Hafta Çalışma Rehberi (MOC)|Rehbere Dön]] | Sonraki: [[03 - Aritmetik Ortalama|03 - Aritmetik Ortalama →]]

---

## 📌 Problem ve Ham Veri Seti

80 öğrencinin istirahat halinde dakikadaki kalp atış sayıları (nabız) verilmiştir:

> `86, 98, 81, 83, 96, 89, 81, 60, 67, 102*, 83, 69, 77, 67, 77, 81, 68, 76, 72, 80, 85, 79, 58, 81, 99, 93, 73, 75, 68, 70, 75, 105, 80, 79, 76, 77, 72, 84, 81, 55, 89, 70, 81, 48, 71, 67, 81, 80, 73, 77, 88, 61, 81, 73, 73, 81, 63, 83, 82, 87, 82, 83, 82, 71, 65, 62, 82, 77, 69, 69, 53, 74, 77, 93, 93, 74, 78, 80, 85, 73`
> 
> *\*(Not: Veri setinde sehven yazılan 1022 değeri fizyolojik tutarlılık ve toplam 80 veri olması gereği 102 kabul edilmiştir).*

---

## 7 Adımlık Tablo Çıkarma Süreci

### Ön Hazırlık: Dağılım Genişliği ($R$)
* **En küçük değer ($X_{\min}$):** $48$
* **En büyük değer ($X_{\max}$):** $105$
* **Dağılım Genişliği ($R$):**
  $$R = X_{\max} - X_{\min} = 105 - 48 = 57$$

### 1. Adım: Kaç Sınıf Olacağına Karar Verilir ($k$)
* $\sqrt{n} \le k \implies \sqrt{80} \approx 8.94 \le k \implies \mathbf{k = 9}$ sınıf seçildi.

### 2. Adım: Sınıf Aralık Uzunluğu Belirlenir ($c$)
* $c \approx \frac{R}{k} = \frac{57}{9} \approx 6.33$
* Verilerin dışarıda kalmaması için bir üst tam sayıya yuvarlanır: $\mathbf{c = 7}$.

### 3. Adım: Sınıf Sınırları Belirlenir ($A_s$ ve $U_s$)
* İlk sınıfın alt sınırı en küçük değer olan $48$ seçilir. Ardışık alt sınırlar $c=7$ eklenerek ilerler:
  * 1. Sınıf: $48 – 54$ *(48, 49, 50, 51, 52, 53, 54: 7 tam sayı)*
  * 2. Sınıf: $55 – 61$
  * 3. Sınıf: $62 – 68$
  * 4. Sınıf: $69 – 75$
  * 5. Sınıf: $76 – 82$
  * 6. Sınıf: $83 – 89$
  * 7. Sınıf: $90 – 96$
  * 8. Sınıf: $97 – 103$
  * 9. Sınıf: $104 – 110$ *(En büyük değer olan 105 bu sınıfa girer).*

### 4. Adım: Sınıf Değerleri ($S_i$) Hesaplanır
* Her sınıfın orta noktası: $S_i = \frac{A_s + U_s}{2}$
  * 1. Sınıf: $(48 + 54) / 2 = 51.0$
  * 2. Sınıf: $(55 + 61) / 2 = 58.0$
  * *(Her adımda $+7$ eklenerek gider).*

### 5. Adım: Frekans Değerleri ($f_i$) Belirlenir
* Ham verilerden aralıklara düşen kişi sayıları:
  * $48 – 54 \implies 2$
  * $55 – 61 \implies 4$
  * $62 – 68 \implies 8$
  * $69 – 75 \implies 18$
  * $76 – 82 \implies 28$
  * $83 – 89 \implies 12$
  * $90 – 96 \implies 4$
  * $97 – 103 \implies 3$
  * $104 – 110 \implies 1$
  * **Toplam Frekans:** $\sum f_i = 80$ ($n$'e eşittir).

### 6. Adım: Göreli Frekanslar ($P_i$) Hesaplanır
* $P_i = \frac{f_i}{n} = \frac{f_i}{80}$
  * Örneğin 1. sınıf: $2 / 80 = 0.0250$ (%2.50)
  * Toplam: $\sum P_i = 1.0000$ (%100).

### 7. Adım: "-den Az" ve "-den Çok" Frekanslar Bulunur
* **"-den Az" (Üst sınırdan küçük veya eşit olanlar - yukarıdan aşağıya toplanır):**
  $2, 6, 14, 32, 60, 72, 76, 79, 80$
* **"-den Çok" (Alt sınırdan büyük veya eşit olanlar - aşağıdan yukarıya toplanır veya toplamdan çıkarılır):**
  $80, 78, 74, 66, 48, 20, 8, 4, 1$

---

## 📊 Nihai Frekans Tablosu (80 Öğrenci)

| Sınıf No ($i$) | Sınıf Aralığı [$A_s - U_s$] | Sınıf Değeri ($S_i$) | Frekans ($f_i$) | Göreli Frekans ($P_i$) | "-den Az" Frekans | "-den Çok" Frekans |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | 48 – 54 | 51.0 | 2 | 0.0250 (%2.50) | 2 | 80 |
| **2** | 55 – 61 | 58.0 | 4 | 0.0500 (%5.00) | 6 | 78 |
| **3** | 62 – 68 | 65.0 | 8 | 0.1000 (%10.00) | 14 | 74 |
| **4** | 69 – 75 | 72.0 | 18 | 0.2250 (%22.50) | 32 | 66 |
| **5** | 76 – 82 | 79.0 | 28 | 0.3500 (%35.00) | 60 | 48 |
| **6** | 83 – 89 | 86.0 | 12 | 0.1500 (%15.00) | 72 | 20 |
| **7** | 90 – 96 | 93.0 | 4 | 0.0500 (%5.00) | 76 | 8 |
| **8** | 97 – 103 | 100.0 | 3 | 0.0375 (%3.75) | 79 | 4 |
| **9** | 104 – 110 | 107.0 | 1 | 0.0125 (%1.25) | 80 | 1 |
| **Toplam** | — | — | **80** | **1.0000 (%100)** | — | — |

---

## 🔗 İlgili Bağlantılar
* Bu tablonun Geometrik ve Harmonik ortalamalarının hesabı için: [[06 - Geometrik ve Harmonik Ortalama]]
* Merkezi eğilim ölçülerine geçiş: [[03 - Aritmetik Ortalama]]
