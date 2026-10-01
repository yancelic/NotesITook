---
title: "02 - Hata Çeşitleri ve Hesaplama Formülleri"
tags:
  - sayisal-analiz
  - sayisal-yontemler
  - hata-analizi
  - hata-cesitleri
date: 2026-09-23
---

> 🧭 **Ders Akışı:** [[01 - Hata Kaynakları|⬅️ 1. Hata Kaynakları]] ➔ **[2. Hata Çeşitleri]** ➔ [[03 - Örnek Soru Çözümleri|3. Soru Çözümleri ➡️]]

---

# 📐 02 - Hata Çeşitleri ve Hesaplama Formülleri

Sayısal yöntemler ile çözülen problemlerin kesin veya analitik çözümleri var ise sayısal çözümde oluşan hata miktarını bulmak zor değildir. Ancak karşılaşılan birçok mühendislik probleminin analitik çözümleri ve kesin sonuçları bilinmemektedir.

Sayısal yöntemler ile yapılan çözümlemelerde hata kaçınılmaz olarak oluşacaktır. Temel amaç, bu hatanın **kabul edilebilir sınırlar içinde olup olmadığını** ölçmektir:

1. **Gerçek Değer Biliniyorsa:** Gerçek değerden faydalanılarak **Mutlak Hata** ve **Bağıl Hata** hesaplanır.
2. **Gerçek Değer Bilinmiyorsa:** Adım adım ilerleyen iterasyon yöntemlerinden faydalanılarak ardışık değerler üzerinden **Yaklaşım Hatası** hesaplanır.

---

## 1. Mutlak Hata ($\varepsilon_m$)

* **Tanım:** Analitik olarak bilinen ve doğru değer olarak kabul edilen bir sonuç ile sayısal yöntemlerle elde edilmiş yaklaşık sonuç arasındaki farkın mutlak değeridir.
* **Matematiksel İfade:**
  $$\varepsilon_m = |Y_g - Y_y|$$
* **Değişkenler:**
  * $\varepsilon_m$: Mutlak Hata
  * $Y_g$: Gerçek Değer (Exact Value)
  * $Y_y$: Yaklaşık Değer (Approximate Value)

---

## 2. Bağıl Hata ($\varepsilon_b$)

* **Tanım:** Yapılan hatanın gerçek değere oranını belirten ve gerçek sonuca ne derece yaklaşıldığını oransal olarak gösteren hata çeşididir.
* **Önemi:** *Çoğu mühendislik probleminde bağıl hata, mutlak hatadan çok daha fazla anlam ifade eder.* Çünkü hatanın mutlak büyüklüğü, ölçülen büyüklüğün ölçeğine göre yanıltıcı olabilir.
* **Matematiksel İfadeler:**
  $$\varepsilon_b = \frac{|Y_g - Y_y|}{Y_g} = \frac{\varepsilon_m}{Y_g}$$
* **Yüzde Bağıl Hata ($\% \varepsilon_b$):**
  $$\% \varepsilon_b = \frac{|Y_g - Y_y|}{Y_g} \times 100 = \varepsilon_b \times 100$$

---

### 📊 Karşılaştırmalı Örnek: Mutlak Hata vs. Bağıl Hata

Bağıl hatanın neden mutlak hatadan daha objektif bir ölçüt olduğunu gösteren iki örnek:

#### Örnek A: Bir Füzenin Menzil Hesabı
* **Gerçek Değer ($Y_g$):** $5000 \text{ km}$
* **Hesaplanan Değer ($Y_y$):** $4999 \text{ km}$
* **Mutlak Hata ($\varepsilon_m$):**
  $$\varepsilon_m = |5000 - 4999| = 1 \text{ km}$$
* **Bağıl Hata ($\varepsilon_b$):**
  $$\varepsilon_b = \frac{5000 - 4999}{5000} = \frac{1}{5000} = 0{,}0002 \implies \%0{,}02$$

#### Örnek B: Bir Aracın Maksimum Hız Hesabı
* **Gerçek Değer ($Y_g$):** $50 \text{ km/h}$
* **Hesaplanan Değer ($Y_y$):** $49 \text{ km/h}$
* **Mutlak Hata ($\varepsilon_m$):**
  $$\varepsilon_m = |50 - 49| = 1 \text{ km/h}$$
* **Bağıl Hata ($\varepsilon_b$):**
  $$\varepsilon_b = \frac{50 - 49}{50} = \frac{1}{50} = 0{,}02 \implies \%2$$

> [!TIP] Objektif Değerlendirme Çıkarımı
> Her iki hesaplamada da mutlak hata aynı büyüklüktedir ($\varepsilon_m = 1 \text{ birim}$).  
> Fakat yüzde bağıl hatalara bakıldığında:
> * Füze menzilindeki sapma: **$\%0{,}02$**
> * Araç hızındaki sapma: **$\%2$**
> 
> İkinci problemdeki hata oransal olarak **100 kat** daha büyüktür. Bu sebeple bağıl hata dikkate alındığında sonuçlar çok daha adil ve objektif biçimde değerlendirilir.

---

## 3. Yaklaşım Hatası ($\varepsilon_y$)

* **Kullanım Nedeni:** Hem mutlak hata hem de bağıl hata formüllerinde gerçek değerin ($Y_g$) bilinmesi zorunludur. Ancak gerçek değerin bilinmediği pek çok problemde bu formüller uygulanamaz. Bu durumlarda **yaklaşım hatası** kullanılır.
* **Hesaplama Yolu:** Çözüm adım adım iteratif (tekrarlamalı) bir şekilde aranır. Bir önceki iterasyonda elde edilen değer ($Y_{\text{eski}}$) ile mevcut iterasyonda elde edilen yeni değer ($Y_{\text{yeni}}$) karşılaştırılarak hata miktarı oransal olarak tahmin edilir.
* **Matematiksel İfadeler:**
  $$\varepsilon_y = \frac{|Y_{\text{yeni}} - Y_{\text{eski}}|}{|Y_{\text{yeni}}|}$$
* **Yüzde Yaklaşım Hatası ($\% \varepsilon_y$):**
  $$\% \varepsilon_y = \frac{|Y_{\text{yeni}} - Y_{\text{eski}}|}{|Y_{\text{yeni}}|} \times 100$$

---

### 🔍 Örnek: $e^x$ Seri Yaklaşımı ile Hata İncelemesi

$e^x$ fonksiyonunun sonsuz seri açılımı aşağıdaki toplam serisi biçimindedir:
$$e^x = 1 + \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots + \frac{x^n}{n!}$$

$x = 0{,}5$ noktası için gerçek analitik değer referansı:
$$e^{0{,}5} \approx 1{,}64872$$
kabul edilsin. Seri açılımından faydalanıp belirli sayıda terim alarak hatayı inceleyelim:

* **1. Terim Alındığında ($n = 0$):**
  $$Y_y = 1$$
* **Mutlak Bağıl Hata Yüzdesi:**
  $$\% \varepsilon_b = \frac{|e^{0{,}5} - 1|}{|e^{0{,}5}|} \times 100 = \frac{|1{,}64872 - 1|}{1{,}64872} \times 100 \approx \%39{,}3$$

> [!NOTE] Derste Alınan Not & İterasyon Tablosu
> *(Derste hocanın tahtaya yazdığı devam tablosu: İterasyon adımlarına göre yeni eklenen terimlerle birlikte bağıl hata ve yaklaşım hatalarının adım adım küçülmesini gösteren tablo görseli buraya gelecektir.)*

---

## 📊 Matematiksel Formül ve Hata Karşılaştırma Tablosu

| Hata Çeşidi | Sembol | Matematiksel Formül | Yüzde İfadesi | Gerekli Bilgi / Kullanım Durumu |
| :--- | :---: | :---: | :---: | :--- |
| **Mutlak Hata** | $\varepsilon_m$ | $\varepsilon_m = \|Y_g - Y_y\|$ | — | Gerçek analitik değer ($Y_g$) bilinmelidir. |
| **Bağıl Hata** | $\varepsilon_b$ | $\varepsilon_b = \dfrac{\|Y_g - Y_y\|}{Y_g}$ | $\% \varepsilon_b = \varepsilon_b \times 100$ | Gerçek değer bilinmelidir; oransal kıyas sağlar. |
| **Yaklaşım Hatası** | $\varepsilon_y$ | $\varepsilon_y = \dfrac{\|Y_{\text{yeni}} - Y_{\text{eski}}\|}{\|Y_{\text{yeni}}\|}$ | $\% \varepsilon_y = \varepsilon_y \times 100$ | Gerçek değer **bilinmediğinde** ardışık iterasyonlarda kullanılır. |

---

> 🧭 **Gezinme:**  
> ⬅️ [[01 - Hata Kaynakları|Önceki: 01 - Hata Kaynakları]] | [[Sayısal Yöntemler 01|Ana Dizin (MOC)]] | [[03 - Örnek Soru Çözümleri|Sonraki Konu: 03 - Örnek Soru Çözümleri ➡️]]
