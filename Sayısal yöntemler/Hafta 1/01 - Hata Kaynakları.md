---
title: "01 - Hata Kaynakları"
tags:
  - sayisal-analiz
  - sayisal-yontemler
  - hata-analizi
  - hata-kaynaklari
date: 2026-09-23
---

> 🧭 **Ders Akışı:** [[Sayısal Yöntemler 01|🏠 Ana Dizin (MOC)]] ➔ **[1. Hata Kaynakları]** ➔ [[02 - Hata Çeşitleri ve Hesaplama Formülleri|2. Hata Çeşitleri ➡️]]

---

# 🔍 01 - Hata Kaynakları

Sayısal yöntemlerle yaklaşık çözümler üretilirken yalnızca hesaplamanın yapıldığı yöntemden ya da bilgisayar donanımından değil, farklı aşamalardan kaynaklanan çeşitli hatalar da ortaya çıkar.

Hata analizi yöntemlerine ve hata miktarlarını belirlemeye geçmeden önce **hata kavramının ve hatanın ortaya çıktığı 5 temel kaynağın** anlaşılması gerekir.

---

## 1. Kullanılan Verideki Hatalar (Ölçme Hatası)

* **Tanım:** Sayısal çözümlemelerde girdi olarak kullanılan veriler genellikle çeşitli deney, gözlem ve fiziksel ölçümlerle elde edilir.
* **Kaynak:** Ölçümün yapıldığı ortam koşulları, ölçüm aletlerinin hassasiyeti veya ölçüm sisteminden kaynaklanan kusurlar verinin hatalı / belirsiz olmasına yol açar.
* **Örnek:** Düşen bir cismin hareketini matematiksel olarak modellemek için cisim birçok kez yüksekten serbest bırakılır. Belli bir süre sonra yapılan yükseklik ve hız ölçümlerinde ortam rüzgârı, kronometre hassasiyeti gibi nedenlerle ölçümlerde belirsizlikler ve sapmalar olduğu görülür.

---

## 2. Yuvarlama Hataları

* **Tanım:** Bazı rasyonel sayılar ve irrasyonel sayıların tamamı ($\pi$, $e$, $\sqrt{3}$ gibi) ondalık sayı sisteminde sonsuz sayıda basamakla ifade edilmek zorundadır.
* **Bilgisayarda Gösterim:** 64 bitlik bir bilgisayar sisteminde dahi bir reel sayının virgülden sonra ancak belirli bir sayıda basamağı (sonlu sayıda bit ile) saklanabilir. Temsil edilemeyen geriye kalan basamaklar sayıdan atılır ya da yuvarlanır. Bu durum **yuvarlama hatasına** neden olur.
* **Hata Yayılması ve Birikmesi:** Elektronik hesaplayıcılar ve bilgisayarlarda sayısal çözümleme yapılırken ardışık olarak binlerce hesaplama adımı yürütülür. Hesaplama şemasının başında veya ara adımlarında meydana gelen küçük bir yuvarlama hatası, kendisinden sonraki hesaplamalara da sirayet eder ve yayılır. Bu tür hatalar birikerek kartopu etkisiyle büyüyebilir ve nihai sonucu önemli ölçüde saptırabilir.

---

## 3. Kesme Hataları

* **Tanım:** Matematiksel fonksiyon yaklaşımlarında kullanılan sonsuz seri açılımlarında (örneğin Taylor veya Maclaurin serileri) sonsuz terimli bir matematiksel ifadenin yalnızca sonlu bir kısmı bilgisayarda hesaplanabilir.
* **Kesme Mantığı:** Sonsuz serinin hesaplamaya dahil edilmeyen, kesilip atılan kuyruk kısmı **kesme hatası** olarak adlandırılır.
* **Örnek:** $e^x$ fonksiyonunun seri açılımı:
  $$e^x = 1 + \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots + \frac{x^n}{n!}$$
  $e^{0.5}$ değerini elde etmek için sonsuz sayıda terimi toplamak mümkün olmadığından, seri belirli bir terimde (örneğin 3. veya 4. terimde) kesilir ve kalan kısım kesme hatasını oluşturur.

> [!WARNING] Sınav Notu (Basamaktan Kesme)
> Sınavda örneğin $2{,}3575454$ sayısına *"2. basamaktan kesme (chopping) uygula"* denirse, yuvarlama kuralına bakılmaksızın virgülden sonraki 2. basamakta işlem kesilir ve doğrudan **$2{,}35$** yazılarak bırakılır.

---

## 4. İnsan Kaynaklı Hatalar

* **Tanım:** Sayısal problemi modelleyen veya çözen kişinin formülleri yanlış kurgulaması, eksik türetmesi ya da matematiksel denklemleri bilgisayar ortamına kod olarak aktarırken yaptığı yazım ve mantık hatalarıdır.
* **Örnek:** Coulomb Kanunu ifadesi:
  $$F = \frac{k \cdot q^2}{r^2}$$
  olması gerekirken, formülü bilgisayara aktarırken paydadaki kare ifadesini unutup $r$ olarak yazarsak ($F = k \cdot q^2 / r$), bu durum doğrudan insan kaynaklı bir hatadır.

---

## 5. Bilgisayar Kaynaklı Hatalar

* **Tanım:** Bilgisayarlar ve dijital hesaplayıcılar elektrik akımı ve yarı iletken elektronik devrelerle çalışan fiziksel cihazlardır.
* **Kaynak:** Elektrik şebekesindeki ani voltaj dalgalanmaları, statik elektriklenme, aşırı ısınma ya da bilgisayar donanımının elektronik aksamında meydana gelen anlık arızalar hesaplamalarda bit hatalarına (bit-flip) ve beklenmeyen sayısal sapmalara yol açabilir.

---

## 📌 Bölüm Özeti ve İlerleme

| Hata Kaynağı | Temel Sebep | Tipik Örnek |
| :--- | :--- | :--- |
| **1. Veri / Ölçme** | Deney ortamı ve ölçüm aleti kusurları | Yüksekten atılan cismin ölçüm belirsizliği |
| **2. Yuvarlama** | Sayıların sonlu basamakla temsil edilmesi | $\pi, e, \sqrt{3}$ gibi sayıların basamak kırpılması |
| **3. Kesme** | Sonsuz serilerin sonlu terimde durdurulması | $e^x$ serisinde terim kesintisi |
| **4. İnsan Kaynaklı** | Formül ve modelin koda aktarımındaki yanlışlar | $r^2$ yerine $r$ yazılması |
| **5. Bilgisayar Kaynaklı** | Donanım, voltaj ve elektronik aksam sorunları | Anlık elektriksel dalgalanma hataları |

---

> 🧭 **Gezinme:**  
> ⬅️ [[Sayısal Yöntemler 01|Ana Dizin (MOC)]] | [[02 - Hata Çeşitleri ve Hesaplama Formülleri|Sonraki Konu: 02 - Hata Çeşitleri ve Hesaplama Formülleri ➡️]]
