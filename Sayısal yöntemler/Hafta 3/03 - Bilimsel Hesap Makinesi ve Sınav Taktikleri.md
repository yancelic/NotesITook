---
title: "03 - Bilimsel Hesap Makinesi ve Sınav Taktikleri"
tags:
  - sayisal-analiz
  - sayisal-yontemler
  - hesap-makinesi
  - casio-fx991
  - sinav-taktikleri
  - bisection
  - fixed-point
date: 2026-10-06
---

> 🧭 **Ders Akışı:** [[01 - İkiye Bölme Yöntemi (Bisection)|1. İkiye Bölme Yöntemi]] ➔ [[02 - Sabit Nokta İterasyonu|2. Sabit Nokta İterasyonu]] ➔ **[3. Hesap Makinesi & Sınav Taktikleri]** ➔ [[Sayısal yöntemler 03|🏠 Ana Dizin (MOC)]]

---

# 🧮 03 - Bilimsel Hesap Makinesi ve Sınav Taktikleri

Sayısal Yöntemler sınavlarında öğrencilerin en çok zorlandığı ve en fazla puan kaybettiği yer yöntemin teorisi değil; **bilimsel hesap makinesini hızlı ve hatasız kullanamamaktır.** 

Bu rehber, Casio fx-991EX (ClassWiz), fx-82ES, fx-570 ve benzeri tüm bilimsel hesap makinelerinde sınavda 20 dakikalık işlem kalabalığını **1-2 dakikaya indiren profesyonel teknikleri** sunar.

---

## 1. Sabit Nokta İterasyonunu 10 Saniyede Çözme (`Ans` Tuşu Taktiği)

Sabit nokta iterasyonunda $x_1, x_2, x_3, \dots, x_8$ değerlerini her seferinde fonksiyonu baştan yazarak hesaplamak hem dakikalarca vakit kaybettirir hem de basamak hatası yapma riskini tavan yaptırır. 

Bunun yerine makinenin **`Ans` (Sonuç Hafızası)** tuşu kullanılarak işlem zinciri kurulur.

### 🚀 Adım Adım `Ans` Yöntemi:

```text
Adım 1: Başlangıç değerini gir (örn: 1) ve [ = ] tuşuna bas. (Ans = 1 oldu)
Adım 2: İterasyon formülünü ekrana yazarken x gördüğün her yere [ Ans ] tuşunu koy.
Adım 3: Sadece ve sadece art arda [ = ] tuşuna bas!
```

---

### 📝 Örnek 1 Uygulaması: $x_{i+1} = \sqrt[3]{2x_i + 5}$ ($x_0 = 1$)

1. Ekrana `1` yaz ve **`=`** tuşuna bas.
2. Ekrana küpkök formülünü yaz:
   * Küpkök simgesi için: **`SHIFT`** + **`√`** (karekök) tuşuna bas.
   * Parantezin içine: `2 × Ans + 5` yaz.
   * *(Ekran görüntüsü: $\sqrt[3]{2\text{Ans} + 5}$)*
3. Şimdi sadece **`=`** tuşuna bas:
   * **1. basış:** Ekranda $\mathbf{1{,}912931}$ görünür $\implies (x_1)$
   * **2. basış:** Ekranda $\mathbf{2{,}066581}$ görünür $\implies (x_2)$
   * **3. basış:** Ekranda $\mathbf{2{,}090292}$ görünür $\implies (x_3)$
   * **4. basış:** Ekranda $\mathbf{2{,}093904}$ görünür $\implies (x_4)$
   * **5. basış:** Ekranda $\mathbf{2{,}094453}$ görünür $\implies (x_5)$
   * **6. basış:** Ekranda $\mathbf{2{,}094537}$ görünür $\implies (x_6)$
   * **7. basış:** Ekranda $\mathbf{2{,}094549}$ görünür $\implies (x_7)$
   * **8. basış:** Ekranda $\mathbf{2{,}094551}$ görünür $\implies (x_8)$

> [!TIP] Süper Sınav Avantajı
> Her `=` tuşuna bastığınızda ekranda çıkan sayıyı sınav kağıdındaki tablonuza doğrudan yazabilirsiniz! 8 adımlı bir soruyu çözmek yalnızca **15 saniyenizi** alır.

---

## 2. Hesap Makinesinde Euler Sayısı $e$ ve $e^x$ Nasıl Yapılır?

Ders notundaki $x \cdot e^{0{,}5x} + 1{,}2x - 5 = 0$ gibi sorularda $e$ sayısını girmek hayati önem taşır.

### A) $e^x$ (Üstel Fonksiyon) Tuşu:
* **Nasıl Basılır:** **`SHIFT`** tuşuna bas, ardından **`ln`** tuşuna bas.
* **Ekranda Ne Görünür:** $e^{\blacksquare}$ (kutucuk) veya `e^(`.
* **Önemli Kural:** Kutucuğun içine üssü yaz. Eğer eski model makine ise parantezi açıp kapatmayı unutma: `e^(0.5 × Ans)`.

### B) Tek Başına $e$ Sabiti ($2{,}71828...$):
* **Nasıl Basılır:** **`ALPHA`** tuşuna bas, ardından en alttaki **`×10ˣ`** tuşuna bas (üzerinde kırmızı küçük $e$ yazar). Veya bazı modellerde **`ALPHA`** + **`ln`**.

---

### 📝 Örnek 2 Uygulaması: $x_{i+1} = \frac{5}{e^{0{,}5 x_i} + 1{,}2}$ ($x_0 = 1$)

1. Ekrana `1` yazıp **`=`** tuşuna bas.
2. Kesir çizgisi aç (**`■/□`** tuşu):
   * Pay kısmına: `5` yaz.
   * Payda kısmına: **`SHIFT`** + **`ln`** basarak $e^{\blacksquare}$ çağır, üs kısmına `0.5 × Ans` yaz, sağ okla kutudan çıkıp `+ 1.2` yaz.
   * *(Ekran görüntüsü: $\frac{5}{e^{0{,}5\text{Ans}} + 1{,}2}$)*
3. **`=`** tuşuna bas:
   * **1. basış:** $\mathbf{1{,}755173}$ $(x_1)$
   * **2. basış:** $\mathbf{1{,}386928}$ $(x_2)$
   * **3. basış:** $\mathbf{1{,}562190}$ $(x_3)$
   * **4. basış:** $\mathbf{1{,}477601}$ $(x_4)$
   * **5. basış:** $\mathbf{1{,}518177}$ $(x_5)$
   * **6. basış:** $\mathbf{1{,}498654}$ $(x_6)$
   * **7. basış:** $\mathbf{1{,}508034}$ $(x_7)$
   * **...** $\implies \mathbf{1{,}5050}$ değerine kolayca oturur.

---

## 3. İkiye Bölme Yönteminde Hızlandırma Taktikleri

İkiye bölme yönteminde her adımda $f(a)$, $f(b)$ ve $f(x_r)$ değerlerini hesaplamak gerekir. $x^3 - 2x - 5$ fonksiyonuna $2{,}0625$ gibi sayıları elle tek tek girmek felakettir.

### Taktik 1: `CALC` Fonksiyon Hesaplama Tuşu (En Pratik Yol)

1. Ekrana doğrudan fonksiyonu değişkenli olarak yaz:
   * $X$ harfi için: **`ALPHA`** + **`)`** tuşuna bas.
   * Ekrana yaz: `X^3 - 2X - 5`
2. Sol üstteki **`CALC`** tuşuna bas:
   * Makine sorar: `X?`
   * `2` yaz ve **`=`** bas $\implies \mathbf{-1}$ (Bu $f(a)$ değeridir).
3. Tekrar **`CALC`** tuşuna bas:
   * `3` yaz ve **`=`** bas $\implies \mathbf{16}$ (Bu $f(b)$ değeridir).
4. Tekrar **`CALC`** tuşuna bas:
   * `2.5` yaz ve **`=`** bas $\implies \mathbf{5{,}625}$ (Bu $f(x_{r1})$ değeridir).
5. Tekrar **`CALC`** tuşuna bas:
   * `2.25` yaz ve **`=`** bas $\implies \mathbf{1{,}890625}$ ($f(x_{r2})$).

> [!NOTE] Neden CALC?
> Fonksiyonu bir kere yazdıktan sonra sadece `CALC` tuşuna basıp yeni $x_r$ değerini girmek yeterlidir; tüm terimleri yeniden yazma zahmetinden kurtarır!

---

### Taktik 2: Başlangıç Aralığını `TABLE` Moduyla 2 Saniyede Bulma

Hoca *"kolay iki sayı seçin"* dediğinde hangi sayıların zıt işaret verdiğini deneme yanılma yapmadan görmek için:

1. **`MENU`** (veya `MODE`) $\to$ **`TABLE`** (Tablo modu) seç.
2. $f(x) =$ alanına `x^3 - 2x - 5` yaz ve `=` bas.
3. Aralığı gir:
   * **Start:** `0`
   * **End:** `5`
   * **Step:** `1`
4. Ekrana bir tablo gelir:
   * $x=1 \implies f(x) = -6$
   * $x=2 \implies f(x) = -1$
   * $x=3 \implies f(x) = 16$
5. Tabloda $f(x)$'in **eksi (-) değerden artı (+) değere geçtiği satıra** bak: $x=2$ ile $x=3$ arası! Başlangıç aralığın anında hazır: **$[2, 3]$**.

---

## 4. İki Yöntemin Sınav Karşılaştırma Matrisi

| Kriter | İkiye Bölme Yöntemi (Bisection) | Sabit Nokta İterasyonu (Fixed-Point) |
| :--- | :--- | :--- |
| **Yöntem Türü** | Kapalı (Braketing / İki noktalı) | Açık (Open / Tek noktalı) |
| **Başlangıç İhtiyacı** | Zıt işaretli 2 nokta: $[a, b]$, $f(a) \cdot f(b) < 0$ | 1 adet başlangıç tahmini: $x_0$ |
| **Türev İhtiyacı** | Yok (Sadece fonksiyon değerleri) | Var ($|g'(x)| < 1$ yakınsama testi için) |
| **Yakınsama Garantisi** | **%100 Garantili** (Asla ıraksamaz) | **Şarta Bağlı** ($|g'(x)| < 1$ ise garantili) |
| **Yakınsama Hızı** | Çok Yavaş (Lineer, her adımda aralık yarıya iner) | Hızlı (Doğru $g(x)$ seçilirse hızla sonuca ulaşır) |
| **Sınavda İstenen** | Genellikle ilk 3-4 adım | 5-8 adım veya sabit basamak elde edilene kadar |

---

## 5. Sınavda Puan Kaybettiren 5 Kritik Hata

> [!WARNING] 🚨 Bu Hataları Asla Yapma!
> 1. **Radyan / Derece Modu:** Eğer fonksiyonda trigonometrik ifade ($\sin x, \cos x$) varsa, makinenin kesinlikle **R (Radyan)** modunda olduğundan emin ol! Sayısal analizde kalkülüs türevleri radyan cinsindendir.
> 2. **Negatif Sayı Parantezi:** Makinede negatif bir sayının karesini alırken parantezsiz `-2^2` yazarsan `-4` bulur! Parantezli `(-2)^2` yazmalısın.
> 3. **Virgülden Sonraki Basamak Sayısı:** Sınavda hocanın kuralı yoksa virgülden sonra **en az 4 veya 6 basamak** taşı. Erken yuvarlama yapmak son adımdaki kök tahminini bozar.
> 4. **Türev Kontrolünü Unutmak:** Sabit nokta iterasyonu sorulduğunda doğrudan iterasyona başlama. Önce $g'(x)$ türevini alıp $|g'(x)| < 1$ olduğunu göster; hoca bu adıma ayrı puan verir.
> 5. **İşaret Testinde Yanlış Sınırı Güncellemek:** İkiye bölme yönteminde $f(a) \cdot f(x_r) > 0$ çıktığında $a = x_r$ yapılması gerektiğini; $< 0$ çıktığında ise $b = x_r$ yapılması gerektiğini karıştırma!

---

> 🧭 **Gezinme:**  
> ⬅️ [[02 - Sabit Nokta İterasyonu|Önceki Konu: 02 - Sabit Nokta İterasyonu]] | [[Sayısal yöntemler 03|🏠 Hafta 03: Ana Dizin (MOC)]]
