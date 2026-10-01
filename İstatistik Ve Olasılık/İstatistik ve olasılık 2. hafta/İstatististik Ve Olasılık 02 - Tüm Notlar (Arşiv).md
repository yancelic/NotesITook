# İstatistik ve Olasılık 02

Büyük boyutlu veri setlerinde her bir veriyi teker teker listelemek yerine frekans tabloları oluşturmak daha mantıklıdır.

---

## 1. Temel Kavramlar ve Dağılım Ölçütleri

* **Sınıf:** Değişkenin aldığı değerlerin birbirinden farklı alt gruplara veya aralıklara bölünmesiyle oluşan kategorilerdir. *(AI ekledi: tanım tamamlama)*
* **Dağılım Sınırı:** Örneklemdeki en küçük değer ile en büyük değer arasındaki sınırlardır.
* **Dağılım Genişliği ($R$ / Ranj):** Bir örneklemde en büyük değer ile en küçük değer arasındaki farka dağılım genişliği denir ve $R$ ile gösterilir:
  $$R = X_{\text{en büyük}} - X_{\text{en küçük}}$$

---

## 2. Frekans Tablosu Hazırlama Adımları ve Tanımlar

Hocanın belirttiği işlem sırası özeti:
1. Kaç sınıf olacağına karar verilir ($k$)
2. Sınıf aralık uzunluğu belirlenir ($c$)
3. Sınıf sınırları belirlenir ($A_s$ ve $U_s$)
4. Sınıf değerleri ($S_s$ / $S_i$) belirlenir
5. Frekans değerleri ($f_i$) belirlenir
6. Göreli frekanslar ($P_i$) belirlenir
7. "-den daha az" ve "-den daha çok" eklemeli (birikimli) frekanslar bulunur

---

### Adım 1: Sınıf Sayısının ($k$) Belirlenmesi
* Frekans tablosu oluştururken ilk adım kaç sınıf olacağına karar verilmesidir.
* Sınıf sayısının genellikle **8 – 15** arasında olması önerilir.
* En uygun sınıf sayısının belirlenmesinde:
  $$\sqrt{n} \le k$$
  *(burada $n$: toplam gözlem/veri sayısı, $k$: sınıf sayısıdır)*

### Adım 2: Sınıf Aralık Uzunluğunun ($c$) Hesaplanması
* **Sınıf Aralığı ($c$):** İki sınıf arasındaki farka sınıf aralığı denir ve $c$ ile gösterilir *(Tanım 1.14)*.
* Dağılım genişliğinin ($R$) sınıf sayısına ($k$) bölünmesi ile bulunur:
  $$c \approx \frac{R}{k} = \frac{\text{Dağılım Genişliği}}{\text{Sınıf Sayısı}} \quad \text{*(AI ekledi: formül)*}$$

### Adım 3: Sınıf Sınırlarının Belirlenmesi
* **Alt Sınır ($A_s$):** Bir sınıfın en küçük değerine alt sınır denir ve $A_s$ ile gösterilir.
* **Üst Sınır ($U_s$):** Bir sınıfın en büyük değerine üst sınır denir ve $U_s$ ile gösterilir.

### Adım 4: Sınıf Değerlerinin ($S_s$ / $S_i$) Belirlenmesi
* **Sınıf Değeri ($S_s$ veya $S_i$):** Bir sınıfın alt sınır ve üst sınır değerlerinin ortalamasına (sınıf orta noktasına) denir ve $S_s$ ile gösterilir:
  $$S_s = \frac{A_s + U_s}{2} \quad \text{*(AI ekledi: formül)*}$$

### Adım 5: Frekans Değerlerinin ($f_i$) Belirlenmesi
* **Frekans / Sıklık ($f_i$):** Bir sınıfa ($i$. sınıfa) düşen veri sayısına frekans/sıklık denir ve $f_i$ ile gösterilir.
  * Frekansların toplamı elimizdeki toplam veri sayısına ($n$) eşit olmalıdır:
    $$\sum f_i = n$$

### Adım 6: Göreli Frekansların ($P_i$) Belirlenmesi
* **Göreli (Rölatif / Oransal) Frekans ($P_i$):** Her sınıfa düşen veri sayısının ($f_i$) toplam veri sayısına ($n$) oranına denir ve $P_i$ ile gösterilir:
  $$P_i = \frac{f_i}{n}$$
  *(Tüm sınıfların göreli frekansları toplamı 1'e yani %100'e eşittir: $\sum P_i = 1$)*

### Adım 7: "-den Az" ve "-den Çok" Birikimli Frekansların Bulunması
* **"-den Az" Birikimli Frekans:** Belirli bir sınıfın üst sınırından daha küçük veya eşit olan verilerin toplam sayısıdır (frekanslar yukarıdan aşağıya toplanarak bulunur). *(AI ekledi)*
* **"-den Çok" Birikimli Frekans:** Belirli bir sınıfın alt sınırından daha büyük veya eşit olan verilerin toplam sayısıdır (toplam frekanstan çıkarılarak veya aşağıdan yukarıya toplanarak bulunur). *(AI ekledi)*

---

## 3. Örnek 1: Sınav Notları Dağılımı

*(Örnek: 50 kişilik bir grupta sınav notlarının dağılımı)*

| Sınıf Aralığı [$A_s - U_s$] | Sınıf Değeri ($S_s$) | Frekans ($f_i$) | Göreli Frekans ($P_i$) | "-den Az" Frekans *(AI ekledi)* | "-den Çok" Frekans *(AI ekledi)* |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 50 – 59 | 54.5 | 5 | 0.10 (%10) | 5 | 50 |
| 60 – 69 | 64.5 | 12 | 0.24 (%24) | 17 | 45 |
| 70 – 79 | 74.5 | 18 | 0.36 (%36) | 35 | 33 |
| 80 – 89 | 84.5 | 10 | 0.20 (%20) | 45 | 15 |
| 90 – 100 | 95.0 | 5 | 0.10 (%10) | 50 | 5 |
| **Toplam** | — | **50** | **1.00 (%100)** | — | — |

---

## 4. Örnek 2: 80 Öğrencinin Dinlenme Halindeki Nabız Sayısı (Adım Adım Çözüm) *(AI ekledi)*

### Ham Veri Seti ($n = 80$)
> `86, 98, 81, 83, 96, 89, 81, 60, 67, 102*, 83, 69, 77, 67, 77, 81, 68, 76, 72, 80, 85, 79, 58, 81, 99, 93, 73, 75, 68, 70, 75, 105, 80, 79, 76, 77, 72, 84, 81, 55, 89, 70, 81, 48, 71, 67, 81, 80, 73, 77, 88, 61, 81, 73, 73, 81, 63, 83, 82, 87, 82, 83, 82, 71, 65, 62, 82, 77, 69, 69, 53, 74, 77, 93, 93, 74, 78, 80, 85, 73`
> 
> *\*(Not: Veri setinde yazılan 1022 değeri, fizyolojik tutarlılık ve toplam 80 veri olması gereği 102 kabul edilmiştir).*

---

### Tablo Oluşturma Adımlarının Uygulanışı

#### Ön Hazırlık: Dağılım Genişliği ($R$)
* **En küçük değer ($X_{\min}$):** $48$
* **En büyük değer ($X_{\max}$):** $105$
* **Dağılım Genişliği ($R$):**
  $$R = X_{\max} - X_{\min} = 105 - 48 = 57$$

#### 1. Adım: Kaç Sınıf Olacağına Karar Verilir ($k$)
* Kural: $\sqrt{n} \le k$
  $$\sqrt{80} \approx 8.94 \le k \implies k = 9 \text{ sınıf seçildi.}$$
  *(8 – 15 arası önerisine tam uygundur).*

#### 2. Adım: Sınıf Aralık Uzunluğu Belirlenir ($c$)
* Formül: $c \approx \frac{R}{k}$
  $$c \approx \frac{57}{9} \approx 6.33$$
* Bütün verilerin açıkta kalmadan kapsanması için tamsayıya yuvarlanır:
  $$c = 7$$

#### 3. Adım: Sınıf Sınırları Belirlenir ($A_s$ ve $U_s$)
* İlk sınıfın alt sınırı en küçük veri olan $A_1 = 48$ olarak alınır.
* Aralık uzunluğu $c = 7$ olduğu için ardışık alt sınırlara 7 eklenir (her sınıf 7 tam sayı barındırır):
  * **1. Sınıf:** $48 – 54$ *(48, 49, 50, 51, 52, 53, 54: tam 7 değer)*
  * **2. Sınıf:** $55 – 61$
  * **3. Sınıf:** $62 – 68$
  * **4. Sınıf:** $69 – 75$
  * **5. Sınıf:** $76 – 82$
  * **6. Sınıf:** $83 – 89$
  * **7. Sınıf:** $90 – 96$
  * **8. Sınıf:** $97 – 103$
  * **9. Sınıf:** $104 – 110$ *(En büyük değerimiz olan 105 son sınıfa dahil olur).*

#### 4. Adım: Sınıf Değerleri ($S_s$) Hesaplanır
* Her sınıfın orta noktası: $S_s = \frac{A_s + U_s}{2}$
  * 1. Sınıf: $(48 + 54) / 2 = 51.0$
  * 2. Sınıf: $(55 + 61) / 2 = 58.0$
  * *(Her adımda sınıf aralığı kadar, yani $+7$ artarak gider).*

#### 5. Adım: Frekans Değerleri ($f_i$) Belirlenir
* Ham verilerin hangi sınıf aralığına düştüğü sayılır:
  * $48 – 54 \implies 2$ kişi ($48, 53$)
  * $55 – 61 \implies 4$ kişi ($55, 58, 60, 61$)
  * $62 – 68 \implies 8$ kişi
  * $69 – 75 \implies 18$ kişi
  * $76 – 82 \implies 28$ kişi
  * $83 – 89 \implies 12$ kişi
  * $90 – 96 \implies 4$ kişi
  * $97 – 103 \implies 3$ kişi ($98, 99, 102$)
  * $104 – 110 \implies 1$ kişi ($105$)
  * **Toplam:** $\sum f_i = 2 + 4 + 8 + 18 + 28 + 12 + 4 + 3 + 1 = 80$ ($n$'e eşittir).

#### 6. Adım: Göreli Frekanslar ($P_i$) Hesaplanır
* Formül: $P_i = \frac{f_i}{n} = \frac{f_i}{80}$
  * 1. Sınıf: $P_1 = 2 / 80 = 0.0250$ (%2.50)
  * 2. Sınıf: $P_2 = 4 / 80 = 0.0500$ (%5.00)
  * ...
  * **Toplam:** $\sum P_i = 1.0000$ (%100).

#### 7. Adım: "-den Az" ve "-den Çok" Frekanslar Bulunur
* **"-den Az" (Üst sınırdan küçük veya eşit olanlar - yukarıdan aşağıya toplanarak):**
  * 54'ten az: $2$
  * 61'den az: $2 + 4 = 6$
  * 68'den az: $6 + 8 = 14$
  * 75'ten az: $14 + 18 = 32$
  * 82'den az: $32 + 28 = 60$
  * 89'den az: $60 + 12 = 72$
  * 96'dan az: $72 + 4 = 76$
  * 103'ten az: $76 + 3 = 79$
  * 110'dan az: $79 + 1 = 80$
* **"-den Çok" (Alt sınırdan büyük veya eşit olanlar - aşağıdan yukarıya toplanarak veya toplamdan çıkarılarak):**
  * 48'den çok: $80$
  * 55'ten çok: $80 - 2 = 78$
  * 62'den çok: $78 - 4 = 74$
  * 69'dan çok: $74 - 8 = 66$
  * 76'dan çok: $66 - 18 = 48$
  * 83'ten çok: $48 - 28 = 20$
  * 90'dan çok: $20 - 12 = 8$
  * 97'den çok: $8 - 4 = 4$
  * 104'ten çok: $4 - 3 = 1$

---

### Nihai Frekans Tablosu (80 Kişilik Kalp Atış Verisi)

| Sınıf No | Sınıf Aralığı [$A_s - U_s$] | Sınıf Değeri ($S_s$) | Frekans ($f_i$) | Göreli Frekans ($P_i$) | "-den Az" Frekans | "-den Çok" Frekans |
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

## 5. Merkezi Eğilim ve Merkezi Dağılım (Yayılım) Ölçütleri

Hocanın derste açtığı iki ana başlık:
1. **Merkezi Eğilim Ölçüleri:** Verilerin hangi merkezi değer etrafında toplandığını gösterir (Aritmetik Ortalama, Medyan, Mod vb.). *(AI ekledi)*
2. **Merkezi Dağılım (Yayılım) Ölçüleri:** Verilerin bu merkez etrafında ne kadar yayıldığını/saçıldığını gösterir (Ranj, Varyans, Standart Sapma vb.). *(AI ekledi)*

> [!NOTE]
> **Ders İçi Not:** Hoca bu analiz ve hesaplamaların bilgisayar ortamında yapılması için ilerleyen aşamalarda **R / RStudio** programını göstereceğini belirtti.

---

## 6. Aritmetik Ortalama ($\bar{X}$)

Veri setindeki gözlemlerin toplamının toplam gözlem sayısına bölünmesiyle elde edilen en yaygın merkezi eğilim ölçüsüdür.

### A) Ham (Sınıflandırılmamış) Veriler İçin Aritmetik Ortalama
Bildiğimiz standart aritmetik ortalama formülüdür:
$$\bar{X} = \frac{\sum_{i=1}^n X_i}{n} = \frac{X_1 + X_2 + \dots + X_n}{n} \quad \text{*(AI ekledi: formül)*}$$
*(burada $X_i$: her bir veri değeri, $n$: toplam veri sayısıdır)*

---

### B) Sınıflandırılmış Veriler İçin Aritmetik Ortalama

> **Önemli Eşitlik:** **Sınıflandırılmış Veri = Frekans Tablosu** haline getirilmiş, sınıflara gruplanmış verilerdir.

Frekans tablosunda ham veriler aralıklara ayrıldığı için tek tek veriler yerine her sınıfı temsilen o sınıfın **orta noktası / sınıf değeri ($S_i$)** kullanılır. *(AI ekledi)*

#### Formül:
$$\bar{X} = \frac{\sum_{i=1}^k (f_i \cdot S_i)}{n} = \frac{\sum_{i=1}^k (f_i \cdot S_i)}{\sum_{i=1}^k f_i} \quad \text{*(AI ekledi: formül)*}$$

**Sembollerin Anlamı:** *(AI ekledi)*
* $k$: Sınıf sayısı
* $S_i$: $i$. sınıfın sınıf değeri (orta noktası: $\frac{A_s + U_s}{2}$)
* $f_i$: $i$. sınıfın frekansı (gözlem sayısı)
* $n$: Toplam gözlem sayısı ($n = \sum f_i$)

*(Alternatif olarak göreli frekansla yazımı: $\bar{X} = \sum_{i=1}^k (P_i \cdot S_i)$)* *(AI ekledi)*

#### Mantığı ve İşlem Adımları: *(AI ekledi)*
1. Her sınıfın frekansı ($f_i$) ile o sınıfın değeri ($S_i$) çarpılır: $(f_i \cdot S_i)$.
2. Elde edilen tüm $(f_i \cdot S_i)$ değerleri toplanır: $\sum (f_i \cdot S_i)$.
3. Bulunan toplam, genel gözlem sayısına ($n$) bölünür.

---

#### Uygulama: Örnek 1.7 (Dersteki Slayt / Tahta Örneği)
*(Örnek 1.4'te verilen sınıflandırılmış frekans tablosundaki verilerin aritmetik ortalaması)*

![[IMG_20260923_110649.jpg]]

| $i$ (Sınıf) | Sınıf Aralığı | Sınıf Değeri ($S_i$) | Frekans ($f_i$) | $S_i \cdot f_i$ |
| :---: | :---: | :---: | :---: | :---: |
| **1** | $[0, 20)$ | 10 | 100 | $10 \cdot 100 = 1000$ |
| **2** | $[20, 40)$ | 30 | 350 | $30 \cdot 350 = 10500$ |
| **3** | $[40, 60)$ | 50 | 250 | $50 \cdot 250 = 12500$ |
| **4** | $[60, 80)$ | 70 | 200 | $70 \cdot 200 = 14000$ |
| **5** | $[80, 100]$ | 90 | 100 | $90 \cdot 100 = 9000$ |
| **Toplam** | — | — | **$n = 1000$** | **$\sum_{i=1}^5 (S_i \cdot f_i) = 47000$** |

**Notların Aritmetik Ortalaması:**
$$\bar{X} = \frac{\sum_{i=1}^k (S_i \cdot f_i)}{n} = \frac{47000}{1000} = 47$$

> [!NOTE]
> **Tahtadaki Ek Not:** Görselin sağ tarafındaki beyaz tahtada $\sqrt{n} \le k$ kuralı ve 1. sınıfın göreli frekansı ($P_1 = \frac{f_1}{n}$) formülü yer almaktadır.

---

## 7. Medyan / Ortanca ($\tilde{X}$ veya $M$)

Küçükten büyüğe sıralanmış bir veri setini tam ortadan iki eşit parçaya bölen (%50'si altında, %50'si üstünde kalan) merkezi eğilim ölçüsüdür. Aşırı uç değerlerden etkilenmez. *(AI ekledi: tanım)*

---

### A) Ham (Sınıflandırılmamış) Veriler İçin Medyan
Veriler öncelikle küçükten büyüğe doğru sıralanır:
* **$n$ tek sayı ise:** Medyan tam ortadaki gözlemdir:
  $$\text{Sıra No} = \frac{n + 1}{2}$$
  $$\text{Medyan} = X_{\left(\frac{n+1}{2}\right)} \quad \text{*(AI ekledi: formül)*}$$
* **$n$ çift sayı ise:** Ortadaki iki değerin aritmetik ortalamasıdır:
  $$\text{Medyan} = \frac{X_{\left(\frac{n}{2}\right)} + X_{\left(\frac{n}{2} + 1\right)}}{2} \quad \text{*(AI ekledi: formül)*}$$

---

### B) Sınıflandırılmış Veriler İçin Medyan (Medyan Tahmini)

Sınıflandırılmış verilerde ham gözlem değerleri tek tek bilinmediğinden, frekans tablosu üzerinden **doğrusal enterpolasyon (tahmin)** yapılarak medyan bulunur. *(AI ekledi)*

#### Formül:
$$\text{Medyan} = L + \frac{c}{f} \left( \frac{n}{2} - d \right)$$

#### Formüldeki Harflerin Anlamları:
* **$n$:** Toplam gözlem / veri sayısı ($n = \sum f_i$).
* **$\frac{n}{2}$:** Medyan gözleminin sıra konumu.
* **Medyan Sınıfı:** "-den az" birikimli frekansın $\frac{n}{2}$ değerine ilk ulaştığı veya bu değeri ilk geçtiği sınıftır. *(AI ekledi)*
* **$L$:** Medyan sınıfının **alt sınırı** ($A_s$).
* **$c$:** Medyan sınıfının **sınıf aralığı** (uzunluğu).
* **$f$:** Medyan sınıfının kendi **frekansı** ($f_i$).
* **$d$:** Medyan sınıfından **önceki sınıfa kadarki birikimli (-den az) frekanslar toplamı**.

---

#### Uygulama: Örnek 1.7 Tablosu Üzerinde Medyan Hesabı *(AI ekledi)*

Yukarıdaki 1000 kişilik sınav notları tablosu üzerinden hesaplayalım:
1. **Medyan Sırası:** $\frac{n}{2} = \frac{1000}{2} = 500$. sıradaki öğrenci aranıyor.
2. **Medyan Sınıfını Bulma:**
   * 1. Sınıf $[0, 20)$: $f_1 = 100 \implies$ Birikimli: $100$
   * 2. Sınıf $[20, 40)$: $f_2 = 350 \implies$ Birikimli: $100 + 350 = 450$
   * 3. Sınıf $[40, 60)$: $f_3 = 250 \implies$ Birikimli: $450 + 250 = 700$ *(500. kişi bu sınıfın içindedir!)*
   * **Medyan Sınıfı:** 3. sınıf olan **$[40, 60)$** aralığıdır.
3. **Değişkenleri Belirleme:**
   * $L = 40$ (Medyan sınıfının alt sınırı)
   * $c = 20$ (Sınıf aralığı: $60 - 40 = 20$)
   * $f = 250$ (Medyan sınıfının frekansı)
   * $d = 450$ (Önceki sınıfların toplam frekansı: $100 + 350 = 450$)
4. **Formüle Yerleştirme:**
   $$\text{Medyan} = 40 + \frac{20}{250} \cdot (500 - 450)$$
   $$\text{Medyan} = 40 + \frac{20}{250} \cdot 50 = 40 + 4 = 44$$

---

## 8. Mod / Tepe Değer ($M_o$ veya $\text{Mod}$)

Bir veri setinde frekansı en yüksek olan, yani **en çok tekrar eden** gözlem değeridir. Uç değerlerden etkilenmez ve nitel (kategorik) veriler için de hesaplanabilen tek merkezi eğilim ölçüsüdür. *(AI ekledi: tanım)*

---

### A) Ham (Sınıflandırılmamış) Veriler İçin Mod
Veri kümesinde en sık görülen değerdir:
* **Tek Modlu (Unimodal):** Tek bir en çok tekrar eden değer varsa. *(AI ekledi)*
  * *Örnek:* $3, 5, 5, 7, 8 \implies \text{Mod} = 5$
* **Çok Modlu (Bimodal / Multimodal):** En yüksek frekansa sahip birden fazla değer varsa. *(AI ekledi)*
  * *Örnek:* $2, 2, 4, 6, 6, 9 \implies \text{Modlar} = 2 \text{ ve } 6$
* **Modu Olmayan Dağılım:** Tüm değerlerin tekrarlanma sayısı aynıysa mod yoktur. *(AI ekledi)*
  * *Örnek:* $10, 20, 30, 40 \implies \text{Mod yoktur}$

---

### B) Sınıflandırılmış Veriler İçin Mod (Mod Tahmini)

Sınıflandırılmış verilerde mod, frekansı en yüksek olan **Mod Sınıfı** belirlendikten sonra komşu sınıfların frekansları arasındaki farklara göre enterpolasyonla bulunur.

#### Formül:
$$\text{Mod} = L + c \left( \frac{\Delta_1}{\Delta_1 + \Delta_2} \right)$$

#### Formüldeki Sembollerin Anlamları:
* **Mod Sınıfı:** Frekansı ($f_i$) en yüksek olan sınıftır. *(AI ekledi)*
* **$L$:** Mod sınıfının **alt sınırı** ($A_s$).
* **$c$:** Mod sınıfının **aralık genişliği** (uzunluğu).
* **$\Delta_1$ (Delta 1):** Mod sınıfının frekansı ile **bir önceki sınıfın frekansı** arasındaki fark: *(AI ekledi)*
  $$\Delta_1 = f_{\text{mod}} - f_{\text{önceki}}$$
* **$\Delta_2$ (Delta 2):** Mod sınıfının frekansı ile **bir sonraki sınıfın frekansı** arasındaki fark: *(AI ekledi)*
  $$\Delta_2 = f_{\text{mod}} - f_{\text{sonraki}}$$

---

#### Uygulama: Örnek 1.7 Tablosu Üzerinde Mod Hesabı *(AI ekledi)*

Slayttaki 1000 kişilik not dağılımı tablosunu inceleyelim:
* Sınıf Frekansları: $f_1 = 100$, $f_2 = 350$, $f_3 = 250$, $f_4 = 200$, $f_5 = 100$
1. **Mod Sınıfını Belirleme:**
   * En yüksek frekans $350$ olduğu için mod sınıfı 2. sınıf olan **$[20, 40)$** aralığıdır.
2. **Değişkenleri Belirleme:**
   * $L = 20$ (Mod sınıfının alt sınırı)
   * $c = 20$ (Sınıf genişliği: $40 - 20 = 20$)
   * $\Delta_1 = f_2 - f_1 = 350 - 100 = 250$ (Önceki sınıfla frekans farkı)
   * $\Delta_2 = f_2 - f_3 = 350 - 250 = 100$ (Sonraki sınıfla frekans farkı)
3. **Formüle Yerleştirme:**
   $$\text{Mod} = 20 + 20 \cdot \left( \frac{250}{250 + 100} \right)$$
   $$\text{Mod} = 20 + 20 \cdot \left( \frac{250}{350} \right) = 20 + 20 \cdot \frac{5}{7} \approx 20 + 14.29 = 34.29$$

> [!TIP]
> **Merkezi Eğilim Ölçüleri Karşılaştırması (Örnek 1.7 için):** *(AI ekledi)*
> * $\text{Mod} \approx 34.29$
> * $\text{Medyan} = 44.00$
> * $\text{Aritmetik Ortalama} (\bar{X}) = 47.00$
> 
> $\text{Mod} < \text{Medyan} < \bar{X}$ olduğu için bu dağılım **sağa çarpık (pozitif çarpık)** bir dağılımdır.

---

## 9. Çeyreklikler / Kartiller ($Q_1, Q_2, Q_3$)

Küçükten büyüğe sıralanmış bir veri kümesini **4 eşit parçaya (%25'lik dilimlere)** bölen 3 adet sınır değeridir. *(AI ekledi: tanım)*

```text
[En Küçük Değer] --- %25 --- [ Q1 ] --- %25 --- [ Q2 = Medyan ] --- %25 --- [ Q3 ] --- %25 --- [En Büyük Değer]
```

> [!IMPORTANT]
> **Hocanın "Sınavda Sorabilirim" Dediği Kritik Eşdeğerlikler:** *(AI ekledi)*
> 1. **1. Çeyreklik ($Q_1$ - Alt Çeyreklik):**
>    * **Öğrendiğimiz hangi kavramla aynı?** $\implies$ **25. Yüzdelik (Persentil - $P_{25}$)** ile birebir aynıdır ($Q_1 \equiv P_{25}$).
>    * **Tablodaki karşılığı:** Tabloda hesapladığımız **"-den az" birikimli frekansın** verilerin **%25'ine ($\frac{n}{4}$)** ulaştığı değerdir.
>    * **Formül:** Medyan formülündeki $\frac{n}{2}$ yerine $\frac{n}{4}$ yazılmış halidir.
> 2. **2. Çeyreklik ($Q_2$ - Ortanca):**
>    * **Öğrendiğimiz hangi kavramla aynı?** $\implies$ **Doğrudan MEDYAN'dır!** ($Q_2 \equiv \text{Medyan} \equiv P_{50}$).
>    * **Tablodaki karşılığı:** "-den az" frekans ile "-den çok" frekansın tam ortada kesiştiği (%50) değerdir.
>    * **Sınav Tuzağı:** Hoca sınavda *"2. çeyrekliğini bulunuz"* derse, aslında sizden bildiğiniz **Medyanı** bulmanızı istiyordur.
> 3. **3. Çeyreklik ($Q_3$ - Üst Çeyreklik):**
>    * **Öğrendiğimiz hangi kavramla aynı?** $\implies$ **75. Yüzdelik (Persentil - $P_{75}$)** ile birebir aynıdır ($Q_3 \equiv P_{75}$).
>    * **Tablodaki karşılığı:** Tablodaki **"-den az" birikimli frekansın** verilerin **%75'ine ($\frac{3n}{4}$)** ulaştığı değerdir.
>    * **Formül:** Medyan formülündeki $\frac{n}{2}$ yerine $\frac{3n}{4}$ yazılmış halidir.

---

### A) Ham (Sınıflandırılmamış) Verilerde Sıralar
Veriler küçükten büyüğe dizildikten sonra aranacak elemanın sıra numarası:
* **$Q_1$ Sırası ($P_{25}$):** $\frac{n}{4}$ *(veya $\frac{n+1}{4}$)*
* **$Q_2$ Sırası (Medyan / $P_{50}$):** $\frac{2n}{4} = \frac{n}{2}$
* **$Q_3$ Sırası ($P_{75}$):** $\frac{3n}{4}$ *(veya $\frac{3(n+1)}{4}$)*

---

### B) Sınıflandırılmış Veriler İçin Çeyreklik Formülleri

> [!NOTE]
> **Formüllerin Mantığı (Neden Birebir Aynılar?):** *(AI ekledi)*
> Aslında Medyan, $Q_1$ ve $Q_3$ farklı formüller değildir. Hepsi istatistikteki genel **Bölünme Değeri / Konum Ölçüsü (Kantil)** ana formülünden türer:
> $$\text{Değer} = L + \frac{c}{f} (\text{Hedef Sıra} - d)$$
> * Hedef Sıra yerine $\frac{n}{4}$ yazınca $\implies Q_1$ ($P_{25}$)
> * Hedef Sıra yerine $\frac{n}{2}$ yazınca $\implies Q_2$ (Medyan)
> * Hedef Sıra yerine $\frac{3n}{4}$ yazınca $\implies Q_3$ ($P_{75}$)

#### 1. Çeyreklik ($Q_1 \equiv P_{25}$) Formülü:
$$Q_1 = L + \frac{c}{f} \left( \frac{n}{4} - d \right) \quad \text{*(AI ekledi: formül)*}$$
* $\frac{n}{4}$: $Q_1$ sınıfını belirleyen sıra sayısıdır (-den az frekansta $\frac{n}{4}$ değerinin ilk ulaşıldığı/aşıldığı sınıf $Q_1$ sınıfıdır).
* $L$: $Q_1$ sınıfının **alt sınırı**.
* $c$: $Q_1$ sınıfının **aralık genişliği**.
* $f$: $Q_1$ sınıfının **kendi frekansı**.
* $d$: $Q_1$ sınıfından **önceki sınıfların toplam frekansı**.

#### 2. Çeyreklik ($Q_2 \equiv \text{Medyan}$) Formülü:
$$Q_2 = L + \frac{c}{f} \left( \frac{2n}{4} - d \right) = L + \frac{c}{f} \left( \frac{n}{2} - d \right) = \text{Medyan} \quad \text{*(AI ekledi: formül)*}$$

#### 3. Çeyreklik ($Q_3 \equiv P_{75}$) Formülü:
$$Q_3 = L + \frac{c}{f} \left( \frac{3n}{4} - d \right) \quad \text{*(AI ekledi: formül)*}$$
* $\frac{3n}{4}$: $Q_3$ sınıfını belirleyen sıra sayısıdır (-den az frekansta $\frac{3n}{4}$ değerinin ilk ulaşıldığı/aşıldığı sınıf $Q_3$ sınıfıdır).
* $L$: $Q_3$ sınıfının **alt sınırı**.
* $c$: $Q_3$ sınıfının **aralık genişliği**.
* $f$: $Q_3$ sınıfının **kendi frekansı**.
* $d$: $Q_3$ sınıfından **önceki sınıfların toplam frekansı**.

---

### Ek Tanım: Çeyrekler Açıklığı ($IQR$ - Interquartile Range)
Sınavlarda yayılım ölçüsü olarak sıklıkla sorulur: *(AI ekledi)*
$$IQR = Q_3 - Q_1$$
*(Verilerin ortasındaki %50'lik dilimin genişliğini gösterir. Uç değerlerden etkilenmeyen dayanıklı bir yayılım ölçütüdür).*

---

#### Uygulama: Örnek 1.13 (Dersteki Slayt / Çeyreklikler Örneği)
*(İlaçla tedavi edilen 8 hastanın iyileşme süreleri gün olarak verilmiştir. Çeyrek değerleri hesaplayınız).*

![[örnek 1.13.jpg]]

**Ham Veri Seti ($n = 8$):**
> `30, 20, 24, 40, 65, 70, 10, 62`

**1. Adım: Veriler Küçükten Büyüğe Sıralanır:**
> $X_{(1)}=10, \quad X_{(2)}=20, \quad X_{(3)}=24, \quad X_{(4)}=30 \quad \mid \quad X_{(5)}=40, \quad X_{(6)}=62, \quad X_{(7)}=65, \quad X_{(8)}=70$

$n = 8$ (çift sayı) olduğundan:

* **1. Çeyreklik ($Q_1$ - Birinci Çeyrek):**
  * Sıra: $\frac{n}{4} = \frac{8}{4} = 2$. sıra.
  * 2. ve bir sonraki (3.) gözlemin aritmetik ortalaması alınır:
    $$Q_1 = \frac{X_{(2)} + X_{(3)}}{2} = \frac{20 + 24}{2} = \frac{44}{2} = 22 \text{ gün}$$

* **2. Çeyreklik ($Q_2$ - İkinci Çeyrek / Medyan):**
  * Sıra: $\frac{2n}{4} = \frac{n}{2} = \frac{8}{2} = 4$. sıra.
  * 4. ve 5. gözlemlerin aritmetik ortalamasıdır:
    $$Q_2 = \frac{X_{(4)} + X_{(5)}}{2} = \frac{30 + 40}{2} = \frac{70}{2} = 35 \text{ gün}$$

* **3. Çeyreklik ($Q_3$ - Üçüncü Çeyrek):**
  * Sıra: $\frac{3n}{4} = \frac{3 \cdot 8}{4} = 6$. sıra.
  * 6. ve 7. gözlemlerin aritmetik ortalamasıdır:
    $$Q_3 = \frac{X_{(6)} + X_{(7)}}{2} = \frac{62 + 65}{2} = \frac{127}{2} = 63.5 \text{ gün}$$

* **Çeyrekler Açıklığı ($IQR$):** *(AI ekledi)*
  $$IQR = Q_3 - Q_1 = 63.5 - 22 = 41.5 \text{ gün}$$

> [!NOTE]
> **Slayttaki Sınıflandırılmış Veri Notu:**
> Görselin üst kısmında yer alan formül notunda:
> * $f_3$: 3. çeyreklik sınıfının frekansı
> * $c$: sınıf aralığı
> * **Not:** $\frac{3n}{4}$ gözlemin bulunduğu sınıfın 3. çeyreklik ($Q_3$) sınıfı olduğu belirtilmektedir.


---

## 10. Geometrik Ortalama ($G$ veya $G.O.$)

Geometrik ortalama; özellikle oranlar, yüzdeler, büyüme/artış hızları ve katlanarak artan veriler için kullanılan duyarlı bir merkezi eğilim ölçüsüdür. Verilerden birinin 0 veya negatif olması durumunda hesaplanamaz. *(AI ekledi: tanım)*

---

### A) Ham (Sınıflandırılmamış) Veriler İçin Geometrik Ortalama
*(Hatırladığınız kural tamamen doğrudur: Tüm veriler çarpılır ve veri sayısı derecesinden kökü alınır).*

$$G = \sqrt[n]{X_1 \cdot X_2 \cdot \dots \cdot X_n} = \left( \prod_{i=1}^n X_i \right)^{1/n} \quad \text{*(AI ekledi: formül)*}$$

**Logaritma İle Hesaplama:**
Çok sayıda veriyi çarpmak ve yüksek dereceli kök almak zor olduğundan, pratikte logaritma dönüşümüyle hesaplanır: *(AI ekledi)*
$$\log G = \frac{\sum_{i=1}^n \log X_i}{n} \implies G = 10^{\frac{\sum \log X_i}{n}}$$

---

### B) Sınıflandırılmış Veriler İçin Geometrik Ortalama
Frekans tablosunda her bir sınıf değeri ($S_i$), frekansı ($f_i$) adet tekrar ettiğinden sınıf değerlerinin frekans kuvvetleri çarpılır ve $n$. dereceden kökü alınır: *(AI ekledi)*

$$G = \sqrt[n]{S_1^{f_1} \cdot S_2^{f_2} \cdot \dots \cdot S_k^{f_k}} = \left( \prod_{i=1}^k S_i^{f_i} \right)^{1/n} \quad \text{*(AI ekledi: formül)*}$$

**Logaritma İle Uygulama Formülü:**
$$\log G = \frac{\sum_{i=1}^k (f_i \cdot \log S_i)}{n} \implies G = 10^{\log G} \quad \text{*(AI ekledi: formül)*}$$
*(burada $S_i$: sınıf değeri, $f_i$: sınıf frekansı, $n$: toplam veri sayısı $\sum f_i$)*

---

#### Uygulama: 80 Öğrencinin Kalp Atışı Verisinde Geometrik Ortalama Hesabı *(AI ekledi)*

Daha önce hazırladığımız 80 kişilik nabız tablosundaki $S_i$ ve $f_i$ değerleriyle:

| Sınıf No | Sınıf Aralığı | Sınıf Değeri ($S_i$) | Frekans ($f_i$) | $\log_{10}(S_i)$ | $f_i \cdot \log_{10}(S_i)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | 48 – 54 | 51.0 | 2 | 1.7076 | 3.4151 |
| **2** | 55 – 61 | 58.0 | 4 | 1.7634 | 7.0537 |
| **3** | 62 – 68 | 65.0 | 8 | 1.8129 | 14.5033 |
| **4** | 69 – 75 | 72.0 | 18 | 1.8573 | 33.4320 |
| **5** | 76 – 82 | 79.0 | 28 | 1.8976 | 53.1336 |
| **6** | 83 – 89 | 86.0 | 12 | 1.9345 | 23.2140 |
| **7** | 90 – 96 | 93.0 | 4 | 1.9685 | 7.8739 |
| **8** | 97 – 103 | 100.0 | 3 | 2.0000 | 6.0000 |
| **9** | 104 – 110 | 107.0 | 1 | 2.0294 | 2.0294 |
| **Toplam** | — | — | **$n = 80$** | — | **$\sum = 150.6550$** |

* $\log G = \frac{150.6550}{80} \approx 1.8832$
* $$G = 10^{1.8832} \approx 76.42 \text{ bpm}$$

---

## 11. Harmonik Ortalama ($H$ veya $H.O.$)

Gözlem değerlerinin çarpmaya göre terslerinin ($1/X$) aritmetik ortalamasının tersidir. Genellikle birim zamanda yapılan iş, hız, verimlilik ve oran hesaplamalarında kullanılır. Veriler içinde 0 değeri bulunmamalıdır. *(AI ekledi: tanım)*

---

### A) Ham (Sınıflandırılmamış) Veriler İçin Harmonik Ortalama
Gözlem sayısının, verilerin terslerinin toplamına bölünmesidir:

$$H = \frac{n}{\sum_{i=1}^n \frac{1}{X_i}} = \frac{n}{\frac{1}{X_1} + \frac{1}{X_2} + \dots + \frac{1}{X_n}} \quad \text{*(AI ekledi: formül)*}$$

---

### B) Sınıflandırılmış Veriler İçin Harmonik Ortalama
Frekans tablosunda her bir sınıfa ait frekansın ($f_i$) o sınıfın değerine ($S_i$) oranlarının toplamı paydada yer alır: *(AI ekledi)*

$$H = \frac{n}{\sum_{i=1}^k \frac{f_i}{S_i}} = \frac{\sum f_i}{\frac{f_1}{S_1} + \frac{f_2}{S_2} + \dots + \frac{f_k}{S_k}} \quad \text{*(AI ekledi: formül)*}$$

---

#### Uygulama: 80 Öğrencinin Kalp Atışı Verisinde Harmonik Ortalama Hesabı *(AI ekledi)*

Tablodaki $\frac{f_i}{S_i}$ sütun değerleri:
* Sınıf 1: $2 / 51.0 \approx 0.03922$
* Sınıf 2: $4 / 58.0 \approx 0.06897$
* Sınıf 3: $8 / 65.0 \approx 0.12308$
* Sınıf 4: $18 / 72.0 = 0.25000$
* Sınıf 5: $28 / 79.0 \approx 0.35443$
* Sınıf 6: $12 / 86.0 \approx 0.13953$
* Sınıf 7: $4 / 93.0 \approx 0.04301$
* Sınıf 8: $3 / 100.0 = 0.03000$
* Sınıf 9: $1 / 107.0 \approx 0.00935$
* **Toplam $\sum \left( \frac{f_i}{S_i} \right)$:** $\approx 1.05758$

* **Harmonik Ortalama:**
  $$H = \frac{80}{1.05758} \approx 75.64 \text{ bpm}$$

---

> [!TIP]
> **Ortalamalar Arasındaki Altın Kural (Sınav Klasiği):** *(AI ekledi)*
> Pozitif değerlerden oluşan herhangi bir veri setinde ortalamalar arasındaki büyüklük sıralaması daima şöyledir:
> $$H \le G \le \bar{X}$$
> *(Harmonik Ortalama $\le$ Geometrik Ortalama $\le$ Aritmetik Ortalama)*
> 
> *Bizim 80 Kişilik Nabız Örneğimizde:*
> $$75.64 \le 76.42 \le 77.16 \quad \checkmark$$

