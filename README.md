# Good Enough Games — web sitesi

Statik site (HTML + CSS, framework yok). Yayın adresi: https://good-enough.games

## Dosyalar

| Dosya | Ne işe yarar |
|---|---|
| `index.html` | Ana sayfa (logo, mağaza rozetleri, LinkedIn) |
| `support/index.html` | Support & Help Center (App Store'un istediği destek URL'si) |
| `privacy-policy/index.html` | Privacy Policy |
| `terms-conditions/index.html` | Terms & Conditions |
| `cookies-policy/index.html` | Cookies Policy |
| `assets/css/style.css` | Tüm stiller. Renkler en üstteki `:root` bloğunda |
| `assets/img/` | Logolar, favicon'lar, OG görseli |
| `CNAME` | GitHub Pages özel alan adı |

## Mağaza linklerini eklemek

`index.html` içinde `STORE LINKS` yorumunun altındaki iki `href="#"` değerini
App Store ve Google Play geliştirici sayfası linkleriyle değiştir.
`#` olduğu sürece rozetler soluk görünür ve "coming soon" satırı çıkar;
gerçek link girilince otomatik aktif olur ve satır kaybolur.

## E-postayı değiştirmek

Tüm sayfalarda `hello@goodenoughgames.com` geçiyor. Değiştirmek için:

```bash
grep -rl "hello@goodenoughgames.com" . | xargs sed -i "s/hello@goodenoughgames.com/YENI@ADRES/g"
```

## Yerelde görüntülemek

```bash
python -m http.server 8787
```

Sonra tarayıcıda http://localhost:8787

## Yayınlamak (GitHub Pages)

1. Bu klasörü GitHub'da bir repoya push et, Settings → Pages → Source: `main` branch, `/ (root)`.
2. Custom domain alanına `good-enough.games` yaz, "Enforce HTTPS" işaretle.
3. GoDaddy DNS'te şu kayıtları gir (mevcut A ve CNAME kayıtlarını sil):

| Tür | Ad | Değer |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | `<github-kullanici-adi>.github.io` |

DNS yayılması birkaç dakika ile birkaç saat sürer; sonra HTTPS otomatik gelir.
