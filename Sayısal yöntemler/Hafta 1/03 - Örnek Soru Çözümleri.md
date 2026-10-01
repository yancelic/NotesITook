---
title: "03 - Örnek Soru Çözümleri"
tags:
  - sayisal-analiz
  - matematik
  - hata-analizi
  - ornek-sorular
date: 2026-09-23
---

> 🧭 **Ders Akışı:** [[02 - Hata Çeşitleri ve Hesaplama Formülleri|⬅️ 2. Hata Çeşitleri]] ➔ **[3. Soru Çözümleri]** ➔ [[Sayısal Yöntemler 01|🏠 Ana Dizin (MOC)]]

---

# 📝 03 - Örnek Soru Çözümleri

Bu dokümanda hata analizi, kesme/yuvarlama kuralları, anlamlı basamak kaybı ve Horner metodu ile ilgili ders notlarında yer alan tüm çözümlü örnekler adım adım ele alınmıştır.

---

## 📌 Soru 1: 5 Basamaklı Sistemde Kesme (Chopping) ve Dört İşlem

> **Soru:**  
> $$x = \frac{5}{7} \quad \text{ve} \quad y = \frac{1}{3}$$  
> sayıları **5 basamaklı** bir sistemde temsil edildiğinde;  
> **a)** $x + y$  
> **b)** $x - y$  
> **c)** $x \cdot y$  
> **d)** $x / y$  
> işlemlerinin sonuçlarını kesme (chopping) yöntemi uygulayarak bulunuz ve mutlak hatalarını ($\varepsilon_m$) değerlendiriniz.

### Sayıların 5 Basamaklı Temsili (Kesme Uygulanışı)
* $x = \frac{5}{7} = 0{,}714285714\dots \xrightarrow{\text{5 basamak kesme}} x \approx 0{,}71428$
* $y = \frac{1}{3} = 0{,}333333333\dots \xrightarrow{\text{5 basamak kesme}} y \approx 0{,}33333$

---

### İşlem Çözümleri ve Hata Analizi

#### a) Toplama ($x + y$)
* **Hesaplanan Değer:**  
  $$0{,}71428 + 0{,}33333 = 1{,}04761$$
* **Gerçek Değer:**  
  $$\frac{5}{7} + \frac{1}{3} = \frac{22}{21} \approx 1{,}04761904\dots$$
* **Mutlak Hata ($\varepsilon_m$):**  
  $$\varepsilon_m = |1{,}047619\dots - 1{,}04761| \approx 0{,}00001$$

#### b) Çıkarma ($x - y$)
* **Hesaplanan Değer:**  
  $$0{,}71428 - 0{,}33333 = 0{,}38095$$
* **Gerçek Değer:**  
  $$\frac{5}{7} - \frac{1}{3} = \frac{8}{21} \approx 0{,}38095238\dots$$
* **Mutlak Hata ($\varepsilon_m$):**  
  Hata mertebesi çok küçük olduğu için pratik hesaplamada **$\varepsilon_m \approx 0$** kabul edilir.

#### c) Çarpma ($x \cdot y$)
* **Hesaplanan Değer:**  
  $$0{,}71428 \times 0{,}33333 \approx 0{,}23809$$
* **Gerçek Değer:**  
  $$\frac{5}{7} \times \frac{1}{3} = \frac{5}{21} \approx 0{,}23809523\dots$$
* **Mutlak Hata ($\varepsilon_m$):**  
  Fark çok küçük düzeyde kaldığı için **$\varepsilon_m \approx 0$** alınır.

#### d) Bölme ($x / y$)
* **Hesaplanan Değer:**  
  $$\frac{0{,}71428}{0{,}33333} \approx 2{,}14286$$
* **Gerçek Değer:**  
  $$\frac{5/7}{1/3} = \frac{15}{7} \approx 2{,}14285714\dots$$
* **Mutlak Hata ($\varepsilon_m$):**  
  Son basamaktaki küçük fark ihmal edilerek **$\varepsilon_m \approx 0$** olarak değerlendirilir.

---

## 📌 Soru 2: Kesme ve Yuvarlama Hataları (Anlamlı Basamak Kaybı)

> **Soru:**  
> Birbirine çok yakın iki sayı:  
> $$p = 0{,}54617 \quad \text{ve} \quad q = 0{,}54601$$  
> olsun. 4 basamaklı bir sistemde $p - q = ?$ değerini hesaplayınız.

### 1. Gerçek Değer (Exact Value)
Sayıların tam farkı:
$$p - q = 0{,}54617 - 0{,}54601 = 0{,}00016 = 0{,}16 \times 10^{-3}$$

---

### A) Kesme (Chopping / Truncation) Yöntemi
4 basamaktan sonrası doğrudan atılır:
* $p = 0{,}5461 \times 10^0$
* $q = 0{,}5460 \times 10^0$

**Yaklaşık Fark:**
$$p - q = 0{,}5461 - 0{,}5460 = 0{,}0001 = 0{,}1 \times 10^{-3}$$

**Mutlak Hata ($\varepsilon_m$):**
$$\varepsilon_m = |\text{Gerçek} - \text{Yaklaşık}|$$
$$\varepsilon_m = |0{,}16 \times 10^{-3} - 0{,}1 \times 10^{-3}| = 0{,}06 \times 10^{-3} = 0{,}6 \times 10^{-4}$$

**Bağıl Hata ($\varepsilon_b$):**
$$\varepsilon_b = \frac{|\text{Gerçek} - \text{Yaklaşık}|}{|\text{Gerçek}|}$$
$$\varepsilon_b = \frac{0{,}6 \times 10^{-4}}{0{,}16 \times 10^{-3}} = \frac{0{,}06}{0{,}16} = 0{,}375 \implies \%37{,}5$$

---

### B) Yuvarlama (Rounding) Yöntemi
4 anlamlı basamağa göre yuvarlama yapılır (5. basamak $\ge 5$ ise bir üst basamağa tamamlanır):
* $p = 0{,}54617 \xrightarrow{\text{yuvarla}} 0{,}5462 \times 10^0$
* $q = 0{,}54601 \xrightarrow{\text{yuvarla}} 0{,}5460 \times 10^0$

**Yaklaşık Fark:**
$$p - q = 0{,}5462 - 0{,}5460 = 0{,}0002 = 0{,}2 \times 10^{-3}$$

**Mutlak Hata ($\varepsilon_m$):**
$$\varepsilon_m = |0{,}16 \times 10^{-3} - 0{,}2 \times 10^{-3}| = 0{,}04 \times 10^{-3} = 0{,}4 \times 10^{-4}$$

**Bağıl Hata ($\varepsilon_b$):**
$$\varepsilon_b = \frac{0{,}4 \times 10^{-4}}{0{,}16 \times 10^{-3}} = \frac{0{,}04}{0{,}16} = 0{,}25 \implies \%25$$

> [!WARNING] Çıkarım (Anlamlı Basamak Kaybı - Loss of Significance)
> Birbirine çok yakın iki sayı birbirinden çıkarıldığında, baştaki ortak basamaklar yok olur ve geriye çok az basamak kalır.  
> Bu durum mutlak hata küçük kalsa dahi bağıl hatanın dramatik şekilde büyümesine (burada **$\%37{,}5$** ve **$\%25$**) yol açar.

---

## 📌 Soru 3: 3 Basamaklı Aritmetikle Polinom Hesabı (Horner Metodu)

> **Soru:**  
> $$f(x) = x^3 - 6{,}1x^2 + 3{,}2x + 1{,}5$$  
> polinomunun $x = 4{,}71$ için değerini **3 basamaklı** bir aritmetik kullanarak hesaplayınız.

---

### Yöntem 1: Doğrudan (Standart) Hesaplama
*Her ara işlem sonucunda 3 anlamlı basamağa yuvarlama uygulanır.*

1. **Kuvvetlerin Hesabı:**
   * $x = 4{,}71$
   * $x^2 = (4{,}71)^2 = 22{,}1841 \xrightarrow{\text{yuvarla}} 22{,}2$
   * $x^3 = x^2 \times x = 22{,}2 \times 4{,}71 = 104{,}562 \xrightarrow{\text{yuvarla}} 105$

2. **Katsayı Çarpımları:**
   * $6{,}1 \times x^2 = 6{,}1 \times 22{,}2 = 135{,}42 \xrightarrow{\text{yuvarla}} 135$
   * $3{,}2 \times x = 3{,}2 \times 4{,}71 = 15{,}072 \xrightarrow{\text{yuvarla}} 15{,}1$

3. **İşlem Sırası (Soldan Sağa Toplama/Çıkarma):**
   * $x^3 - 6{,}1x^2 = 105 - 135 = -30{,}0$
   * $(-30{,}0) + 3{,}2x = -30{,}0 + 15{,}1 = -14{,}9$
   * $(-14{,}9) + 1{,}5 = -13{,}4$

$$\mathbf{f(4{,}71) \approx -13{,}4}$$

---

### Yöntem 2: Horner Metodu (İç İçe Çarpanlara Ayırma)
Polinom biçimi iç içe parantezlerle yeniden düzenlenir:
$$f(x) = ((x - 6{,}1)x + 3{,}2)x + 1{,}5$$

1. **1. Adım:**  
   $$4{,}71 - 6{,}1 = -1{,}39$$
2. **2. Adım:**  
   $$-1{,}39 \times 4{,}71 = -6{,}5469 \xrightarrow{\text{yuvarla}} -6{,}55$$
3. **3. Adım:**  
   $$-6{,}55 + 3{,}2 = -3{,}35$$
4. **4. Adım:**  
   $$-3{,}35 \times 4{,}71 = -15{,}7785 \xrightarrow{\text{yuvarla}} -15{,}8$$
5. **5. Adım:**  
   $$-15{,}8 + 1{,}5 = -14{,}3$$

$$\mathbf{f(4{,}71) \approx -14{,}3}$$

---

### 📊 Karşılaştırma & Hata Değerlendirmesi

* **Gerçek Analitik Değer:**
  $$f(4{,}71) = (4{,}71)^3 - 6{,}1(4{,}71)^2 + 3{,}2(4{,}71) + 1{,}5 = -14{,}263899$$

| Yöntem | Hesaplanan Değer | Mutlak Hata ($\varepsilon_m$) |
| :--- | :---: | :---: |
| **Doğrudan Yöntem** | $-13{,}4$ | $|-14{,}263899 - (-13{,}4)| \approx \mathbf{0{,}86}$ |
| **Horner Metodu** | $-14{,}3$ | $|-14{,}263899 - (-14{,}3)| \approx \mathbf{0{,}04}$ |

> [!TIP] Neden Horner Metodu?
> Horner metodu hem işlem sayısını (çarpma maliyetini) azaltarak hesaplama hızını artırır hem de ara basamaklardaki yuvarlama hatalarının birikmesini engelleyerek gerçek değere çok daha yakın (hata $\approx 0{,}04$) sonuç verir.

---

> 🧭 **Gezinme:**  
> ⬅️ [[02 - Hata Çeşitleri ve Hesaplama Formülleri|Önceki Konu: 02 - Hata Çeşitleri]] | [[Sayısal Yöntemler 01|🏠 Ana Dizin (MOC)]]
