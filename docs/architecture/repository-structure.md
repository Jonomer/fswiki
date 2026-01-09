# Repository Yapısı / Repository Structure

FS DEV Knowledge Base projesinin detaylı klasör yapısı ve organizasyon prensipleri.

Detailed folder structure and organization principles of the FS DEV Knowledge Base project.

## Genel Bakış / Overview

```
fswiki/
├── README.md                    # Ana proje dokümantasyonu
├── CONTRIBUTING.md              # Katkı rehberi
├── ROADMAP.md                   # Proje yol haritası
├── STYLE_GUIDE.md              # Yazım standartları
├── CODE_OF_CONDUCT.md          # Davranış kuralları
├── LICENSE                      # MIT Lisansı
├── .gitignore                   # Git ignore kuralları
│
├── cybersecurity/               # Siber Güvenlik
│   ├── README.md
│   ├── defensive-security/
│   ├── ethical-hacking/
│   ├── network-security/
│   ├── vulnerability-assessment/
│   └── incident-response/
│
├── software-development/        # Yazılım Geliştirme
│   ├── README.md
│   ├── architecture/
│   ├── best-practices/
│   ├── devops/
│   ├── performance/
│   └── testing/
│
├── linux-sysadmin/             # Linux & Sistem Yönetimi
│   ├── README.md
│   ├── configuration/
│   ├── containerization/
│   ├── automation/
│   ├── monitoring/
│   └── security-hardening/
│
├── hardware-electronics/       # Donanım & Elektronik
│   ├── README.md
│   ├── embedded-systems/
│   ├── microcontrollers/
│   ├── pcb-design/
│   ├── hardware-security/
│   └── iot/
│
├── 3d-printing/                # 3D Baskı & Mühendislik
│   ├── README.md
│   ├── modeling/
│   ├── materials/
│   ├── post-processing/
│   ├── mechanical-design/
│   └── prototyping/
│
├── resources/                  # Ek Kaynaklar
│   ├── README.md
│   ├── tools/
│   ├── references/
│   ├── cheatsheets/
│   └── templates/
│
├── docs/                       # Proje Dokümantasyonu
│   ├── architecture/
│   │   └── repository-structure.md (bu dosya)
│   ├── guidelines/
│   └── templates/
│       ├── article-template.md
│       └── cybersecurity-article-template.md
│
└── assets/                     # Medya Dosyaları
    └── images/
```

## Organizasyon Prensipleri / Organization Principles

### 1. Kategorizasyon / Categorization

Her ana kategori:
- Tek bir konu alanını kapsar
- Kendi README.md dosyasına sahiptir
- Mantıklı alt kategorilere bölünmüştür

### 2. Hiyerarşi / Hierarchy

```
Kategori (Category)
  └── Alt Kategori (Sub-category)
      └── Makale (Article)
```

### 3. Dosya İsimlendirme / File Naming

- Küçük harf kullanımı
- Kebab-case formatı
- Açıklayıcı isimler
- Türkçe karakter yok

Örnekler:
- ✅ `network-segmentation-guide.md`
- ✅ `docker-container-security.md`
- ❌ `Network_Segmentation.md`
- ❌ `docker container guide.md`

## İçerik Organizasyonu / Content Organization

### Makale Yerleştirme / Article Placement

**Kural:** Her makale en spesifik uygun alt kategoriye yerleştirilir.

Örnek:
- "Docker Security Best Practices" → `linux-sysadmin/containerization/`
- "Network Segmentation for Security" → `cybersecurity/defensive-security/`
- "3D Printed Enclosure for Raspberry Pi" → `3d-printing/mechanical-design/`

### Cross-Referencing

İlgili içerikler:
- İlgili makaleler bölümünde linklenir
- Her kategori README'sinde ilgili kategoriler belirtilir

## Dosya Türleri / File Types

### Markdown Dosyaları (.md)

- Makaleler
- README dosyaları
- Dokümantasyon

### Diğer Dosyalar

- **Görseller:** `assets/images/` klasöründe
- **Şablonlar:** `resources/templates/` veya `docs/templates/`
- **Konfigürasyon:** Root dizinde (`.gitignore`, vb.)

## Genişletilebilirlik / Scalability

### Yeni Kategori Ekleme

Yeni kategori eklerken:
1. Ana dizinde klasör oluştur
2. `README.md` ekle (kategori açıklaması ile)
3. Ana `README.md`'yi güncelle
4. İlgili alt kategorileri oluştur

### Yeni Alt Kategori Ekleme

Yeni alt kategori eklerken:
1. İlgili kategori klasöründe alt klasör oluştur
2. Kategori `README.md`'sini güncelle
3. İlgili makaleleri taşı/ekle

## Bakım Notları / Maintenance Notes

### Düzenli Görevler

1. **Broken Link Kontrolü:**
   - İç linkler çalışıyor mu?
   - Dış linkler aktif mi?

2. **Organizasyon Review:**
   - Makaleler doğru yerde mi?
   - Yeni alt kategori gerekli mi?

3. **README Güncellemeleri:**
   - Kategori README'leri güncel mi?
   - İçerik listesi doğru mu?

## Örnek Yapılandırma / Example Structure

### Senaryo: Network Security Kategorisi

```
cybersecurity/
├── README.md
├── network-security/
│   ├── vpn-setup-guide.md
│   ├── firewall-configuration.md
│   ├── network-segmentation.md
│   └── ids-ips-setup.md
├── defensive-security/
│   └── ...
```

Her makale:
- Spesifik bir konuyu kapsar
- Uygun uzunlukta (500-3000 kelime)
- İlgili makalelere linklenir

---

**Son Güncelleme / Last Updated:** 2024 Q1

