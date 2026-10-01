528```
public class Vakit {
    public int saat;
    public int dakika;
    public int saniye;

    public void ilerlet() {
        saniye++;
        if (saniye >= 60) {
            saniye = 0;
            dakika++;
            if (dakika >= 60) {
                dakika = 0;
                saat++;
                if (saat >= 24) {
                    saat = 0;
                }
            }
        }
    }

    public void vakitYaz() {
        System.out.printf("%02d:%02d:%02d%n", saat, dakika, saniye);
    }
}
```

```
public class VakitApp {
    public static void main(String[] args) {
        Vakit vkt = new Vakit();
        vkt.saat = 23;
        vkt.dakika = 59;
        vkt.saniye = 59;

        for (int i = 0; i < 60; i++) {
            vkt.vakitYaz();
            vkt.ilerlet();
        }
    }
}

```