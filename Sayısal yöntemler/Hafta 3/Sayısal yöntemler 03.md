---
title: "Sayısal Yöntemler 03: Lineer Olmayan Denklemlerin Çözümü"
aliases:
  - Lineer Olmayan Denklemler MOC
  - Sayısal Yöntemler 03
  - Kök Bulma Yöntemleri
tags:
  - sayisal-analiz
  - sayisal-yontemler
  - lineer-olmayan-denklemler
  - kok-bulma
  - ikiye-bolme-yontemi
  - sabit-nokta-iterasyonu
  - bisection
  - fixed-point
  - sinav-notu
date: 2026-10-06
---

> 🧭 **Ders Akışı:** [[Hafta 2/Sayısal yöntemler 02|⬅️ Hafta 02: Bilimsel Gösterim & Kayan Nokta]] ➔ **[Hafta 03: Lineer Olmayan Denklemlerin Çözümü]**

---

# 🧭 Sayısal Yöntemler 03: Lineer Olmayan Denklemlerin Çözümü (Ders Akışı & MOC)

Mühendislik ve fen bilimlerinde karşımıza çıkan denklemlerin büyük bir kısmı (polinomlar, üstel fonksiyonlar, logaritmik veya trigonometrik terimler içeren yapılar) analitik olarak cebirsel yollarla doğrudan çözülemez ($f(x) = 0$). Bu durumlarda fonksiyonun $x$ eksenini kestiği kök noktalarını bulmak için **sayısal kök bulma yöntemleri (root-finding methods)** kullanılır.

Bu derste kök bulma yöntemlerinin iki temel sütunu işlenmiştir:
1. **İkiye Bölme Yöntemi (Bisection Method):** Kapalı (braketing) yöntemlerin temeli. En basit, en garantili fakat en yavaş yöntemdir.
2. **Sabit Nokta İterasyonu (Fixed-Point Iteration):** Açık (open) yöntemlerin temeli. $x = g(x)$ formuna dönüştürülerek çok daha hızlı çözüme ulaşılır; ancak yakınsama şartının ($|g'(x)| < 1$) sağlanması gerekir.

---

## 🗺️ Çalışma Flow'u (Adım Adım Öğrenme Akışı)

Sınava en verimli ve sistematik şekilde hazırlanabilmeniz için ders notları 3 temel çalışma modülüne ayrılmıştır:

```mermaid
flowchart LR
    A["🧭 00. Giriş & MOC\n(Genel Bakış)"] --> B["🎯 01. İkiye Bölme Yöntemi\n(Bolzano Teoremi & 4 Adım)"]
    B --> C["🔁 02. Sabit Nokta İterasyonu\n(x = g(x) & Türev Şartı)"]
    C --> D["🧮 03. Hesap Makinesi Rehberi\n(Ans Tuşu & Sınav Taktikleri)"]
```

---

## 📚 Modül Özetleri ve Çözülen Sorular

### 1. Adım: [[01 - İkiye Bölme Yöntemi (Bisection)]]
> *Aralığı daraltarak kökü sıkıştırma mantığı*

* **Bolzano (Ara Değer) Teoremi:** Sürekli bir fonksiyonda $f(a) \cdot f(b) < 0$ ise $[a, b]$ aralığında en az bir reel kök vardır.
* **Hocanın "Yarıla, Fonksiyona Bak, Aralığa Karar Ver" Mantığı:**
  * Her adımda orta nokta $x_r = \frac{a+b}{2}$ bulunur.
  * $f(a) \cdot f(x_r) < 0$ ise kök sol yarıda ($b = x_r$), $> 0$ ise kök sağ yarıdadır ($a = x_r$).
* **Sınav Tipi Çözümlü Sorular:**
  * **Örnek 1 ($f(x) = x^3 - 2x - 5 = 0$):** Kolay başlangıç aralığı tespiti ($f(2)=-1$, $f(3)=16 \implies [2, 3]$) ve 4 adımlı sınav çözümü ($x_{r4} = 2{,}0625$, gerçek kök $\approx 2{,}09455$).
  * **Örnek 2 ($f(x) = x^3 - 3 = 0$):** Pozitif kök için $[1, 2]$ aralığında 4 adım ($x_{r4} = 1{,}4375$, gerçek kök $\approx 1{,}44225$). Negatif kök analizi: Fonksiyon monoton artan olduğundan **negatif reel kökü yoktur**.
* **Hata Sınırı:** $n$. adım sonundaki maksimum hata $E_n \le \frac{b - a}{2^n}$.
* 📖 **Detaylı Not:** [[01 - İkiye Bölme Yöntemi (Bisection)|01 - İkiye Bölme Yöntemi (Bisection) Sayfasına Git ➡️]]

---

### 2. Adım: [[02 - Sabit Nokta İterasyonu]]
> *Fonksiyonu $x = g(x)$ formuna dönüştürerek iteratif yaklaşım*

* **Temel Prensip:** $f(x) = 0 \iff x = g(x)$ ve $x_{i+1} = g(x_i)$.
* **Mutlak Yakınsama Kriteri:** Kök civarında **$|g'(x)| < 1$** ise iterasyon KESİNLİKLE köke yakınsar! $|g'(x)| > 1$ ise iterasyon ıraksar (patlar).
* **🧠 Hocanın Taktiğinin Doğrulanması (İspat):**
  > *"Taktik: Denklemin en yüksek derecesi olan kuvvetini kullanarak yalnız bırakırsak en hızlı şekilde bulabiliriz."*
  * **Doğrulama:** $x^n$ yalnız bırakılıp $n$. kök alındığında ($x = [h(x)]^{1/n}$), türevde payda $n \cdot x^{n-1}$ çarpanı kazanır. Bu durum $|g'(x)|$ değerini aşırı küçültür ($|g'(x)| \ll 1$), böylece iterasyon ışık hızında köke kilitlenir! Lineer $x$ yalnız bırakılırsa türev patlar ($|g'(x)| > 1$).
* **Sınav Tipi Çözümlü Sorular:**
  * **Örnek 1 ($x^3 - 2x - 5 = 0$, $x_0 = 1$):** $x_{i+1} = \sqrt[3]{2x_i + 5}$ formülüyle $x_1$'den $x_9$'a kadar adım adım hesaplamalar ve virgülden sonra 5 basamağın sabitlenmesi ($x \approx 2{,}09455$).
  * **Örnek 2 ($x \cdot e^{0{,}5x} + 1{,}2x - 5 = 0$, $x_0 = 1$):** Doğru dönüşüm $x = \frac{5}{e^{0{,}5x} + 1{,}2}$ türevi $|g'(1{,}5050)| \approx 0{,}4807 < 1$ olduğu için salınımlı spiral şeklinde köke ($x \approx 1{,}5050$) yakınsar.
* 📖 **Detaylı Not:** [[02 - Sabit Nokta İterasyonu|02 - Sabit Nokta İterasyonu Sayfasına Git ➡️]]

---

### 3. Adım: [[03 - Bilimsel Hesap Makinesi ve Sınav Taktikleri]]
> *Sınavda 20 dakikalık işlem kalabalığını 1 dakikaya indiren teknikler*

* **`Ans` Tuşu Mucizesi:** Başlangıç değerini gir (`1 =`), fonksiyonu $x$ yerine `Ans` tuşu ile yaz (`√(2×Ans+5)`), ardından sadece `=` tuşuna bas! Her basışta bir sonraki iterasyon adımı ekrana gelir.
* **Euler Sayısı $e$ ve $e^x$ Yazımı:** `SHIFT` + `ln` $\implies e^{\blacksquare}$. `ALPHA` + `×10ˣ` $\implies e$ sabiti.
* **İkiye Bölmede `CALC` Modu:** Fonksiyonu `X^3 - 2X - 5` olarak bir kere yazıp `CALC` tuşuyla sadece $x$ değerlerini girerek fonksiyon sonuçlarını anında bulma.
* **`TABLE` Modu ile Başlangıç Aralığı:** İşaret değişimini denemeden 2 saniyede görme taktiği.
* 📖 **Detaylı Not:** [[03 - Bilimsel Hesap Makinesi ve Sınav Taktikleri|03 - Bilimsel Hesap Makinesi ve Sınav Taktikleri Sayfasına Git ➡️]]

---

## 📊 Hızlı Başvuru & Yöntem Karşılaştırma Matrisi

| Özellik | İkiye Bölme Yöntemi (Bisection) | Sabit Nokta İterasyonu (Fixed-Point) |
| :--- | :--- | :--- |
| **Girdi Gereksinimi** | İki sınır noktası: $[a, b]$ | Tek bir başlangıç noktası: $x_0$ |
| **Başlangıç Şartı** | $f(a) \cdot f(b) < 0$ (Zıt işaret) | Kök civarında bir $x_0$ tahmini |
| **Temel Formül** | $x_r = \dfrac{a + b}{2}$ | $x_{i+1} = g(x_i)$ |
| **Türev Hesabı** | Gerekmez | Zorunlu ($|g'(x)| < 1$ kontrolü için) |
| **Yakınsama Garantisi** | **%100 Kesin Garantili** | Şarta bağlı ($|g'(x)| < 1$ ise kesin) |
| **Yakınsama Hızı** | Çok Yavaş (Lineer, $r = 0{,}5$) | Doğru $g(x)$ ile Oldukça Hızlı |
| **Hata Sınırı** | $E_n \le \dfrac{b - a}{2^n}$ | $|e_{i+1}| \approx |g'(r)| \cdot |e_i|$ |
| **Sınav Beklentisi** | Tablo halinde 3 veya 4 adım | 5–8 adım veya basamaklar sabitlenene kadar |

---

## 💡 Sınav İçin Kritik Çıkarımlar & Altın Kurallar

1. **Kolay Sayı Seçimi:** İkiye bölme yönteminde aralık verilmemişse $x = 0, 1, 2, 3$ gibi küçük tam sayıları fonksiyona koyup işaretin eksi'den artı'ya geçtiği ardışık iki sayıyı seçin ($f(a) \cdot f(b) < 0$).
2. **Hocanın Sol/Sağ Güncelleme Kuralı:**
   * $f(a) \cdot f(x_r) < 0 \implies$ Kök $[a, x_r]$ arasındadır $\implies$ **Üst sınır güncellenir: $b = x_r$**.
   * $f(a) \cdot f(x_r) > 0 \implies$ Kök $[x_r, b]$ arasındadır $\implies$ **Alt sınır güncellenir: $a = x_r$**.
3. **Sabit Noktada En Yüksek Derece Kuralı:** Polinom denkleminde daima en yüksek dereceli $x^n$ terimini yalnız bırakıp kök alın. Bu hamle türevin paydasına $x^{n-1}$ atarak $|g'(x)| \ll 1$ olmasını sağlar ve ıraksamayı engeller.
4. **Sınavda Kağıda Türevi Yaz:** Sabit nokta sorusunda doğrudan sayısal iterasyona başlama. Önce seçtiğin $g(x)$ fonksiyonunun türevini alıp $|g'(x)| < 1$ olduğunu göstererek hocadan tam teorik puan al.
5. **Hesap Makinesinde `Ans` Kullan:** Sınavda vakit kaybetmemek ve işlem hatası yapmamak için iterasyonları mutlaka `Ans` hafızası ile çöz.

---

> 🚀 **Çalışmaya Başla:** [[01 - İkiye Bölme Yöntemi (Bisection)|1. Konu: 01 - İkiye Bölme Yöntemi (Bisection) ➡️]]