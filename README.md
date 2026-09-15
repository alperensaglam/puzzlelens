# PuzzleLens — destek ve gizlilik sayfaları

App Store kaydının **Support URL** ve **Privacy Policy URL** alanları buraya
işaret ediyor. İkisi de doldurulmadan uygulama gönderilemiyor.

Yayına alma:

```bash
# GitHub'da "puzzlelens" adında PUBLIC bir depo aç, sonra:
cd site
git init && git add -A
git commit -m "PuzzleLens destek ve gizlilik sayfaları"
git branch -M main
git remote add origin https://github.com/alperensaglam/puzzlelens.git
git push -u origin main
```

Ardından depo ayarlarından **Settings → Pages → Source: main / (root)**.

Birkaç dakika içinde yayına giriyor:

- https://alperensaglam.github.io/puzzlelens/
- https://alperensaglam.github.io/puzzlelens/privacy/
- https://alperensaglam.github.io/puzzlelens/support/

Sayfalar `privacy.html` değil `privacy/index.html` olarak duruyor: App Store
Connect'e yazılan adresler **uzantısız** ve Apple gönderimde bu iki URL'yi
gerçekten açıyor. Dizin biçimi her statik sunucuda çözülüyor; uzantısız
adresin `.html` dosyasına düşmesi ise sunucu davranışına bağlı. Gizlilik
URL'sinin 404 vermesi doğrudan ret sebebi, o yüzden tahmine bırakılmadı.

`Scripts/asc.py metadata` bu URL'leri App Store Connect'e yazıyor; adresler
`SUPPORT_URL` ve `PRIVACY_URL` sabitlerinde tanımlı.
