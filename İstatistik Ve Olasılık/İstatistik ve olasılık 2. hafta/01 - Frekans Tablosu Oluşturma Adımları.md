# 01 - Frekans Tablosu Oluşturma Adımları

← [[00 - 2. Hafta Çalışma Rehberi (MOC)|Çalışma Rehberine Dön]] | Sonraki: [[02 - Kapsamlı Frekans Tablosu Örneği (80 Öğrenci)|02 - 80 Kişilik Örnek Tablo →]]

---

## 1. Giriş ve Temel Kavramlar

Büyük boyutlu veri setlerinde her bir veriyi teker teker listelemek veya incelemek pratik ve anlamlı değildir. Verileri özetlemek, desenleri görebilmek ve istatistiksel analizler yapabilmek için **frekans tabloları (gruplandırılmış dağılımlar)** oluşturulur.

* **Sınıf:** Değişkenin aldığı değerlerin birbirinden farklı alt gruplara veya aralıklara bölünmesiyle oluşan kategorilerdir. *(AI ekledi: tanım)*
* **Dağılım Sınırı:** Örneklemdeki en küçük değer ile en büyük değer arasındaki sınırlardır.
* **Dağılım Genişliği ($R$ / Ranj):** Bir örneklemdeki en büyük değer ile en küçük değer arasındaki farktır:
  $$R = X_{\text{en büyük}} - X_{\text{en küçük}}$$

---

## 2. Frekans Tablosu Hazırlama Adımları (7 Adımlık Kural)

Hocanın derste belirttiği mantıksal işlem sırası:

### 1. Adım: Sınıf Sayısının ($k$) Belirlenmesi
* Frekans tablosu oluştururken ilk adım kaç sınıf ($k$) olacağına karar verilmesidir.
* Sınıf sayısının genellikle **8 – 15** arasında olması önerilir.
* En uygun sınıf sayısının belirlenmesinde kök kuralı kullanılır:
  $$\sqrt{n} \le k$$
  *(burada $n$: toplam gözlem/veri sayısı, $k$: sınıf sayısıdır)*

### 2. Adım: Sınıf Aralık Uzunluğunun ($c$) Hesaplanması
* **Sınıf Aralığı ($c$):** İki sınıf arasındaki farka sınıf aralığı denir ve $c$ ile gösterilir *(Tanım 1.14)*.
* Dağılım genişliğinin ($R$) sınıf sayısına ($k$) bölünmesi ile bulunur:
  $$c \approx \frac{R}{k} = \frac{\text{Dağılım Genişliği}}{\text{Sınıf Sayısı}} \quad \text{*(AI ekledi: formül)*}$$
* Verilerin açıkta kalmaması için $c$ genellikle bir üst tam sayıya yuvarlanır.

### 3. Adım: Sınıf Sınırlarının Belirlenmesi
* **Alt Sınır ($A_s$):** Bir sınıfın en küçük değerine alt sınır denir ve $A_s$ ile gösterilir.
* **Üst Sınır ($U_s$):** Bir sınıfın en büyük değerine üst sınır denir ve $U_s$ ile gösterilir.
* İlk sınıfın alt sınırı genellikle en küçük veri ($X_{\min}$) seçilir ve ardışık alt sınıflar $c$ eklenerek oluşturulur.

### 4. Adım: Sınıf Değerlerinin ($S_s$ / $S_i$) Belirlenmesi
* **Sınıf Değeri ($S_i$ veya $S_s$):** Bir sınıfın alt sınır ve üst sınır değerlerinin aritmetik ortalamasına (orta noktasına) denir:
  $$S_i = \frac{A_s + U_s}{2} \quad \text{*(AI ekledi: formül)*}$$

### 5. Adım: Frekans Değerlerinin ($f_i$) Belirlenmesi
* **Frekans / Sıklık ($f_i$):** Bir sınıfa ($i$. sınıfa) düşen veri sayısına frekans denir.
* Frekansların toplamı toplam gözlem sayısına ($n$) eşit olmalıdır:
  $$\sum f_i = n$$

### 6. Adım: Göreli Frekansların ($P_i$) Belirlenmesi
* **Göreli (Rölatif / Oransal) Frekans ($P_i$):** Her sınıfa düşen veri sayısının ($f_i$) toplam veri sayısına ($n$) oranına denir:
  $$P_i = \frac{f_i}{n}$$
* Tüm sınıfların göreli frekansları toplamı 1'e (%100'e) eşittir: $\sum P_i = 1.00$.

### 7. Adım: "-den Az" ve "-den Çok" Birikimli Frekansların Bulunması
* **"-den Az" Birikimli Frekans:** Belirli bir sınıfın üst sınırından daha küçük veya eşit olan verilerin toplam sayısıdır (yukarıdan aşağıya frekanslar toplanarak ilerler). *(AI ekledi)*
* **"-den Çok" Birikimli Frekans:** Belirli bir sınıfın alt sınırından daha büyük veya eşit olan verilerin toplam sayısıdır (toplam frekanstan çıkarılarak veya aşağıdan yukarıya toplanarak ilerler). *(AI ekledi)*

---

## 3. Örnek Tablo (50 Kişilik Sınav Notları Dağılımı)

| Sınıf Aralığı [$A_s - U_s$] | Sınıf Değeri ($S_i$) | Frekans ($f_i$) | Göreli Frekans ($P_i$) | "-den Az" Frekans *(AI ekledi)* | "-den Çok" Frekans *(AI ekledi)* |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 50 – 59 | 54.5 | 5 | 0.10 (%10) | 5 | 50 |
| 60 – 69 | 64.5 | 12 | 0.24 (%24) | 17 | 45 |
| 70 – 79 | 74.5 | 18 | 0.36 (%36) | 35 | 33 |
| 80 – 89 | 84.5 | 10 | 0.20 (%20) | 45 | 15 |
| 90 – 100 | 95.0 | 5 | 0.10 (%10) | 50 | 5 |
| **Toplam** | — | **50** | **1.00 (%100)** | — | — |

---

## 🔗 İlgili Bağlantılar
* Bu adımların gerçek bir ham veri kümesinde baştan sona nasıl uygulandığını görmek için: [[02 - Kapsamlı Frekans Tablosu Örneği (80 Öğrenci)]]
* Bu tablolardan aritmetik ortalama hesabı için: [[03 - Aritmetik Ortalama]]
