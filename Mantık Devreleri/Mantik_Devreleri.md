[[XXX_DERS_PROGRAMI]]

# Mantık Devreleri: Sayı Sistemleri ve Dönüşümleri

#ders #donem3 #mantik_devreleri

> [!NOTE] 𝐾 Goodnotes PDF Defteri & El Yazmaları
> - *Bu klasöre (Mantık Devreleri) henüz PDF eklenmedi.*

---

## 1. Giriş ve Temel Kavramlar

Dijital mantık devrelerinde tüm veriler elektrik sinyallerinin iki durumu (Var/Yok, Yüksek/Alçak gerilim, 1/0) ile temsil edilir. Bu nedenle sayı sistemleri, devre tasarımının temelini oluşturur.

Herhangi bir $r$ tabanındaki (radix) sayı genel olarak şu şekilde ifade edilir:

$$N = (a_{n-1} a_{n-2} \dots a_1 a_0 . a_{-1} a_{-2} \dots a_{-m})_r$$

Bu sayının onlu (decimal) karşılığı basamak ağırlıkları açılarak hesaplanır:

$$N = \sum_{i=-m}^{n-1} a_i \cdot r^i = a_{n-1} r^{n-1} + \dots + a_1 r^1 + a_0 r^0 + a_{-1} r^{-1} + a_{-2} r^{-2} + \dots$$

### Temel Tabanlar

| Sistem | Taban ($r$) | Kullanılan Semboller / Rakamlar | Örnek |
| :--- | :---: | :--- | :--- |
| **İkili (Binary)** | $2$ | $0, 1$ | $(1011.01)_2$ |
| **Sekizli (Octal)** | $8$ | $0, 1, 2, 3, 4, 5, 6, 7$ | $(357.2)_8$ |
| **Onlu (Decimal)** | $10$ | $0, 1, 2, 3, 4, 5, 6, 7, 8, 9$ | $(249.5)_{10}$ |
| **Onaltılı (Hexadecimal)** | $16$ | $0, 1, 2, 3, 4, 5, 6, 7, 8, 9, \text{A}(10), \text{B}(11), \text{C}(12), \text{D}(13), \text{E}(14), \text{F}(15)$ | $(2\text{A}3.\text{C})_{16}$ |

---

## 2. Sayı Sistemi Dönüşümleri

### 2.1. Herhangi Bir Tabandan Onlu (Decimal) Tabana Dönüşüm
Basamak ağırlıkları yöntemi uygulanır. Sayı virgülün solunda $r^0, r^1, r^2 \dots$, sağında $r^{-1}, r^{-2} \dots$ ile çarpılarak toplanır.

$$\text{Örnek: } (1101.1)_2 = (1 \cdot 2^3) + (1 \cdot 2^2) + (0 \cdot 2^1) + (1 \cdot 2^0) + (1 \cdot 2^{-1}) = 8 + 4 + 0 + 1 + 0.5 = (13.5)_{10}$$

---

### 2.2. Onlu (Decimal) Tabandan Herhangi Bir Tabana Dönüşüm

Bu işlem iki ayrı adımda yapılır:
1. **Tam Kısım (Ardışık Bölme Yöntemi):** Sayı hedef tabana bölünür. Kalanlar not edilir, bölüm tekrar tabana bölünür. Bölüm 0 olana kadar devam edilir. Kalanlar **en son kalandan ilk kalana doğru (aşağıdan yukarıya)** yazılır.
2. **Kesirli Kısım (Ardışık Çarpma Yöntemi):** Kesirli kısım hedef tabanla çarpılır. Oluşan tam kısım not edilir. Kalan kesirli kısım tekrar hedef tabanla çarpılır. İstenilen hassasiyete ulaşana ya da kesir sıfırlanana kadar gidilir. Tam kısımlar **ilk çıkandan sona doğru (yukarıdan aşağıya)** yazılır.

---

### 2.3. İkili, Sekizli ve Onaltılı Arasında Hızlı Doğrudan Dönüşümler

Bu tabanlar 2'nin tam kuvveti olduğu için ($2^3 = 8$ ve $2^4 = 16$), onluk sisteme geçmeden doğrudan bit gruplama yöntemiyle dönüştürülür:

- **Binary $\leftrightarrow$ Octal:** Virgülden başlayarak sola ve sağa doğru **3'erli gruplar** oluşturulur.
  - Örnek: $(011 \ 101)_2 = (35)_8$
- **Binary $\leftrightarrow$ Hexadecimal:** Virgülden başlayarak sola ve sağa doğru **4'erli gruplar** oluşturulur.
  - Örnek: $(1011 \ 1100)_2 = (\text{BC})_{16}$
- **Octal $\leftrightarrow$ Hexadecimal:** Sayı önce Binary'ye açılır, ardından 4'erli (veya 3'erli) gruplanarak hedefe çevrilir.

---

## 3. İşaretli Sayılar ve Tümleyen (Complement) Aritmetiği

Dijital sistemlerde negatif sayılar üç farklı yöntemle temsil edilebilir:
1. **İşaret ve Büyüklük (Sign-Magnitude):** En soldaki bit (MSB) işarettir ($0 \rightarrow +, 1 \rightarrow -$). Geriye kalan bitler sayının büyüklüğünü belirtir.
2. **1'e Tümleyen (1's Complement):** Pozitif sayının tüm bitleri terslenir ($0 \rightarrow 1, 1 \rightarrow 0$).
3. **2'ye Tümleyen (2's Complement):** Dijital işlemcilerde standarttır. Negatif sayıyı bulmak için:
   $$\text{2'ye Tümleyen} = \text{1'e Tümleyen} + 1$$
   *Kısa Yol:* Sayının en sağından (LSB) başlanarak ilk $1$ görülene kadar tüm bitler aynen yazılır, o $1$'den sonraki tüm bitler terslenir.

### 2'ye Tümleyen ile Çıkarma İşlemi: $A - B = A + (-B)$
- $B$ sayısının 2'ye tümleyeni alınır ve $A$ ile toplanır.
- Eğer toplama sonucunda en soldan bir **elde (carry)** çıkarsa, bu elde ihmal edilir (sonuç pozitiftir).
- Elde çıkmazsa sonuç negatiftir ve sonucun gerçek büyüklüğünü görmek için tekrar 2'ye tümleyeni alınır.

---

## 4. Adım Adım Çözümlü Örnek Sorular

### Soru 1: Decimal $\rightarrow$ Binary ve Hexadecimal Dönüşümü
**Soru:** $(53.625)_{10}$ sayısını ikili (Binary) ve onaltılı (Hexadecimal) tabana dönüştürünüz.

**Çözüm:**
1. **Tam Kısım ($53$):** Ardışık bölme:
   - $53 / 2 = 26$ (Kalan: $1$)
   - $26 / 2 = 13$ (Kalan: $0$)
   - $13 / 2 = 6$ (Kalan: $1$)
   - $6 / 2 = 3$ (Kalan: $0$)
   - $3 / 2 = 1$ (Kalan: $1$)
   - $1 / 2 = 0$ (Kalan: $1$)
   - Sondan başa yazılır: $(110101)_2$

2. **Kesirli Kısım ($0.625$):** Ardışık çarpma:
   - $0.625 \times 2 = 1.25$ (Tam kısım: $1$)
   - $0.25 \times 2 = 0.5$ (Tam kısım: $0$)
   - $0.5 \times 2 = 1.0$ (Tam kısım: $1$)
   - Yukarıdan aşağı yazılır: $(.101)_2$

- **Binary Sonucu:** $(53.625)_{10} = \mathbf{(110101.101)_2}$

3. **Hexadecimal Dönüşümü:**
   Binary sonucu virgülden 4'erli gruplayalım (eksik yerlere sıfır eklenir):
   - Tam kısım: $0011 \ 0101 \rightarrow 3 \ 5$
   - Kesirli kısım: $1010 \rightarrow \text{A}$
   - **Hexadecimal Sonucu:** $\mathbf{(35.\text{A})_{16}}$

---

### Soru 2: Binary $\rightarrow$ Decimal, Octal ve Hexadecimal Dönüşümü
**Soru:** $(11011010.1011)_2$ sayısını Decimal, Octal ve Hexadecimal tabanlara dönüştürünüz.

**Çözüm:**
1. **Hexadecimal'e (4'lü gruplama):**
   - Tam kısım: $\underbrace{1101}_{\text{D}} \ \underbrace{1010}_{\text{A}}$
   - Kesirli kısım: $\underbrace{1011}_{\text{B}}$
   - Sonuç: $\mathbf{(\text{DA}.\text{B})_{16}}$

2. **Octal'a (3'lü gruplama):**
   - Tam kısım: $\underbrace{011}_{3} \ \underbrace{011}_{3} \ \underbrace{010}_{2}$
   - Kesirli kısım: $\underbrace{101}_{5} \ \underbrace{100}_{4}$
   - Sonuç: $\mathbf{(332.54)_8}$

3. **Decimal'e:**
   Hex üzerinden çevirmek daha pratiktir:
   $$\text{DA}.\text{B}_{16} = 13 \cdot 16^1 + 10 \cdot 16^0 + 11 \cdot 16^{-1} = 208 + 10 + \frac{11}{16} = 218 + 0.6875 = \mathbf{(218.6875)_{10}}$$

---

### Soru 3: Herhangi İki Taban Arasında Dönüşüm
**Soru:** $(342)_5$ sayısını 7'lik tabana dönüştürünüz.

**Çözüm:**
Farklı iki taban arasında geçiş için önce 10'luk tabana gidilir:
1. **5'lik tabandan 10'luk tabana:**
   $$(342)_5 = (3 \cdot 5^2) + (4 \cdot 5^1) + (2 \cdot 5^0) = 75 + 20 + 2 = (97)_{10}$$

2. **10'luk tabandan 7'lik tabana (Ardışık bölme):**
   - $97 / 7 = 13$ (Kalan: $6$)
   - $13 / 7 = 1$ (Kalan: $6$)
   - $1 / 7 = 0$ (Kalan: $1$)
   - Sondan başa kalanlar: $\mathbf{(166)_7}$

---

### Soru 4: 2'ye Tümleyen ile Çıkarma ve İşaret Analizi
**Soru:** 8-bit işaretli ikili sistemde $X = (38)_{10}$ ve $Y = (54)_{10}$ veriliyor. 2'ye tümleyen aritmetiği kullanarak $X - Y$ işlemini gerçekleştiriniz.

**Çözüm:**
1. **Sayıların 8-bit ikili karşılıkları:**
   - $X = 38 = (00100110)_2$
   - $Y = 54 = (00110110)_2$

2. **$-Y$ sayısını bulmak (2'ye Tümleyen alma):**
   - $Y$ nin 1'e tümleyeni: $11001001$
   - $+1$ ekleyelim:
     $$11001001 + 1 = 11001010_2 \quad (-54)$$

3. **$X + (-Y)$ Toplaması:**
   $$\begin{array}{r@{\quad}l}
     00100110 & (38) \\
   + 11001010 & (-54) \\
   \hline
     11110000 &
   \end{array}$$

4. **Sonucun Değerlendirilmesi:**
   - Elde (carry) oluşmadı. MSB biti $1$ olduğundan sonuç **negatiftir**.
   - Gerçek büyüklüğü bulmak için sonucun tekrar 2'ye tümleyeni alınır:
     - 1'e tümleyen: $00001111$
     - $+1$: $00010000_2 = (16)_{10}$
   - Dolayısıyla sonuç: $\mathbf{-(16)_{10}}$ (Doğrulama: $38 - 54 = -16$, sonuç doğrudur).
