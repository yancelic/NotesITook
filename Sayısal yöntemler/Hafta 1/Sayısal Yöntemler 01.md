---
title: "Sayısal Yöntemler 01: Hata Analizi"
aliases:
  - Hata Analizi MOC
  - Sayısal Yöntemler 01
tags:
  - sayisal-analiz
  - sayisal-yontemler
  - hata-analizi
date: 2026-09-23
---

# 🧭 Sayısal Yöntemler 01: Hata Analizi (Ders Akışı & MOC)

Günümüzde özellikle mühendislik ve fen bilimlerinde karşılaşılan pek çok matematiksel problemin kesin (analitik) çözümü yapılamamaktadır. Bu nedenle problemlerin sayısal yöntemlerle yaklaşık çözümlerinin üretilmesine ihtiyaç duyulur.

Sayısal çözümlerde kullanılan yöntemlerin doğasından, verilerden ve bilgisayar sisteminin fiziksel/yapısal kısıtlarından ötürü hatalar kaçınılmazdır. Bu hataların kabul edilebilir sınırlar içinde olup olmadığını belirlemek ve doğruluğu denetlemek amacıyla **Hata Analizi** yapılır.

---

## 🗺️ Çalışma Flow'u (Adım Adım Öğrenme Akışı)

Konuyu mantıksal bir sıra ve en verimli şekilde çalışabilmeniz için notlar 3 temel modüle ayrılmıştır. Sırayla takip ediniz:

```mermaid
flowchart LR
    A["🧭 00. Giriş & MOC\n(Genel Bakış)"] --> B["🔍 01. Hata Kaynakları\n(Hatanın Kökeni)"]
    B --> C["📐 02. Hata Çeşitleri\n(Formüller & Karşılaştırma)"]
    C --> D["📝 03. Soru Çözümleri\n(Alıştırmalar & Horner Metodu)"]
```

### 1. Adım: [[01 - Hata Kaynakları]]
> *Hata nereden kaynaklanır?*
* **Ölçme Hataları:** Deney ortamı ve ölçüm belirsizlikleri (cismin yüksekten atılması).
* **Yuvarlama Hataları:** Sonsuz basamaklı sayıların ($\pi, e, \sqrt{3}$) 64-bit temsili, basamak kırpılması ve hataların ardışık işlemlerde birikerek yayılması.
* **Kesme Hataları:** Sonsuz serilerin ($e^x$ açılımı) sonlu terimde kesilmesi ve sınavda basamak kesme kuralı.
* **İnsan Kaynaklı Hatalar:** Modellerin ve denklemlerin koda hatalı aktarılması ($F=kq^2/r^2$ yerine $r$ yazılması).
* **Bilgisayar Kaynaklı Hatalar:** Elektrik dalgalanmaları ve donanım aksamı arızaları.

---

### 2. Adım: [[02 - Hata Çeşitleri ve Hesaplama Formülleri]]
> *Hata nasıl ölçülür ve matematiksel olarak ifade edilir?*
* **Mutlak Hata ($\varepsilon_m$):** Gerçek analitik değer bilindiğinde hesaplanan doğrudan fark ($\varepsilon_m = |Y_g - Y_y|$).
* **Bağıl Hata ($\varepsilon_b$):** Hatanın gerçek büyüklüğe oranı ($\varepsilon_b = \frac{|Y_g - Y_y|}{Y_g}$).
  * *Füze Menzili vs. Araç Hızı Örneği:* Mutlak hata $1$ birim iken bağıl hatanın neden daha objektif karar sunduğunun analizi.
* **Yaklaşım Hatası ($\varepsilon_y$):** Gerçek analitik çözüm bilinmediğinde, iteratif adımların birbirine oranlanması ($\varepsilon_y = \frac{|Y_{\text{yeni}} - Y_{\text{eski}}|}{|Y_{\text{yeni}}|}$).
  * $e^x$ Taylor serisi yaklaşım hatası incelemesi.

---

### 3. Adım: [[03 - Örnek Soru Çözümleri]]
> *Öğrenilen kurallar problem çözümlerinde nasıl uygulanır?*
* **Soru 1:** 5 Basamaklı sistemde kesme (chopping) ile dört işlem ($x=5/7, y=1/3$) ve mutlak hata değerlendirmesi.
* **Soru 2:** Birbirine çok yakın sayıların farkında **Anlamlı Basamak Kaybı** (Kesme vs. Yuvarlama farkı).
* **Soru 3:** 3 basamaklı aritmetikle polinom hesabı ($x=4{,}71$) — Doğrudan yöntem ile **Horner Metodu** karşılaştırması ve hata minimizasyonu.

---

## 📊 Hızlı Başvuru & Karşılaştırma Matrisi

| Hata Türü | Sembol | Formül | Yüzde Formülü | Ne Zaman Kullanılır? |
| :--- | :---: | :---: | :---: | :--- |
| **Mutlak Hata** | $\varepsilon_m$ | $\varepsilon_m = \|Y_g - Y_y\|$ | — | Gerçek değer ($Y_g$) bilindiğinde mutlak sapmayı bulmak için |
| **Bağıl Hata** | $\varepsilon_b$ | $\varepsilon_b = \dfrac{\|Y_g - Y_y\|}{Y_g}$ | $\% \varepsilon_b = \varepsilon_b \times 100$ | Hatanın oransal büyüklüğünü ve hassasiyetini kıyaslamak için |
| **Yaklaşım Hatası** | $\varepsilon_y$ | $\varepsilon_y = \dfrac{\|Y_{\text{yeni}} - Y_{\text{eski}}\|}{\|Y_{\text{yeni}}\|}$ | $\% \varepsilon_y = \varepsilon_y \times 100$ | Gerçek değer bilinmediğinde ardışık iterasyonlarda |

---

## 💡 Önemli Çıkarımlar & Sınav Tüyoları

1. **Kesme (Chopping) Kuralı:** İstenen basamaktan sonrası yuvarlama kurallarına bakılmaksızın doğrudan atılır.
2. **Anlamlı Basamak Kaybı:** Birbirine çok yakın iki sayı çıkarıldığında ortak basamaklar yok olur ve bağıl hata çok büyük oranda artar.
3. **Horner Metodu Üstünlüğü:** Polinom hesaplarında Horner metodu hem çarpma sayısını azaltır hem de ara yuvarlama hatalarının birikmesini engelleyerek daha doğru sonuca ulaştırır.

---

> 🚀 **Çalışmaya Başla:** [[01 - Hata Kaynakları|1. Konu: 01 - Hata Kaynakları ➡️]]
