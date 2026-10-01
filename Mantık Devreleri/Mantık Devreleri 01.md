---
title: "Mantık Devreleri 01 - Analog ve Dijital Sistemler"
tags:
  - mantik-devreleri
  - analog
  - dijital
  - pozitif-mantik
  - negatif-mantik
  - adc-dac
date: 2026-09-28
---

> 🧭 **Ders Akışı:** [[Mantık Devreleri 00|⬅️ 00 - Ders Bilgileri]] ➔ **[01 - Analog ve Dijital Sistemler]** ➔ [[Mantık Devreleri 02|02 - Sayı Sistemleri ve Taban Dönüşümleri ➡️]]

---

# ⚡ Mantık Devreleri 01 - Analog ve Dijital Sistemler

Elektronik sistemler temel olarak iki ana kategoriye ayrılır: **Analog Sistemler** ve **Dijital (Sayısal) Sistemler**.

---

## 1. Etimoloji ve Temel Tanımlar

* **Dijital (Sayısal):**
  * Köken: Latince *"digitus"* (parmakla saymak / rakam) kelimesinden gelir.
  * **Mantık:** Kesikli (ayrık / discrete) değerlerle çalışır. Ara değerler yoktur; durum ya vardır ya yoktur (**1 veya 0**, HIGH veya LOW, Açık veya Kapalı).
* **Analog:**
  * Köken: Yunanca *"analogos"* (orantılı, benzer, süreklilik gösteren) kelimesinden gelir.
  * **Mantık:** Kesintisiz ve sürekli (continuous) sinyallerdir. Belirli bir aralıkta sonsuz sayıda farklı değer alabilir.

> [!NOTE] Günlük Hayattan Benzetme
> Bir lambayı açıp kapayan standart bir anahtar **dijital** bir sistemdir (ya yanar ya söner).
> Işığın şiddetini kademesiz olarak kısıp açabildiğimiz bir reosta/dimmer anahtarı ise **analog** bir sistemdir.

---

## 2. Analog ve Dijital Sistemlerin Karşılaştırması

| Kriter | Analog Sistemler | Dijital (Sayısal) Sistemler |
| :--- | :--- | :--- |
| **Sinyal Yapısı** | Sürekli (Continuous), zamana bağlı sonsuz değer. | Kesikli / Ayrık (Discrete), 0 veya 1 seviyeleri. |
| **Ayarlanabilirlik** | Hassas ve kademesiz ayar yapılabilir (sonsuz ara değer). | Sabit adımlı / ikili seviyelerdedir. |
| **Veri Depolama** | Zordur; zamanla kayıp ve bozulma yaşanır (kaset, plak). | Çok kolay ve kayıpsızdır (SSD, Flash, HDD vb.). |
| **Devre Boyutları** | Genellikle daha büyüktür (büyük bobin, kapasitör vb.). | Mikro/nano ölçekte entegre edilebilir (VLSI çipleri). |
| **Gürültü Bağışıklığı** | Düşüktür; çevresel elektriksel gürültü sinyali doğrudan bozar. | Yüksektir; eşik voltajı korunduğu sürece 0 ve 1 bozulmaz. |
| **Hata Tespiti & Onarımı** | Hatanın tespiti ve ayrıştırılması zordur. | Hata tespit ve düzeltme kodları (Parity, CRC, Hamming) ile çok kolaydır. |

---

## 3. Lojik (Mantık) Seviyeleri: Pozitif vs. Negatif Mantık

Dijital devrelerde ikili durumlar belirli gerilim aralıklarıyla temsil edilir.

### 🔹 Pozitif Mantık (Positive Logic) — *Standart Kullanım*
En yaygın kullanılan lojik sistemdir:
- **Mantık 1 (HIGH / Doğru):** Yüksek gerilim seviyesi (Örn: $+5\text{V}$ veya $+3.3\text{V}$)
- **Mantık 0 (LOW / Yanlış):** Düşük gerilim seviyesi (Örn: $0\text{V}$ / Toprak)

### 🔹 Negatif Mantık (Negative Logic)
Pozitif mantığın tam tersi mantık düzeyidir:
- **Mantık 1 (Aktif):** Düşük gerilim seviyesi (Örn: $0\text{V}$)
- **Mantık 0 (Pasif):** Yüksek gerilim seviyesi (Örn: $+5\text{V}$ veya negatif gerilimler $-5\text{V}$)

---

### ⏱️ Kenar Tetikleme (Edge Triggering) Mantığı
Saat sinyali (Clock - CLK) darbelerinde durum geçiş anları ikiye ayrılır:

```text
       +5V (1)        ┌──────────────┐
                      │              │
        0V (0) ───────┘              └───────
                      ▲              ▲
               Yükselen Kenar  Düşen Kenar
               (Rising Edge)   (Falling Edge)
```

1. **Yükselen Kenar (Rising Edge - Pozitif Geçiş):** Sinyalin $0$'dan $1$'e çıktığı (düşük voltajdan yüksek voltaja geçtiği) andır.
2. **Düşen Kenar (Falling Edge - Negatif Geçiş):** Sinyalin $1$'den $0$'a indiği (yüksek voltajdan düşük voltaja düştüğü) andır.

---

## 4. Analog ile Dijital Arasındaki Köprü: Dönüştürücüler

Gerçek dünya analogdur (ses, ısı, basınç, ışık). Bu verilerin mikroişlemcilerde işlenebilmesi ve tekrar dış dünyaya verilebilmesi için çeviriciler kullanılır:

* **ADC (Analog-to-Digital Converter):** Sensör veya mikrofondan gelen sürekli analog sinyali örnekleyerek `0` ve `1`lerden oluşan dijital verilere çevirir.
* **DAC (Digital-to-Analog Converter):** Dijital işlemcide hesaplanan `0` ve `1` verilerini hoparlör veya motor sürücü gibi cihazlar için analog voltaja dönüştürür.
