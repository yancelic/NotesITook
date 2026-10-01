---
title: "Mantık Devreleri 02 - Sayı Sistemleri ve Taban Dönüşümleri"
tags:
  - mantik-devreleri
  - sayi-sistemleri
  - binary
  - octal
  - decimal
  - hexadecimal
  - taban-donusumleri
  - msb
  - lsb
date: 2026-09-28
---
2855
> 🧭 **Ders Akışı:** [[Mantık Devreleri 01|⬅️ 01 - Analog ve Dijital Sistemler]] ➔ **[02 - Sayı Sistemleri ve Taban Dönüşümleri]**

---

# 🔢 Mantık Devreleri 02 - Sayı Sistemleri ve Taban Dönüşümleri

> [!WARNING] Sınav Uyarısı
> **Hoca sayı sistemlerini kesinlikle sınavda soracağını belirtti!** 
> Özellikle sayı çözümleme mantığı, iki yönlü taban dönüşümleri ve virgüllü (kesirli) sayılarda basamak hesapları üzerinde mutlaka durulmalıdır.

---

## 1. Sayı Sistemlerinin Temel Mantığı ve Basamak Çözümleme

Dijital sistemlerde veriler farklı sayı tabanları ile temsil edilir. Bir sayının değeri, basamaklarındaki rakamların **konumsal ağırlığına (positional notation)** göre hesaplanır.

### 📐 Genel Çözümleme Formülü
Tabanı $r$ olan bir sayının basamak açılımı:

$$N_r = d_n r^n + d_{n-1} r^{n-1} + \dots + d_1 r^1 + d_0 r^0 + d_{-1} r^{-1} + d_{-2} r^{-2} + \dots$$

- $r$: Sayı tabanı (radix / base)
- $d$: İlgili basamaktaki rakam (digit)
- Virgülün solundaki tam kısım için üsler: $0, 1, 2, 3 \dots$ şeklinde pozitif artar.
- Virgülün sağındaki kesirli kısım için üsler: $-1, -2, -3 \dots$ şeklinde negatif azalır.

---

### 🔹 Onluk (Decimal - Taban 10) Çözümleme Örneği: `1907`

| Basamak | Rakam | Basamak Adı | Ağırlık ($10^n$) | Değer |
| :--- | :---: | :--- | :---: | :--- |
| **0. Basamak** | $7$ | Birler Basamağı | $10^0 = 1$ | $7 \times 10^0 = 7$ |
| **1. Basamak** | $0$ | Onlar Basamağı | $10^1 = 10$ | $0 \times 10^1 = 0$ |
| **2. Basamak** | $9$ | Yüzler Basamağı | $10^2 = 100$ | $9 \times 10^2 = 900$ |
| **3. Basamak** | $1$ | Binler Basamağı | $10^3 = 1000$ | $1 \times 10^3 = 1000$ |

$$\text{Toplam: } (1 \times 10^3) + (9 \times 10^2) + (0 \times 10^1) + (7 \times 10^0) = 1000 + 900 + 0 + 7 = 1907$$

> [!NOTE] Kural
> Başka bir sayı sistemi verilse dahi mantık aynıdır; sadece $10$ yerine o sistemin taban değeri ($r$) yazılır.

---

### 🔹 İkili (Binary - Taban 2) Çözümleme Örneği: `(1101.101)₂`

Hem tam sayıyı hem de virgüllü (kesirli) kısmı kapsayan 2'li taban çözümlemesi:

$$(1101.101)_2 = ?_{10}$$

1. **Tam Kısım ($1101_2$):**
   - $1 \times 2^3 = 8$
   - $1 \times 2^2 = 4$
   - $0 \times 2^1 = 0$
   - $1 \times 2^0 = 1$
   - Tam kısım toplamı: $8 + 4 + 0 + 1 = 13$

2. **Kesirli Kısım ($0.101_2$):**
   - $1 \times 2^{-1} = 1 \times 0.5 = 0.5$
   - $0 \times 2^{-2} = 0 \times 0.25 = 0$
   - $1 \times 2^{-3} = 1 \times 0.125 = 0.125$
   - Kesirli kısım toplamı: $0.5 + 0 + 0.125 = 0.625$

3. **Sonuç:**
   $$(1101.101)_2 = 13 + 0.625 = (13.625)_{10}$$

---

## 2. Mantık Devrelerinde Kullanılan Temel Sayı Sistemleri

| Sayı Sistemi | Taban ($r$) | Kullanılan Semboller | Tanım / Kullanım Alanı |
| :--- | :---: | :--- | :--- |
| **Binary** | $2$ | $0, 1$ | Mantık devrelerinin temel dili (Var/Yok, 5V/0V). |
| **Octal** | $8$ | $0, 1, 2, 3, 4, 5, 6, 7$ | 3 bitlik ikili grupları kısaltmak için kullanılır ($2^3 = 8$). |
| **Decimal** | $10$ | $0, 1, 2, 3, 4, 5, 6, 7, 8, 9$ | Günlük hayatta kullandığımız standart sistem. |
| **Hexadecimal** | $16$ | $0 - 9$ ve $\text{A, B, C, D, E, F}$ | 4 bitlik grupları temsil eder ($2^4 = 16$). Bellek adreslemede kullanılır. |

> [!TIP] Hexadecimal Harf Karşılıkları
> Hexadecimal sistemde 9'dan büyük rakamlar harflerle ifade edilir:
> $\text{A} = 10, \quad \text{B} = 11, \quad \text{C} = 12, \quad \text{D} = 13, \quad \text{E} = 14, \quad \text{F} = 15$

---

### 📋 0 - 15 Arası Sayı Sistemleri Karşılaştırma Tablosu

| Decimal (10'luk) | Binary (2'lik - 4 Bit) | Octal (8'lik) | Hexadecimal (16'lık) |
| :---: | :---: | :---: | :---: |
| **0** | `0000` | $0$ | $\text{0}$ |
| **1** | `0001` | $1$ | $\text{1}$ |
| **2** | `0010` | $2$ | $\text{2}$ |
| **3** | `0011` | $3$ | $\text{3}$ |
| **4** | `0100` | $4$ | $\text{4}$ |
| **5** | `0101` | $5$ | $\text{5}$ |
| **6** | `0110` | $6$ | $\text{6}$ |
| **7** | `0111` | $7$ | $\text{7}$ |
| **8** | `1000` | $10$ | $\text{8}$ |
| **9** | `1001` | $11$ | $\text{9}$ |
| **10** | `1010` | $12$ | $\mathbf{A}$ |
| **11** | `1011` | $13$ | $\mathbf{B}$ |
| **12** | `1100` | $14$ | $\mathbf{C}$ |
| **13** | `1101` | $15$ | $\mathbf{D}$ |
| **14** | `1110` | $16$ | $\mathbf{E}$ |
| **15** | `1111` | $17$ | $\mathbf{F}$ |

---

### 📊 `25` Sayısının Farklı Tabanlardaki Görünümü

| Sistem | Gösterim | Dönüşüm Özeti |
| :--- | :---: | :--- |
| **Decimal (Onluk)** | $(25)_{10}$ | $2 \times 10^1 + 5 \times 10^0 = 25$ |
| **Binary (İkili)** | $(11001)_2$ | $16 + 8 + 0 + 0 + 1 = 25$ |
| **Octal (Sekizli)** | $(31)_8$ | $3 \times 8^1 + 1 \times 8^0 = 24 + 1 = 25$ |
| **Hexadecimal (Onaltılık)** | $(19)_{16}$ | $1 \times 16^1 + 9 \times 16^0 = 16 + 9 = 25$ |

---

## 3. İki Yönlü Taban Dönüşümleri (Adım Adım)

### 3.1. Decimal $\leftrightarrow$ Binary Dönüşümü

#### A) Decimal $\to$ Binary: Sürekli 2'ye Bölme Yöntemi
$(25)_{10}$ sayısını 2'liğe dönüştürelim:

1. $25 \div 2 = 12$ kalan: **$1$** (En anlamsız bit - LSB)
2. $12 \div 2 = 6$ kalan: **$0$**
3. $6 \div 2 = 3$ kalan: **$0$**
4. $3 \div 2 = 1$ kalan: **$1$**
5. $1 \div 2 = 0$ kalan: **$1$** (En anlamlı bit - MSB)

> Kalanlar **aşağıdan yukarıya (sondan başa)** doğru okunur:
> $$(25)_{10} = (11001)_2$$

#### B) Binary $\to$ Decimal: Ağırlıklı Toplama Yöntemi
$(11001)_2$ sayısını onluk sisteme çevirelim:

$$(11001)_2 = (1 \times 2^4) + (1 \times 2^3) + (0 \times 2^2) + (0 \times 2^1) + (1 \times 2^0)$$
$$= 16 + 8 + 0 + 0 + 1 = (25)_{10}$$

---

### 3.2. Decimal $\leftrightarrow$ Octal Dönüşümü

#### A) Decimal $\to$ Octal: Sürekli 8'e Bölme Yöntemi
$(25)_{10}$ sayısını 8'lik sisteme dönüştürelim:

1. $25 \div 8 = 3$ kalan: **$1$**
2. $3 \div 8 = 0$ kalan: **$3$**

> Kalanlar aşağıdan yukarıya yazılır:
> $$(25)_{10} = (31)_8$$

#### B) Octal $\to$ Decimal: Ağırlıklı Toplama Yöntemi
$(31)_8$ sayısını onluk sisteme çevirelim:

$$(31)_8 = (3 \times 8^1) + (1 \times 8^0) = 24 + 1 = (25)_{10}$$

---

### 3.3. Decimal $\leftrightarrow$ Hexadecimal Dönüşümü

#### A) Decimal $\to$ Hexadecimal: Sürekli 16'ya Bölme Yöntemi

**Örnek 1: $(25)_{10}$ sayısı:**
1. $25 \div 16 = 1$ kalan: **$9$**
2. $1 \div 16 = 0$ kalan: **$1$**

> Aşağıdan yukarıya:
> $$(25)_{10} = (19)_{16}$$

**Örnek 2: Harf içeren örnek: $(175)_{10}$ sayısı:**
1. $175 \div 16 = 10$ kalan: **$15$** ($\text{Hex karşılığı: F}$)
2. $10 \div 16 = 0$ kalan: **$10$** ($\text{Hex karşılığı: A}$)

> Aşağıdan yukarıya:
> $$(175)_{10} = (\text{AF})_{16}$$

#### B) Hexadecimal $\to$ Decimal: Ağırlıklı Toplama Yöntemi

**Örnek 1: $(19)_{16}$ sayısı:**
$$(19)_{16} = (1 \times 16^1) + (9 \times 16^0) = 16 + 9 = (25)_{10}$$

**Örnek 2: $(\text{AF})_{16}$ sayısı:**
$$(\text{AF})_{16} = (\text{A} \times 16^1) + (\text{F} \times 16^0) = (10 \times 16) + (15 \times 1) = 160 + 15 = (175)_{10}$$

---

### 3.4. Pratik Grup Dönüşümleri (Kısayol Yöntemleri)

*Mantık devrelerinde Binary, Octal ve Hexadecimal arasındaki dönüşümlerde onluk tabana geçmeye gerek yoktur. Doğrudan bit gruplamasıyla pratik şekilde dönüştürülür:*

#### 1. Binary $\leftrightarrow$ Octal ($8 = 2^3$)
Her 8'lik (Octal) basamak, **tam olarak 3 bitlik** bir ikili (binary) sayıya karşılık gelir:

| Octal Basamak | $0$ | $1$ | $2$ | $3$ | $4$ | $5$ | $6$ | $7$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **3-Bit Binary** | `000` | `001` | `010` | `011` | `100` | `101` | `110` | `111` |

##### 📌 Örnek Soru: $(34507{,}0216)_8$ Sayısını İkili (Binary) Sisteme Dönüştürme
Her bir basamağı 3 bitlik ikili bloklara ayıralım:

1. **Tam Kısım ($34507_8$):**
   - $3 \implies \mathbf{011}$
   - $4 \implies \mathbf{100}$
   - $5 \implies \mathbf{101}$
   - $0 \implies \mathbf{000}$
   - $7 \implies \mathbf{111}$
   - *Birleşimi:* $011 \ 100 \ 101 \ 000 \ 111$

2. **Kesirli Kısım ($,0216_8$):**
   - $0 \implies \mathbf{000}$
   - $2 \implies \mathbf{010}$
   - $1 \implies \mathbf{001}$
   - $6 \implies \mathbf{110}$
   - *Birleşimi:* $,000 \ 010 \ 001 \ 110$

3. **Sonuç:**
   $$(34507{,}0216)_8 = (011100101000111{,}000010001110)_2$$

> [!TIP] Sadeleştirme Notu
> Tam kısmın en solundaki gereksiz sıfır ($0$) ile kesirli kısmın en sağındaki gereksiz sıfır ($0$) isteğe bağlı olarak yazılmayabilir:
> $$(34507{,}0216)_8 = (11100101000111{,}00001000111)_2$$

---

#### 2. Binary $\leftrightarrow$ Hexadecimal ($16 = 2^4$)
Her 16'lık basamak için **4'er bitlik** gruplar oluşturulur. Gruplama kuralı çok önemlidir:
- **Tam kısım:** Virgülün solundan başlanarak **sağdan sola** doğru 4'erli gruplanır (Eksik kalırsa en sola `0` eklenir).
- **Kesirli kısım:** Virgülün sağından başlanarak **soldan sağa** doğru 4'erli gruplanır (Eksik kalırsa en sağa `0` eklenir).

##### 📌 Örnek Soru: Önceki Örnekte Bulunan İkili Sayıyı Hexadecimal'e (16'lığa) Çevirme
Bulduğumuz ikili sayı: $(011100101000111{,}000010001110)_2$

1. **Tam Kısım Gruplaması (Virgülden sola doğru 4'erli):**
   - Sayı: `011100101000111` (15 bit)
   - 4'ün katı olması için sol tarafına bir adet `0` eklenir (16 bit yapılır):
   - `0011` | `1001` | `0100` | `0111`
   - Her grubun Hex karşılığı:
     - `0011` $\implies 2 + 1 = \mathbf{3}$
     - `1001` $\implies 8 + 1 = \mathbf{9}$
     - `0100` $\implies 4 = \mathbf{4}$
     - `0111` $\implies 4 + 2 + 1 = \mathbf{7}$
   - *Tam kısım:* $\mathbf{3947}$

2. **Kesirli Kısım Gruplaması (Virgülden sağa doğru 4'erli):**
   - Sayı: `,000010001110` (12 bit - zaten 4'ün tam katı)
   - `0000` | `1000` | `1110`
   - Her grubun Hex karşılığı:
     - `0000` $\implies \mathbf{0}$
     - `1000` $\implies \mathbf{8}$
     - `1110` $\implies 8 + 4 + 2 + 0 = 14 \implies \mathbf{E}$
   - *Kesirli kısım:* $\mathbf{,08E}$

3. **Sonuç:**
   $$(011100101000111{,}000010001110)_2 = (3947{,}08\text{E})_{16}$$

> [!NOTE] Özet Bağlantı
> Böylece tek bir örnek üzerinden 8'likten 16'lığa pratik geçiş yapılmış oldu:
> $$(34507{,}0216)_8 = (011100101000111{,}000010001110)_2 = (3947{,}08\text{E})_{16}$$

---

## 4. Virgüllü (Kesirli) Sayıların Taban Dönüşümü

Virgüllü bir sayıyı onluk tabandan başka bir tabana çevirirken:
- **Tam Kısım:** Sürekli **bölünür**.
- **Kesirli Kısım:** Sürekli taban ile **çarpılır**. Çarpım sonucunun tam kısmı basamak olarak alınır, kalan kesir tekrar çarpılır.

### 🔹 Tam Sonlanan Örnek: $(0.625)_{10} \to (?)_2$
1. $0.625 \times 2 = \mathbf{1}.25 \implies$ Tam kısım: **$1$**, kalan: $0.25$
2. $0.25 \times 2 = \mathbf{0}.50 \implies$ Tam kısım: **$0$**, kalan: $0.50$
3. $0.50 \times 2 = \mathbf{1}.00 \implies$ Tam kısım: **$1$**, kalan: $0.00$ (İşlem bitti)

> Çarpma işleminde sonuçlar **yukarıdan aşağıya (baştan sona)** yazılır:
> $$(0.625)_{10} = (0.101)_2$$

---

### ⚠️ Devirli / Sonsuz Kesirler ve Sınav İpucu

> [!IMPORTANT] Hoca Uyarısı / Sınav Notu
> Eğer virgüllü bir sayıyı dönüştürürken çarpma işlemlerinden sonra kesir sıfırlanmıyorsa (sonsuz devrediyorsa veya tam sayı elde edilmiyorsa), **uzun süre devam edip sınavda vakit kaybetmeyin**.
> Hoca, belirli bir basamak hassasiyetine (genellikle virgülden sonra **3 veya 4 basamağa**) ulaştıktan sonra işlemin kesilip bırakılması gerektiğini belirtti.

#### Devreden Sayı Örneği: $(0.2)_{10} \to (?)_2$
1. $0.2 \times 2 = \mathbf{0}.4 \implies$ Basamak: **$0$**
2. $0.4 \times 2 = \mathbf{0}.8 \implies$ Basamak: **$0$**
3. $0.8 \times 2 = \mathbf{1}.6 \implies$ Basamak: **$1$**
4. $0.6 \times 2 = \mathbf{1}.2 \implies$ Basamak: **$1$**
5. $0.2 \times 2 = \mathbf{0}.4 \dots$ *(Sayı başa döndü ve devretmeye başladı)*

> Sınavda burada durulur ve yaklaşık değer olarak yazılır:
> $$(0.2)_{10} \approx (0.0011)_2$$


---

## 5. Bit Kavramları: MSB (Most Significant Bit) ve LSB (Least Significant Bit)

Dijital elektronikte ve ikili (binary) sayı sisteminde her bir `0` veya `1` değerine **bit** (*Binary Digit*) denir. Çok basamaklı ikili sayılarda basamakların sayısal büyüklüğe katkısı (konumsal ağırlığı) birbirinden farklıdır:

| Kısaltma | İngilizce Açılımı | Türkçe Karşılığı | Konum | Tanım ve Özellik |
| :---: | :--- | :--- | :---: | :--- |
| **MSB** | **M**ost **S**ignificant **B**it | En Anlamlı / En Değerli Bit | **En Sol** | Sayısal ağırlığı ($2^n$) en büyük olan bittir. Sayının büyüklüğünü en çok etkileyen basamaktır. |
| **LSB** | **L**east **S**ignificant **B**it | En Anlamsız / En Az Değerli Bit | **En Sağ** | Sayısal ağırlığı ($2^0 = 1$) en küçük olan bittir. Tam sayılarda sayının **tek mi çift mi** olduğunu belirler. |

---

### 🔹 Değer Örneği Üzerinde İnceleme: `(1101010)₂`

7 bitlik `1101010` ikili sayısını ele alalım:

```text
    MSB                                       LSB
 (En Sol)                                  (En Sağ)
    │                                         │
    ▼                                         ▼
  ┌───┬───┬───┬───┬───┬───┬───┐
  │ 1 │ 1 │ 0 │ 1 │ 0 │ 1 │ 0 │
  └───┴───┴───┴───┴───┴───┴───┘
    ▲   ▲   ▲   ▲   ▲   ▲   ▲
    │   │   │   │   │   │   └─► Bit 0: Ağırlık = 2⁰ = 1  (Değer: 0 × 1  = 0)
    │   │   │   │   │   └─────► Bit 1: Ağırlık = 2¹ = 2  (Değer: 1 × 2  = 2)
    │   │   │   │   └─────────► Bit 2: Ağırlık = 2² = 4  (Değer: 0 × 4  = 0)
    │   │   │   └─────────────► Bit 3: Ağırlık = 2³ = 8  (Değer: 1 × 8  = 8)
    │   │   └─────────────────► Bit 4: Ağırlık = 2⁴ = 16 (Değer: 0 × 16 = 0)
    │   └─────────────────────► Bit 5: Ağırlık = 2⁵ = 32 (Değer: 1 × 32 = 32)
    └─────────────────────────► Bit 6: Ağırlık = 2⁶ = 64 (Değer: 1 × 64 = 64)
```

#### Basamak Ağırlık Tablosu ve Onluk Karşılığı:

| Bit Konumu | Bit İndeksi | Bit Değeri | Basamak Ağırlığı ($2^n$) | Katkı Değeri | Rolü |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **En Sol Basamak** | $b_6$ | **$1$** | $2^6 = 64$ | $1 \times 64 = 64$ | 🌟 **MSB (Most Significant Bit)** |
| 5. Basamak | $b_5$ | **$1$** | $2^5 = 32$ | $1 \times 32 = 32$ | Ara basamak |
| 4. Basamak | $b_4$ | **$0$** | $2^4 = 16$ | $0 \times 16 = 0$ | Ara basamak |
| 3. Basamak | $b_3$ | **$1$** | $2^3 = 8$ | $1 \times 8 = 8$ | Ara basamak |
| 2. Basamak | $b_2$ | **$0$** | $2^2 = 4$ | $0 \times 4 = 0$ | Ara basamak |
| 1. Basamak | $b_1$ | **$1$** | $2^1 = 2$ | $1 \times 2 = 2$ | Ara basamak |
| **En Sağ Basamak** | $b_0$ | **$0$** | $2^0 = 1$ | $0 \times 1 = 0$ | 🎯 **LSB (Least Significant Bit)** |

$$\text{Toplam Değer: } 64 + 32 + 0 + 8 + 0 + 2 + 0 = (106)_{10}$$

> [!TIP] Pratik Çıkarım: Çift / Tek Kontrolü
> LSB basamağı $0$ olduğu için bu sayı bir **çift sayıdır** ($106$). Eğer LSB $1$ olsaydı sayı tek olacaktı.

---

### ⚠️ Kritik Kontrol: Bölme Yönteminde İlk Kalan MSB midir, LSB midir?

> [!CAUTION] Sık Düşülen Yanılgı ve Doğrusu
> **Yanılgı:** *"Sürekli bölme yaparken ilk böldüğümüzde sayının en başındaki basamağı (MSB) buluruz."* ❌ **(YANLIŞ)**  
> **Doğrusu:** **İlk bölmede elde edilen İLK KALAN her zaman LSB'dir!** ✅  
> **En son elde edilen kalan (veya son bölüm) ise MSB'dir!** ✅

#### 🧠 Matematiksel Mantığı Neden Böyledir?
Onluk bir sayıyı (örneğin $106$ sayısını) sürekli 2'ye böldüğümüz açılımı düşünelim:

$$N = b_6 \cdot 2^6 + b_5 \cdot 2^5 + b_4 \cdot 2^4 + b_3 \cdot 2^3 + b_2 \cdot 2^2 + b_1 \cdot 2^1 + \mathbf{b_0 \cdot 2^0}$$

1. $2^1, 2^2, 2^3 \dots$ terimlerinin hepsi $2$'nin tam katıdır ve $2$'ye kalansız bölünür.
2. Sayıyı ilk kez 2'ye böldüğümüzde kalan ($N \pmod 2$), doğrudan **yalnızca $b_0$ (yani $2^0$) katsayısını** verir. Bu da **en sağdaki basamak olan LSB'dir**.
3. Bölüm sonucu elde edilen sayı artık $b_0$'dan arınmıştır; onu tekrar 2'ye böldüğümüzde bu defa $b_1$ ($2^1$) katsayısı kalan olarak açığa çıkar.
4. Bu işlem zincirinde sayıyı böle böle en yüksek basamağa doğru ilerleriz. Artık 2'ye bölünemeyecek en son kalan ise **en yüksek ağırlıklı basamak olan MSB'dir**.

#### 📋 $(106)_{10}$ Sayısının Bölme İşlemi Adımları:

$$\begin{array}{rll}
106 \div 2 = 53 & \text{kalan: } \mathbf{0} & \longleftarrow \mathbf{1.\text{ Kalan } \to \text{LSB (En sağdaki bit, } 2^0)} \\
53 \div 2 = 26 & \text{kalan: } \mathbf{1} & \longleftarrow 2.\text{ Kalan } (2^1) \\
26 \div 2 = 13 & \text{kalan: } \mathbf{0} & \longleftarrow 3.\text{ Kalan } (2^2) \\
13 \div 2 = 6  & \text{kalan: } \mathbf{1} & \longleftarrow 4.\text{ Kalan } (2^3) \\
6 \div 2 = 3   & \text{kalan: } \mathbf{0} & \longleftarrow 5.\text{ Kalan } (2^4) \\
3 \div 2 = 1   & \text{kalan: } \mathbf{1} & \longleftarrow 6.\text{ Kalan } (2^5) \\
1 \div 2 = 0   & \text{kalan: } \mathbf{1} & \longleftarrow \mathbf{Son\text{ Kalan } \to \text{MSB (En soldaki bit, } 2^6)}
\end{array}$$

> [!NOTE] Özet Kural
> Kalanları ikili sayı olarak yazarken **aşağıdan yukarıya (sondan başa)** doğru yazarız:
> 
> $$\underbrace{\mathbf{1}}_{\text{MSB}} \ \mathbf{1} \ \mathbf{0} \ \mathbf{1} \ \mathbf{0} \ \mathbf{1} \ \underbrace{\mathbf{0}}_{\text{LSB}} \implies (1101010)_2$$

---

### 🔄 Karşılaştırma Özeti: Bölme vs. Çarpma Yöntemi

| İşlem Türü               | Kullanıldığı Durum        | İlk Bulunan Değer  | Son Bulunan Değer  |              Yazılış Yönü              |
| :----------------------- | :------------------------ | :----------------: | :----------------: | :------------------------------------: |
| **Sürekli 2'ye Bölme**   | **Tam Sayı** dönüşümü     |  **LSB** ($2^0$)   |  **MSB** ($2^n$)   | **Aşağıdan Yukarıya** (Sondan başa) ⬆️ |
| **Sürekli 2 ile Çarpma** | **Kesirli Sayı** dönüşümü | **MSB** ($2^{-1}$) | **LSB** ($2^{-m}$) | **Yukarıdan Aşağıya** (Baştan sona) ⬇️ |
