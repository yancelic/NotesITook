# Lineer olmayan denklemlerin çözümü

## İkiye bölme yöntemi
ikiye bölme yöntemiyle yerleşik çözüm bulmak için prosedür yada algoritma aşağıdaki gibidir:
1) Fonksiyonun kökünü içine lana ve f(a)* f(b) * < 0 şartlarını sağlayan bir xaltindis alt = a ve xaltindis üst = b noktaları belirlenir
2) Fonksiyonun kökünün ilk tahmini: xaltindis r1 aşağıdaki fonksiyondan bulunur
3) xaltindis r1 = (xaltindis alt + x altindis üst)/2
4) fonksiyonun kökünün yeri bulunan değere göre hangi alt aralıkta olduğunu bulmak için aşağıdaki hesaplar yapılır;

- f(a) * f(xaltindis r1) < 0 ise kök (a, xaltindis r1) arasındadır. o halde yeni kök tahmini yapmak için 2. adıma dönülür
- f(xaltindis r1) * f(b) < 0 ise kök (xaltindis r1 , b) arasındadır. o halde yeni kök tahmini yapmak için 2. adıma dönülür
- f(a) * f(xaltindis r1) = 0 yada f(xaltindis r1) * f(b) = 0  kök xaltindis r1'e eşittir. hesaplamaya son verilir

Örnek: f(x) = x^3 - 2x - 5 =0 denkleminin bir kökünün ikiye bölme yöntemiyle bulunuz.

(genelde kolay 2 sayı seçip yöntemi kullanmamızı söyledi hoca, bu örneği ona göre uygulamalı çöz.)

yarıla fonksiyondaki değere bak aralığa karar ver gibisinden bir şeyler söyledi hoca. yöntemin ne olduğunu tam kavrayamadığım için anlamadım ancak örnekte bunu da kullanıcaz galiba, sınavdaa bu şekilde 4 adımla çözmemizi istiyor. Öğreneceğimiz yöntemler arasında en yavaşı ve en basiti buymuş ancak öğrendiğimiz için sınavda sorabilecğeini söyledi.

Örnek 2: f(x) = x^3 - 3 = 0 Denkleminin pozitif kökünü ikiye bölme yöntemi ile bulunuz, negatif ve pozitif kökün aralığını bulunuz.
yine 4 adımda yaklaşacağız

Hesap makinesi ile çözmeyi çalışmak gerekiyor hesap makinesinde e nasıl yapılır vb vb hepsini öğrenmek gerekir. !!!

# Sabit Nokta İterasyonu
Sabit nokta iterasyonu f(x) = 0 yapısında bir denklemi çözmek için kullanılan bir yöntemdir. Bu yöntemde denklem,
x = g(x)
biriminde tekrar yazılarak uygulanır. Yaklaşık çözüm bulmak için x = xaltindis 0 değeri g(x) fonksiyonunda yerine göre yazılark xaltindis 1 değeri bulunur, daha sonra x=xaltindis1 değeri g(x) fonksiyonunda yerine yazılarak xaltindis 2 değeri bulunur ve bu şekilde iterasyon devam ettirilir.

xaltindis 1 = g(xaltindis 0)
xaltindis 2 = g(xaltindis 1)
xaltindis3 = g(xaltindis 2)
*
*
*
*
xaltindis i+1 = g(xaltindis i)
iterasyonu ortaya çıkar =>İterasyon |g'(x)| <1 ise yakınsama mutlak olur, yani mutlaka köke doğru yaklaşır. Ancak bu şartın sağlanmadığı durumlarda köke yakınsama olabilir.

Örnek: x^3 -2x -5 = 0 denklemini göz önüne alalım. Denklemin yaklaşık kökü 2,09455 olduğundanan xaltindis 0 =1 den başlayarak kökü bulmaya çalışalım.

Çözümünü sabit nokta iterasyonu kullanarak adım adım açıklayarak yap.
Taktik: denklemin en yüksek derecesi olan kuvvetini kullanarak yalnız bırakarak denersek en hızlı şekilde bulabilirz gibisinden bir şey dedi. bu bilgiyi doğrulamamız gerek ama. (emin değilim.)

xaltindis0 = 1 değeri için mutlak bir yaklaşım elde edilceği söylenebilir. Fakat |g'(x)| <1 koşulu yeterli bir şart olsada olmayabilir. Bazen |g'(x)|>=1 koşulu olduğunda da çözüme yaklaşılabilir.

Örnek1'in çözümünün devamı?
İterasyon fonksiyonu ile kökü bulmaya çalışalım,
xaltindis i +1 = küpkök(2xaltindis i +5 )
x1
x2
x4
.
.
(buraları doldur x 7'ye kadar)
İterasyonu kesebiliriz. ünkü artık x7,x8,x9 ve diğer terimlerin ilk basamağı aynı olacaktır.

Örnek 2
x * e^0,5x + 1,2x - 5 = 0 denklemini ele alalım. Denklemin yaklaşık çözümü x = 1,5050 olduğuna göre x0 = 1 den başlayarak çözüm bulalım.