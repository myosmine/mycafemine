# MyMinerOS

**Windows bilgisayarlarında Pearl madenciliğini tek panelden yönetmek için ücretsiz yönetim uygulaması.**

MyMinerOS; internet kafeler, birden fazla bilgisayarı olan kullanıcılar ve kendi cihazlarını uzaktan yönetmek isteyenler için hazırlanmıştır. Hesabınıza bağlı istemciler oluşturabilir, cihazların bağlantı durumunu takip edebilir ve madencilik işlemini panelden başlatıp durdurabilirsiniz.

> **Bu dağıtım WildRig veya başka bir madenci yazılımı içermez.** MyMinerOS yönetim paneli ve istemci dosyalarını sağlar. Madencilik için gerekli WildRig dosyalarını geliştiricisinin indirme sayfasından ayrıca edinmeniz gerekir.

## Özellikler

- E-posta ve şifreyle üyelik ve giriş.
- Kendi Pearl cüzdan adresinizle hesabınıza özel istemci dosyaları oluşturma.
- Windows bilgisayarlarını tek panelde listeleme ve bağlantı durumlarını takip etme.
- Seçili cihazlarda veya tüm cihazlarda madenciliği başlatma ve durdurma.
- Ctrl tuşuyla birden fazla istemci seçme.
- Bilgisayar adı, IP, son bildirim ve hata bilgilerini görüntüleme.
- Paneldeki mining komutu ile WildRig işlem durumunu ayrı ayrı görüntüleme.
- Seçilen istemci için NVIDIA güç limiti, GPU hedef frekansı ve bellek frekansı ayarları.

## Gereksinimler

- Madencilik istemcisinin çalışacağı Windows bilgisayarları.
- İstemcilerin yönetim hizmetine bağlanabilmesi için internet erişimi.
- WildRig'in desteklediği ekran kartı ve uygun sürücüler.
- NVIDIA ayarlarını kullanmak için uyumlu NVIDIA ekran kartı ve gerekli sistem izinleri.
- Kendi Pearl cüzdan alım adresiniz.
- Ayrıca indirilecek WildRig dosyaları.

## Kurulum ve kullanım

### 1. MyMinerOS paketini indirin

Bu deponun **Releases / Sürümler** bölümünden madenci içermeyen MyMinerOS dağıtım paketini indirin ve ZIP'i bir klasöre çıkarın.

### 2. Hesabınızı oluşturun

Paketteki yönetim panelini açın. **Üye ol** bölümünden hesabınızı oluşturun veya mevcut hesabınızla **Giriş yap** seçeneğini kullanın.

### 3. İstemci dosyalarını oluşturun

Paneldeki **Pearl cüzdan adresi** alanına kendi cüzdanınızın alım adresini yazın ve **İstemci dosyalarını oluştur** düğmesine basın.

Bu alana yalnızca alım adresinizi girin; özel anahtar veya kurtarma kelimeleri girilmez.

### 4. WildRig'i ayrıca indirin

WildRig'i kendi geliştiricisinin yayın sayfasından edinin:

**[WildRig Multi — Resmî depo ve sürümler](https://github.com/andru-kun/wildrig-multi/releases)**

WildRig paketindeki gerekli dosyaları, oluşturduğunuz istemci klasörünün içindeki `wildrig` alt klasörüne yerleştirin. Çalıştırılabilir dosyanın yolu şu şekilde olmalıdır:

```text
istemci-klasoru/
└── wildrig/
    ├── wildrig.exe
    └── WildRig paketindeki diğer gerekli dosyalar
```

WildRig, ayrı geliştirilen bir üçüncü taraf yazılımıdır ve kendi kullanım koşullarına tabidir.

### 5. İstemcileri bilgisayarlarınıza dağıtın

Hazırladığınız istemci klasörünü yönetmek istediğiniz Windows bilgisayarlarına kopyalayın ve istemciyi başlatın. Bilgisayarların panelde **Bağlı** olarak görünmesini bekleyin.

Kurulumu yalnızca kendi bilgisayarlarınızda veya sahibinden açık izin aldığınız cihazlarda yapın. Hesabınıza özel oluşturulan istemci paketini herkese açık depoya yüklemeyin.

### 6. Panelden başlatın ve durdurun

Başlangıçta madencilik kapalıdır. Bir cihaz seçip **Seçileni aç** düğmesiyle başlatın. Durdurmak için **Seçileni kapat** düğmesini kullanın.

Birden fazla cihazı Ctrl tuşuyla seçebilirsiniz. **Tümünü aç** ve **Tümünü kapat** düğmeleri toplu kontrol sağlar.

## NVIDIA ayarları

Listeden bir istemci seçerek desteklenen GPU ayarlarını değiştirebilirsiniz:

| Alan | Açıklama |
| --- | --- |
| Güç limiti (W) | Kartın desteklediği minimum ve maksimum değerler arasında olmalıdır. |
| GPU hedefi (MHz) | Sabit hedef frekanstır; +MHz offset değeri değildir. |
| Bellek (MHz) | Seçilen kart ve sürücünün desteklediği bellek frekansı ayarıdır. |
| 0 değeri | İlgili ayarı uygulamamak anlamına gelir. |

**Ayar değiştirme sırası:** Madenciliği kapatın → **Durdu** durumunu bekleyin → Değerleri girip **Uygula** düğmesine basın → Madenciliği yeniden açın.

Her ekran kartı aynı watt ve frekans değerlerini desteklemez. Ayar uygulanamazsa paneldeki hata bilgisini kontrol edin.

## Durum göstergeleri

| Gösterge | Anlamı |
| --- | --- |
| Bağlı | İstemciden güncel bildirim alınıyor. |
| Bağlantı yok | İstemciden 90 saniyedir bildirim alınmadı. |
| Mining komutu | Panelden gönderilen başlatma veya durdurma isteği. |
| Gerçek mining | WildRig işleminin bildirilen çalışma durumu. |
| Son bildirim | İstemciden alınan son durum bildiriminin zamanı. |
| Hata | İstemcinin bildirdiği hata açıklaması. |

Komutlar istemcinin bir sonraki 30 saniyelik kontrolünde uygulanır; düğmeye basıldığı anda durumun değişmesi beklenmemelidir.

**WildRig işleminin çalışıyor görünmesi, havuzun geçerli pay kabul ettiğini tek başına kanıtlamaz.** İşçi, hashrate ve kabul edilen pay bilgilerini havuz üzerinden ayrıca kontrol edin.

## Sık sorulan sorular

### MyMinerOS bir işletim sistemi mi?

Hayır. MyMinerOS, Windows bilgisayarlarında çalışan istemcileri yönetmek için kullanılan bir uygulamadır.

### WildRig bu paketin içinde mi?

Hayır. Bu GitHub dağıtımı madenci içermez. WildRig'i yukarıdaki geliştirici bağlantısından ayrıca indirip istemci klasörüne eklemeniz gerekir.

### MyMinerOS ücretsiz mi?

Evet. MyMinerOS ücretsiz kullanıma sunulmaktadır. Üçüncü taraf madenci ve havuzların koşulları ile elektrik ve internet maliyetleri ayrıca değerlendirilir.

### “WildRig bulunamadı” hatası alıyorum

WildRig dosyalarının istemci klasöründeki `wildrig` alt klasöründe bulunduğunu ve `wildrig.exe` dosya yolunun doğru olduğunu kontrol edin.

### Bilgisayar panelde bağlı görünmüyor

Bilgisayarın açık, internete bağlı ve istemci uygulamasının çalışıyor olduğunu kontrol edin. Ayrıca doğru hesabınıza bağlı istemci dosyalarını kullandığınızdan emin olun.

### Güç limiti uygulanamıyor

Hata mesajında belirtilen, ekran kartının desteklediği aralıkta bir watt değeri girin. Örneğin bir kart için uygun olan 200 W, başka bir kartın izin verdiği aralığın dışında kalabilir.

## Bağlantılar ve destek


- **WildRig:** [Geliştiricinin sürüm sayfası](https://github.com/andru-kun/wildrig-multi/releases)
- **Pearlhash havuzu:** [pearlhash.xyz](https://pearlhash.xyz/)
- **Pearl platformu:** [compute.pearlresearch.ai](https://compute.pearlresearch.ai/)
- **Destek:** [myminerteam9933xx1h@gmail.com](mailto:myminerteam9933xx1h@gmail.com)

MyMinerOS, WildRig ve Pearl hizmetlerinden bağımsız bir yönetim uygulamasıdır.
