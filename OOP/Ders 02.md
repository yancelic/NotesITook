# OOP - Ders 02 Notları

## 1. JVM (Java Virtual Machine) Mimarisi
JVM temel olarak 3 ana birimden oluşur:

1. **Class Loader (Sınıf Yükleyici):**
   - Derlenmiş `.class` (bytecode) dosyalarını çalışma zamanında belleğe yükler.

2. **Bytecode Verifier (Bayt Kod Doğrulayıcı):**
   - Java uygulaması derlendiğinde doğrudan çalıştırılabilir (executable) makine kodu yerine **bytecode** üretilir.
   - Belleğe yüklenen bytecode'ları inceleyerek tür bilgilerini doğrular, parametre tiplerini denetler ve güvenlik kısıtlamalarını kontrol eder.

3. **Interpreter (Yorumlayıcı):**
   - Bytecode'ları çalıştırıldığı platforma/işlemciye (CPU) özel makine kodlarına dönüştürerek satır satır yorumlar.
   - Platform bağımsızlığı (*Write Once, Run Anywhere*) bu yapı sayesinde sağlanır.

---

## 2. Java Temel Kuralları ve Sözdizimi

- **Sınıf Zorunluluğu:** Metot, fonksiyon veya değişken; tanımlanan her şey **bir sınıfın içinde** olmak zorundadır.
- **Dosya ve Public Sınıf Kuralı:** Aynı dosyada birden fazla sınıf bulunabilir; ancak **yalnızca 1 tanesi `public` olabilir** ve bu sınıfın adı dosya adıyla aynı olmalıdır.
- **Main Metodu:** Çalıştırılabilir her Java uygulamasında başlangıç noktası olarak en az bir `main` metodu bulunmalıdır.
- **Veri Tipleri:** Primitive (ilkel) türler hariç her şey bir sınıftır (referans tiptir).
- **String ve `+` Operatörü:** `+` operatörü sayılarda toplama yaparken, bir sınıf olan `String` ile kullanıldığında metinleri birleştirmeye yarar.
- **Fonksiyon Çağrıları:** Parametreli herhangi bir fonksiyon çağrılırken beklenen argümanlarla çağrılmak zorundadır.

---

## 3. Sınıf (Class) ve Nesne (Object) Kavramı

Bir sınıfın temel bileşenleri:
$$\text{Sınıf} = \text{Veri (Attribute / Nitelikler)} + \text{Davranış (Method / Metotlar)}$$

| Kavram | Açıklama | Bellek Durumu |
| :--- | :--- | :--- |
| **Sınıf (Class)** | Bütün alt nesnelerin ortak özellik ve davranışlarını ifade eden soyut bir tanımdır / şablondur. | Sınıf kodu hariç bellekte yer işgal etmez. |
| **Nesne (Object)** | Sınıftan türetilmiş, değerleri belirlenmiş, davranışları somutlaşmış ve biricik kimliği olan varlıktır. | Fiziksel olarak vardır; **Heap** belleğinde saklanır ve her nesnenin kendine ait bir bellek alanı bulunur. |

> **Örnek:** `Şekil` bir sınıf (class) ise; ondan türetilen `Daire`, `Üçgen`, `Kare` birer nesnedir.

### Sınıf Tanımlama ve Nesne Üretme (Sözdizimi)
Java'da nesne üretilirken mutlaka **`new`** anahtar kelimesi kullanılır:

```java
// Sınıf Tanımı (Şablon)
class Vakit {
    int saat;     // Attribute (Veri)
    int dakika;
}

// Nesne Oluşturma (Heap belleğinde yer açar)
Vakit vkt = new Vakit();
```

- **`Vakit`**: Referans tipi / Sınıf adı.
- **`vkt`**: Referans değişkeni (Stack'te tutulur, Heap'teki nesneyi işaret eder).
- **`new`**: Heap belleğinde nesne için yeni bir fiziksel alan ayırır.
- **`Vakit()`**: Yapıcı metot (Constructor) çağrısı.

---

## 4. `static` Kavramı ve Erişim Belirteçleri

- **`static` Belirteci:**
  - Bir fonksiyon veya değişken `static` tanımlanırsa nesne oluşturmadan doğrudan **sınıf adıyla** her yerden erişilebilir.
  - `static` bir alan bir nesne tarafından değiştirilirse, aynı koddaki **tüm nesneler için bu değer değişir** (ortak bellek paylaşımı).
- **Erişim Belirteçleri (Access Modifiers):**
  - `public`, `protected`, `default` (paket düzeyi) ve `private`.
  - *(Detayları Kapsülleme / Encapsulation konusunda işlenecektir).*

---

## 5. Kalıtım ve Alt Sınıflar (Inheritance / Subclass)

- **Temel Mantık:**
  - Bir sınıf daha fazla detay aldıkça alt sınıf (subclass) sayısı ve hiyerarşisi artar.
  - Alt sınıf (subclass), üst sınıftan (superclass) veri ve özellikleri devralabilir (okuyabilir).
  - Her alt sınıf; üst sınıfa kıyasla **daha geniş/spesifik** özelliklere, aynı seviyedeki diğer alt sınıflardan ise **farklı** özelliklere sahiptir.
  - **Temel Tasarım Kuralı:** Alt sınıfta yalnızca üst sınıfta var olmayan (farklılaşan) yeni özellik ve davranışlar tanımlanmalıdır.

### Hiyerarşi Örnekleri

1. **Karınca Örneği:**
   - **Üst Sınıf:** `Karınca`
   - **Alt Sınıf:** `Kanatlı Karınca` *(Üst sınıfa ek olarak kanat özelliği bulunur).*

2. **Araç Hiyerarşisi:**
   - **Üst Sınıf:** `Araç`
     - Alt sınıflar: `Otobüs`, `Kamyon`, `Uçak`, `Gemi`, `Otomobil`
   - **Otomobilin Alt Sınıfları:**
     - `Kartal`, `Doğan`, `Şahin`, `TOGG` *(Bunlar hem Aracın hem de Otomobilin alt sınıflarıdır).*
   - **Şahinin Alt Sınıfları:**
     - `Kırmızı Şahin`, `Doğan Görünümlü Şahin`

---

> [!TODO] Kişisel Pratik
> - [ ] Sınıf ve nesneleri kullanarak bir alan hesabı uygulaması yap.




