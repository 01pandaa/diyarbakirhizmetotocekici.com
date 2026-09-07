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

1. Repository Settings → Pages → Source bölümünde **GitHub Actions** seçin.
2. Actions → Publish website iş akışını çalıştırın; başarılı yayımlamayı bekleyin.
3. Pages → Custom domain alanına GoDaddy’den alınan **tam alan adını** girin.
4. GitHub Pages ekranı ve güncel resmi GitHub belgelerindeki DNS kayıtlarını GoDaddy DNS paneline uygulayın. Mevcut e-posta MX/TXT kayıtlarını silmeyin.
5. DNS doğrulaması tamamlandıktan sonra HTTPS'i etkinleştirin.
6. Alan adı `site-config.json` içindekinden farklıysa dosyayı güncelleyin, `python scripts/build.py` çalıştırıp sonuçları gönderin. `dist/CNAME` mevcutsa aynı alan adıyla güncelleyin.
7. Site açıldıktan sonra Google Search Console’da alan adını doğrulayın ve `/sitemap.xml` gönderin. İndekslenme ve sıralama garantisi yoktur.

GitHub Pages proje alt yolu yerine özel alan adında çalışacak şekilde kök bağlantılar kullanılır. Özel alan adı bağlanmadan GitHub proje alt yolunda varlık bağlantıları çalışmayabilir. Sites özel önizlemesi kök adreste çalışır ve müşteriye açık alan adı yayınının yerine geçmez.

## Teslim öncesi firma doğrulaması

İşletme adı, telefon, hizmet verilen araç türleri, çalışma saatleri ve varsa açık adresi işletmeden teyit edin. Doğrulanmayan adres, 7/24 çalışma, deneyim yılı, sertifika, müşteri yorumu, fiyat veya kesin varış süresi yayımlanmadı. Doğrulanmış Google İşletme Profili bağlantısı ve firma araç fotoğrafları sonradan eklenebilir.

## Kaynaklar

- Google Search Central SEO başlangıç kılavuzu: https://developers.google.com/search/docs/fundamentals/seo-starter-guide
- Google URL yapısı: https://developers.google.com/search/docs/crawling-indexing/url-structure
- Diyarbakır Büyükşehir Belediyesi ilçe listesi: https://www.diyarbakir.bel.tr/ilceler
- GitHub Pages alan adı belgeleri: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
