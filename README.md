# Diyarbakır Hizmet Oto Çekici

Mobil uyumlu, Türkçe, statik oto çekici ve oto kurtarma web sitesi.

- İletişim: **0536 587 66 73**
- Alan adı: **diyarbakirhizmetotocekici.com** (depo adına göre hazırlanmıştır; GoDaddy kaydıyla doğrulayın).
- Ana sayfa, kurumsal, iletişim, hizmetler, hizmet bölgeleri ve blog.
- Dört hizmet detay sayfası, dört merkez ilçe sayfası ve beş özgün blog yazısı.
- Sabit telefon / WhatsApp butonları; mobil menü ve SSS.
- Sayfalara özel title/description, canonical, JSON-LD, sitemap, robots ve 404.
- Temsili olarak üretilmiş çekici fotoğrafı; gerçek firma aracı olduğu iddia edilmez.

## Düzenleme

`site-config.json` firma adı, telefon ve ana alan adını içerir. Metinler ve sayfa üretimi `scripts/build.py`, stiller ve mobil menü `dist/assets/` içindedir.

```sh
python scripts/build.py
```

Çıktı `dist/` dizinindedir. `dist/` herhangi bir statik barındırma hizmetine yüklenebilir. Site, gerçek HTML sayfalarından oluşur; sayfa içeriği için JavaScript gerekmez.

## GitHub Pages / alan adı

Site hem depo kökünden hem de `dist/` klasörünü yayımlayan Actions iş akışından çalışır. `python scripts/build.py` iki konumdaki çıktıyı birlikte günceller.

- Mevcut **Deploy from a branch → main → / (root)** ayarı kullanılabilir. Kök `index.html` tasarımı açar; `.nojekyll` ile statik dosyalar doğrudan sunulur.
- Alternatif olarak Source bölümünden **GitHub Actions** seçilebilir. İş akışı `dist/` çıktısını yayımlar.
- `CNAME` içindeki mevcut özel alan adı korunur ve üretimde `dist/CNAME` dosyasına da kopyalanır.
- Alan adı değişirse `CNAME` ve `site-config.json` birlikte güncellenmeli, sayfalar yeniden üretilmelidir.
- GoDaddy DNS kayıtları ve HTTPS doğrulaması GitHub Pages ekranından izlenir. E-posta MX/TXT kayıtları korunmalıdır.
- Site açıldıktan sonra Google Search Console’da alan adını doğrulayın ve `/sitemap.xml` gönderin. İndekslenme ve sıralama garantisi yoktur.

## Teslim öncesi firma doğrulaması

İşletme adı, telefon, hizmet verilen araç türleri, çalışma saatleri ve varsa açık adresi işletmeden teyit edin. Doğrulanmayan adres, 7/24 çalışma, deneyim yılı, sertifika, müşteri yorumu, fiyat veya kesin varış süresi yayımlanmadı. Doğrulanmış Google İşletme Profili bağlantısı ve firma araç fotoğrafları sonradan eklenebilir.

## Kaynaklar

- Google Search Central SEO başlangıç kılavuzu: https://developers.google.com/search/docs/fundamentals/seo-starter-guide
- Google URL yapısı: https://developers.google.com/search/docs/crawling-indexing/url-structure
- Diyarbakır Büyükşehir Belediyesi ilçe listesi: https://www.diyarbakir.bel.tr/ilceler
- GitHub Pages alan adı belgeleri: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
