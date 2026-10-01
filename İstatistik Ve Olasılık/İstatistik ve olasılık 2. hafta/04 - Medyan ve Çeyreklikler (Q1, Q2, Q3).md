# 04 - Medyan ve Çeyreklikler ($Q_1, Q_2, Q_3$)

← [[03 - Aritmetik Ortalama|03 - Aritmetik Ortalama]] | [[00 - 2. Hafta Çalışma Rehberi (MOC)|Rehbere Dön]] | Sonraki: [[05 - Mod (Tepe Değer)|05 - Mod (Tepe Değer) →]]

---

## 1. Medyan / Ortanca ($\tilde{X}$ veya $M$)

Küçükten büyüğe sıralanmış bir veri setini tam ortadan iki eşit parçaya bölen (%50'si altında, %50'si üstünde kalan) merkezi eğilim ölçüsüdür. **Aşırı uç değerlerden etkilenmez.** *(AI ekledi: tanım)*

### A) Ham (Sınıflandırılmamış) Veriler İçin:
* **$n$ tek sayı ise:** Tam ortadaki gözlemdir:
  $$\text{Sıra} = \frac{n + 1}{2} \implies \text{Medyan} = X_{\left(\frac{n+1}{2}\right)}$$
* **$n$ çift sayı ise:** Ortadaki iki değerin aritmetik ortalamasıdır:
  $$\text{Medyan} = \frac{X_{\left(\frac{n}{2}\right)} + X_{\left(\frac{n}{2} + 1\right)}}{2}$$

### B) Sınıflandırılmış Veriler İçin (Medyan Tahmini):
Frekans tablosunda ham veriler tek tek bilinmediğinden, **doğrusal enterpolasyon** formülü kullanılır:
$$\text{Medyan} = L + \frac{c}{f} \left( \frac{n}{2} - d \right)$$

* **$n$:** Toplam veri sayısı ($\sum f_i$).
* **$\frac{n}{2}$:** Medyanın sıra numarası.
* **Medyan Sınıfı:** "-den az" frekansın $\frac{n}{2}$ değerine ilk ulaştığı / geçtiği sınıf.
* **$L$:** Medyan sınıfının **alt sınırı**.
* **$c$:** Medyan sınıfının **aralık genişliği**.
* **$f$:** Medyan sınıfının **kendi frekansı**.
* **$d$:** Medyan sınıfından **önceki sınıfların toplam frekansı**.

---

## 2. Çeyreklikler / Kartiller ($Q_1, Q_2, Q_3$)

Küçükten büyüğe sıralanmış bir veri kümesini **4 eşit parçaya (%25'lik dilimlere)** bölen 3 adet sınır değeridir:

```text
[En Küçük Değer] --- %25 --- [ Q1 ] --- %25 --- [ Q2 = Medyan ] --- %25 --- [ Q3 ] --- %25 --- [En Büyük Değer]
```

> [!IMPORTANT]
> **Hocanın "Sınavda Sorabilirim" Dediği Kritik Eşdeğerlikler:** *(AI ekledi)*
> 1. **1. Çeyreklik ($Q_1$ - Alt Çeyreklik):**
>    * **Öğrendiğimiz hangi kavramla aynı?** $\implies$ **25. Yüzdelik (Persentil - $P_{25}$)** ile birebir aynıdır ($Q_1 \equiv P_{25}$).
>    * **Tablodaki karşılığı:** Tablodaki **"-den az" birikimli frekansın** verilerin **%25'ine ($\frac{n}{4}$)** ulaştığı değerdir.
> 2. **2. Çeyreklik ($Q_2$ - Ortanca):**
>    * **Öğrendiğimiz hangi kavramla aynı?** $\implies$ **Doğrudan MEDYAN'dır!** ($Q_2 \equiv \text{Medyan} \equiv P_{50}$).
>    * **Sınav Tuzağı:** Sınavda *"2. çeyrekliğini bulunuz"* denirse doğrudan Medyan formülü uygulanır.
> 3. **3. Çeyreklik ($Q_3$ - Üst Çeyreklik):**
>    * **Öğrendiğimiz hangi kavramla aynı?** $\implies$ **75. Yüzdelik (Persentil - $P_{75}$)** ile birebir aynıdır ($Q_3 \equiv P_{75}$).
>    * **Tablodaki karşılığı:** Tablodaki **"-den az" birikimli frekansın** verilerin **%75'ine ($\frac{3n}{4}$)** ulaştığı değerdir.

### Sınıflandırılmış Verilerde Formüller
Hepsi aynı ana kalıptan türemiştir: $\text{Değer} = L + \frac{c}{f} (\text{Hedef Sıra} - d)$

$$Q_1 = L + \frac{c}{f} \left( \frac{n}{4} - d \right)$$
$$Q_2 = L + \frac{c}{f} \left( \frac{2n}{4} - d \right) = \text{Medyan}$$
$$Q_3 = L + \frac{c}{f} \left( \frac{3n}{4} - d \right)$$

### Çeyrekler Açıklığı ($IQR$ - Interquartile Range)
Sınavlarda sıklıkla sorulan bir yayılım ölçüsüdür:
$$IQR = Q_3 - Q_1$$
*(Verilerin ortasındaki %50'lik dilimin genişliğidir. Aşırı uç değerlerden etkilenmez).*

---

## 3. Dersteki Uygulama: Örnek 1.13 (Slayt Örneği)

*(İlaçla tedavi edilen 8 hastanın iyileşme süreleri gün olarak verilmiştir. Çeyrek değerleri hesaplayınız).*

![[örnek 1.13.jpg]]

**Ham Veri Seti ($n = 8$):**
> `30, 20, 24, 40, 65, 70, 10, 62`

**Küçükten Büyüğe Sıralanışı:**
> $X_{(1)}=10, \quad X_{(2)}=20, \quad X_{(3)}=24, \quad X_{(4)}=30 \quad \mid \quad X_{(5)}=40, \quad X_{(6)}=62, \quad X_{(7)}=65, \quad X_{(8)}=70$

* **1. Çeyreklik ($Q_1$):**
  $$\text{Sıra} = \frac{n}{4} = \frac{8}{4} = 2 \implies Q_1 = \frac{X_{(2)} + X_{(3)}}{2} = \frac{20 + 24}{2} = \mathbf{22\text{ gün}}$$
* **2. Çeyreklik ($Q_2$ - Medyan):**
  $$\text{Sıra} = \frac{2n}{4} = \frac{8}{2} = 4 \implies Q_2 = \frac{X_{(4)} + X_{(5)}}{2} = \frac{30 + 40}{2} = \mathbf{35\text{ gün}}$$
* **3. Çeyreklik ($Q_3$):**
  $$\text{Sıra} = \frac{3n}{4} = \frac{24}{4} = 6 \implies Q_3 = \frac{X_{(6)} + X_{(7)}}{2} = \frac{62 + 65}{2} = \mathbf{63.5\text{ gün}}$$
* **Çeyrekler Açıklığı ($IQR$):**
  $$IQR = Q_3 - Q_1 = 63.5 - 22 = \mathbf{41.5\text{ gün}}$$

---

## 4. Ek Uygulama: Örnek 1.7 Tablosu Üzerinde Medyan Hesabı

[[03 - Aritmetik Ortalama|Örnek 1.7]]'deki 1000 kişilik not tablosunda:
1. **Medyan Sırası:** $\frac{n}{2} = \frac{1000}{2} = 500$. sıradaki öğrenci.
2. **Medyan Sınıfı:** 3. sınıf $[40, 60)$ aralığıdır (Birikimli frekans 450'den 700'e çıkar).
3. **Değişkenler:** $L = 40, c = 20, f = 250, d = 450$
4. **Hesaplama:**
   $$\text{Medyan} = 40 + \frac{20}{250} \cdot (500 - 450) = 40 + \frac{20}{250} \cdot 50 = 40 + 4 = \mathbf{44}$$

---

## 🔗 İlgili Bağlantılar
* Mod hesabı ve çarpıklık karşılaştırması için: [[05 - Mod (Tepe Değer)]]
* Aritmetik ortalama ile karşılaştırma: [[03 - Aritmetik Ortalama]]
