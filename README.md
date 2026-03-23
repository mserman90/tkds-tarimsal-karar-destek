# TKDS PRO v2 — Turkiye Bitkisel Uretim Karar Destek Sistemi

Turkiye'deki 57 ilce ve 44 urun icin tarimsal karar destek sistemi. Gercek meteorolojik veri, 2025-2027 devlet destekleme fiyatlari ve su dengesi analizi iceren kapsamli bir web uygulamasi.

## Ozellikler

- **57 Ilce, 44 Urun**: Turkiye genelinde tarimsal uretim planlama
- **2025-2027 Destekleme Verileri**: T.C. Tarim ve Orman Bakanligi resmi birim fiyatlari (244 TL/da baz birim)
- **Gercek GDD Hesaplama**: Open-Meteo arsiv API'si ile son 90 gunluk buyume derecesi gun hesabi
- **Su Dengesi Analizi**: FAO-56 Penman-Monteith ETo, Thornthwaite su butcesi modeli
- **Erken Uyari Sistemi**: Sicaklik, yagis, don ve kuraklik alarmlari
- **Finansal Analiz**: Maliyet dagilimi, kar analizi, sulama maliyeti
- **NDVI Simulasyonu**: Uydu bazli bitki sagligi indeksi
- **Leaflet Harita**: Interaktif konum secimi ve goruntusu

## API Kullanimi ve Guvenlik

### Kullanilan API'ler

| API | Anahtar Gerekli | Aciklama |
|-----|:---:|---|
| [Open-Meteo](https://open-meteo.com/) | Hayir | Hava durumu tahmini, toprak nemi, sicaklik |
| [Open-Meteo Archive](https://archive-api.open-meteo.com/) | Hayir | Gecmis meteorolojik veri (GDD hesaplama) |
| [Nominatim/OSM](https://nominatim.openstreetmap.org/) | Hayir | Geocoding (konum arama) |
| [NASA Earthdata](https://earthdata.nasa.gov/) | Evet | MODIS NDVI, SMAP Toprak Nemi, GLDAS |

### Guvenlik Kurallari

1. **API anahtarlarini ASLA kaynak koduna gommeyin**
2. `.env` dosyasini `.gitignore` ile hariclayarak anahtarin Git'e girmesini onleyin
3. Deployment platformunda (Vercel, Railway, Render) **Environment Variables / Secrets** kullanin
4. NASA Earthdata token'i duzenli olarak yenileyin
5. `.env.example` dosyasini referans olarak kullanin

### Yerel Gelistirme

```bash
# 1. Repoyu klonlayin
git clone https://github.com/mserman90/tkds-tarimsal-karar-destek.git

# 2. .env dosyasi olusturun
cp .env.example .env

# 3. .env dosyasina NASA token'inizi ekleyin
# EARTHDATA_TOKEN=your_actual_token_here

# 4. index.html dosyasini tarayicida acin
```

## Veri Kaynaklari

- [T.C. Tarim ve Orman Bakanligi - 2025 Destekleme Birim Fiyatlari](https://www.tarimorman.gov.tr/BUGEM/Belgeler/Tar%C4%B1m%20Havzalar%C4%B1/2025%20Y%C4%B1l%C4%B1%20Destekleme%20Birim%20Fiyatlar%C4%B1--.pdf)
- [TKDK IPARD III - 2026 Cagri Takvimi](https://www.tkdk.gov.tr/Haber/bakan-yumakli-241-milyon-avro-butceli-2026-cagri-takvimimiz-hayirli-olsun-13038)
- [Open-Meteo API](https://open-meteo.com/)
- [NASA Earthdata](https://earthdata.nasa.gov/)

## Lisans

MIT

---
*Created with [Perplexity Computer](https://www.perplexity.ai/computer)*
