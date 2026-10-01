# 05 - Mod (Tepe Değer)

← [[04 - Medyan ve Çeyreklikler (Q1, Q2, Q3)|04 - Medyan ve Çeyreklikler]] | [[00 - 2. Hafta Çalışma Rehberi (MOC)|Rehbere Dön]] | Sonraki: [[06 - Geometrik ve Harmonik Ortalama|06 - Geometrik ve Harmonik Ortalama →]]

---

## 1. Mod (Tepe Değer) Nedir?

Bir veri setinde frekansı en yüksek olan, yani **en çok tekrar eden** gözlem değeridir ($M_o$ veya $\text{Mod}$).
* **Uç Değerlere Dayanıklılık:** Uç değerlerden hiç etkilenmez.
* **Kategorik Veriler:** Sayısal olmayan (nitel/kategorik) veriler için de hesaplanabilen **tek** merkezi eğilim ölçüsüdür (örn: en çok satılan tişört bedeni). *(AI ekledi: tanım)*

---

## 2. Mod Hesaplama Yöntemleri

### A) Ham (Sınıflandırılmamış) Veriler İçin:
Veri kümesinde en sık görülen değer doğrudan moddur:
* **Tek Modlu (Unimodal):** Tek bir en çok tekrar eden değer varsa.
  * *Örnek:* $3, 5, 5, 7, 8 \implies \text{Mod} = 5$
* **Çok Modlu (Bimodal / Multimodal):** En yüksek frekansa sahip birden fazla değer varsa.
  * *Örnek:* $2, 2, 4, 6, 6, 9 \implies \text{Modlar} = 2 \text{ ve } 6$
* **Modu Olmayan Dağılım:** Tüm değerlerin tekrarlanma sayısı aynıysa mod yoktur.
  * *Örnek:* $10, 20, 30, 40 \implies \text{Mod yoktur}$

---

### B) Sınıflandırılmış Veriler İçin (Mod Tahmini):
Frekans tablosunda en yüksek frekanslı sınıfa **Mod Sınıfı** denir ve komşu sınıfların frekans farkları kullanılarak enterpolasyon yapılır:

$$\text{Mod} = L + c \left( \frac{\Delta_1}{\Delta_1 + \Delta_2} \right)$$

#### Formüldeki Semboller:
* **Mod Sınıfı:** Frekansı ($f_i$) en büyük olan sınıftır.
* **$L$:** Mod sınıfının **alt sınırı** ($A_s$).
* **$c$:** Mod sınıfının **aralık genişliği**.
* **$\Delta_1$ (Delta 1):** Mod sınıfının frekansı ile **bir önceki sınıfın frekansı** arasındaki farktır:
  $$\Delta_1 = f_{\text{mod}} - f_{\text{önceki}}$$
* **$\Delta_2$ (Delta 2):** Mod sınıfının frekansı ile **bir sonraki sınıfın frekansı** arasındaki farktır:
  $$\Delta_2 = f_{\text{mod}} - f_{\text{sonraki}}$$

---

## 3. Uygulama: Örnek 1.7 Tablosu Üzerinde Mod Hesabı

[[03 - Aritmetik Ortalama|Örnek 1.7]]'deki 1000 kişilik not tablosunu inceleyelim:
* Sınıf Frekansları: $f_1 = 100, \quad f_2 = 350, \quad f_3 = 250, \quad f_4 = 200, \quad f_5 = 100$

1. **Mod Sınıfı:** En yüksek frekans $350$ olduğu için 2. sınıf olan **$[20, 40)$** aralığıdır.
2. **Değişkenler:**
   * $L = 20$ (Mod sınıfının alt sınırı)
   * $c = 20$ (Sınıf aralığı: $40 - 20 = 20$)
   * $\Delta_1 = f_2 - f_1 = 350 - 100 = 250$
   * $\Delta_2 = f_2 - f_3 = 350 - 250 = 100$
3. **Formüle Yerleştirme:**
   $$\text{Mod} = 20 + 20 \cdot \left( \frac{250}{250 + 100} \right) = 20 + 20 \cdot \left( \frac{250}{350} \right) = 20 + 14.29 \approx \mathbf{34.29}$$

---

## 4. 🎯 Vize Sorusu Klasiği: Dağılımın Çarpıklığı (Asimetrisi)

Örnek 1.7 için bulduğumuz üç temel merkezi eğilim ölçüsünü karşılaştıralım: *(AI ekledi)*
* **$\text{Mod} \approx 34.29$**
* **$\text{Medyan} = 44.00$**
* **$\text{Aritmetik Ortalama} (\bar{X}) = 47.00$**

```text
       Mod (34.29) < Medyan (44.00) < Ortalama (47.00)
       -------------------------------------------->
                   Sağa Çarpık (Pozitif Çarpık)
```

> [!TIP]
> **Karşılaştırma Kuralları:**
> 1. $\text{Mod} < \text{Medyan} < \bar{X} \implies$ **Sağa Çarpık (Pozitif Asimetrik):** Verilerin çoğunluğu sol tarafta (küçük değerlerde) toplanmış, sağ tarafta uzun bir kuyruk vardır.
> 2. $\bar{X} < \text{Medyan} < \text{Mod} \implies$ **Sola Çarpık (Negatif Asimetrik):** Verilerin çoğunluğu sağ tarafta (yüksek değerlerde) toplanmış, sol tarafta uzun bir kuyruk vardır.
> 3. $\bar{X} = \text{Medyan} = \text{Mod} \implies$ **Simetrik Dağılım (Normal Dağılım / Çan Eğrisi):** Veriler merkeze göre tam simetrik yayılmıştır.

---

## 🔗 İlgili Bağlantılar
* Aritmetik ortalama detayları: [[03 - Aritmetik Ortalama]]
* Medyan detayları: [[04 - Medyan ve Çeyreklikler (Q1, Q2, Q3)]]
* Geometrik ve Harmonik ortalamaya geçiş: [[06 - Geometrik ve Harmonik Ortalama]]
