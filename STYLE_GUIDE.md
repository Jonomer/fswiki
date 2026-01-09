# Stil Kılavuzu / Style Guide

FS DEV Knowledge Base için yazım standartları, formatlama kuralları ve içerik gereksinimleri.

Writing standards, formatting rules, and content requirements for FS DEV Knowledge Base.

---

## 📋 İçindekiler / Table of Contents

- [Genel İlkeler / General Principles](#-genel-ilkeler--general-principles)
- [Dosya Organizasyonu / File Organization](#-dosya-organizasyonu--file-organization)
- [Markdown Formatlama / Markdown Formatting](#-markdown-formatlama--markdown-formatting)
- [İçerik Yapısı / Content Structure](#-içerik-yapısı--content-structure)
- [Dil ve Ton / Language and Tone](#-dil-ve-ton--language-and-tone)
- [Kod ve Örnekler / Code and Examples](#-kod-ve-örnekler--code-and-examples)
- [Görseller / Images](#-görseller--images)
- [Linkler ve Referanslar / Links and References](#-linkler-ve-referanslar--links-and-references)
- [Özel Durumlar / Special Cases](#-özel-durumlar--special-cases)

---

## 🎯 Genel İlkeler / General Principles

### 1. Netlik ve Doğruluk / Clarity and Accuracy

- ✅ Açık, anlaşılır dil kullanın
- ✅ Teknik terimleri ilk kullanımda açıklayın
- ✅ Gerçek ve doğrulanabilir bilgi verin
- ✅ Kaynak gösterin

### 2. Pratik Odaklılık / Practical Focus

- ✅ Teoriden çok, uygulanabilir içerik
- ✅ Gerçek dünya senaryoları
- ✅ Adım adım talimatlar
- ✅ Troubleshooting bölümleri

### 3. Profesyonellik / Professionalism

- ✅ Yüksek kalite standartları
- ✅ Tutarlı formatlama
- ✅ Doğru gramer ve yazım
- ✅ Uygun teknik terminoloji

---

## 📁 Dosya Organizasyonu / File Organization

### Dosya İsimlendirme / File Naming

**Format:** `kebab-case.md` (küçük harf, tire ile ayrılmış)

**Örnekler:**
```
✅ network-segmentation-guide.md
✅ docker-container-security.md
✅ pcb-design-best-practices.md
✅ 3d-printing-troubleshooting.md

❌ Network_Segmentation_Guide.md
❌ docker container security.md
❌ PCB-Design.md
```

**Kurallar:**
- Sadece küçük harf
- Kelimeler arasında tire (`-`)
- Açıklayıcı ve spesifik isimler
- Türkçe karakter kullanmayın (İ → i, Ş → s, vb.)

### Klasör Yapısı / Folder Structure

Her kategori altında mantıklı alt klasörler kullanın:

```
cybersecurity/
├── defensive-security/
│   ├── network-segmentation-guide.md
│   └── firewall-configuration.md
├── ethical-hacking/
│   └── penetration-testing-methodology.md
└── README.md (kategori açıklaması için)
```

---

## 📝 Markdown Formatlama / Markdown Formatting

### Başlıklar / Headings

**Hiyerarşi:**
```markdown
# H1 - Ana Başlık (Sayfa başlığı, bir kez kullanılır)
## H2 - Bölüm başlıkları
### H3 - Alt bölümler
#### H4 - Alt alt bölümler (nadiren)
```

**Kurallar:**
- H1 sadece dosyanın en başında, bir kez
- H2 ve H3 yaygın kullanım
- H4 ve altı mümkünse kaçının
- Başlıklar açıklayıcı olmalı

### Metin Formatlama / Text Formatting

```markdown
**Kalın / Bold** - Önemli terimler, komutlar
*İtalik / Italic* - Vurgu, değişken isimleri
`Kod / Code` - Teknik terimler, komutlar, dosya yolları
~~Üstü çizili / Strikethrough~~ - Güncel olmayan bilgi (nadiren)
```

**Örnek:**
```markdown
`docker run` komutu ile bir container başlatabilirsiniz. 
**Önemli:** Bu işlem root yetkisi gerektirebilir.
```

### Listeler / Lists

**Sırasız Liste (Unordered):**
```markdown
- İlk madde
- İkinci madde
  - Alt madde (2 space indent)
  - Alt madde
- Üçüncü madde
```

**Sıralı Liste (Ordered):**
```markdown
1. İlk adım
2. İkinci adım
   1. Alt adım
   2. Alt adım
3. Üçüncü adım
```

**Kontrol Listesi (Checklist):**
```markdown
- [ ] Yapılacak görev 1
- [x] Tamamlanmış görev
- [ ] Yapılacak görev 2
```

### Blok Alıntılar / Blockquotes

```markdown
> **Not / Note:** Önemli bir bilgi veya uyarı için kullanılır.

> **Uyarı / Warning:** Dikkat edilmesi gereken durumlar için.

> **İpucu / Tip:** Yararlı ipuçları için.
```

### Kod Blokları / Code Blocks

**Satır İçi Kod / Inline Code:**
```markdown
`komut` veya `değişken_ismi`
```

**Kod Blokları / Code Blocks:**
````markdown
```language
kod buraya
```

```bash
docker ps -a
```

```python
def example():
    return "Hello"
```

```yaml
services:
  web:
    image: nginx
```
````

**Dil Etiketleri / Language Tags:**
- `bash`, `sh` - Shell komutları
- `python`, `javascript`, `go`, vb. - Programlama dilleri
- `yaml`, `json`, `xml` - Konfigürasyon dosyaları
- `dockerfile`, `docker-compose` - Docker dosyaları
- `text` veya boş - Genel metin

---

## 📖 İçerik Yapısı / Content Structure

### Zorunlu Bölümler / Required Sections

Her makale şu yapıyı içermelidir:

```markdown
# Makale Başlığı / Article Title

## Özet / Summary
[2-3 cümlelik kısa açıklama]

## Gereksinimler / Prerequisites
- Gerekli bilgi seviyesi
- Gerekli araçlar/yazılımlar
- Ön koşul bilgiler

## İçerik / Content
[Ana içerik burada]

## Örnekler / Examples
[Pratik örnekler, kod snippet'leri]

## Sonuç / Conclusion
[Özet ve sonraki adımlar]

## Kaynaklar / References
- [Kaynak 1](url)
- [Kaynak 2](url)

## İlgili Makaleler / Related Articles
- [Makale 1](relative-path.md)
- [Makale 2](relative-path.md)
```

### Opsiyonel Bölümler / Optional Sections

```markdown
## Sorun Giderme / Troubleshooting
[Yaygın sorunlar ve çözümleri]

## Güvenlik Notları / Security Notes
[Güvenlikle ilgili önemli notlar]

## Best Practices
[En iyi uygulamalar]

## Notlar / Notes
[Ek notlar, uyarılar]
```

---

## 💬 Dil ve Ton / Language and Tone

### Dil Kuralları / Language Rules

1. **Profesyonel ama Erişilebilir:**
   - Teknik terimler kullanın ama açıklayın
   - Jargon'u aşırı kullanmayın
   - Yeni başlayanlar için de anlaşılır olun

2. **Aktif Ses Kullanımı:**
   ```
   ✅ "Komutu çalıştırın" (aktif)
   ❌ "Komut çalıştırılmalıdır" (pasif, gereksiz formal)
   ```

3. **Net Talimatlar:**
   ```
   ✅ "Dosyayı kaydedin ve servisi yeniden başlatın"
   ❌ "Dosyanın kaydedilmesi ve servisin yeniden başlatılması önerilir"
   ```

4. **İkinci Şahıs (Sen/Siz):**
   - Talimatlarda "siz" kullanın
   - Örneklerde "sen" kullanılabilir (daha samimi)

### Çoklu Dil Desteği / Multilingual Support

**Format:** Türkçe ve İngilizce birlikte veya ayrı dosyalar

**Yöntem 1 - Aynı Dosyada:**
```markdown
# Başlık / Title

## Türkçe Bölüm
İçerik...

## English Section
Content...
```

**Yöntem 2 - Ayrı Dosyalar:**
```
guide-tr.md
guide-en.md
```

**Önerilen:** Yöntem 1 (aynı dosya), daha kolay bakım

---

## 💻 Kod ve Örnekler / Code and Examples

### Kod Örnekleri Kuralları / Code Example Rules

1. **Çalışır Örnekler:**
   - Tüm kod örnekleri test edilmiş olmalı
   - Çalışmayan placeholder kod kullanmayın

2. **Açıklayıcı Yorumlar:**
   ```python
   # ✅ İyi
   def secure_hash(password: str) -> str:
       """Güvenli hash fonksiyonu - bcrypt kullanır"""
       return bcrypt.hashpw(password.encode(), bcrypt.gensalt())
   
   # ❌ Kötü
   def hash(p):
       return h(p)  # Ne yaptığı belli değil
   ```

3. **Output Gösterimi:**
   ```markdown
   Komutu çalıştırdığınızda:
   
   ```bash
   $ docker ps
   CONTAINER ID   IMAGE     STATUS
   abc123         nginx     Up 2 hours
   ```
   ```

4. **Hata Senaryoları:**
   ```markdown
   Eğer hata alırsanız:
   
   ```bash
   $ docker run ubuntu
   Error: permission denied
   ```
   
   Çözüm: `sudo` kullanın veya docker grubuna ekleyin.
   ```

### Güvenlik Hassasiyeti / Security Sensitivity

**Asla Yapmayın / Never Do:**
- ❌ Gerçek API key'leri
- ❌ Gerçek şifreler veya token'lar
- ❌ Production veritabanı bağlantı bilgileri
- ❌ Kişisel bilgiler

**Yapın / Do:**
- ✅ `YOUR_API_KEY`, `example.com` gibi placeholder'lar
- ✅ `.env.example` dosyaları
- ✅ Güvenlik notları ekleyin

---

## 🖼️ Görseller / Images

### Görsel Kuralları / Image Rules

1. **Format:**
   - PNG: Screenshot'lar, diagram'lar
   - SVG: Vektör grafikler (tercih edilir)
   - JPG: Fotoğraflar (nadiren)

2. **Boyut:**
   - Maksimum genişlik: 1200px
   - Dosya boyutu: Mümkün olduğunca küçük (<500KB ideal)

3. **Dosya İsimlendirme:**
   ```
   assets/
   ├── images/
   │   ├── network-topology-diagram.png
   │   ├── docker-architecture.svg
   │   └── pcb-design-example.png
   ```

4. **Markdown Kullanımı:**
   ```markdown
   ![Alt text açıklaması / Alt text description](path/to/image.png)
   
   *Şekil 1: Ağ topolojisi diyagramı / Figure 1: Network topology diagram*
   ```

5. **Erişilebilirlik:**
   - Alt text mutlaka ekleyin
   - Açıklayıcı başlık/şekil numarası ekleyin

---

## 🔗 Linkler ve Referanslar / Links and References

### İç Linkler / Internal Links

```markdown
✅ [Makale Adı](relative/path/to/article.md)
✅ [Başlık](#section-id)  # Aynı dosya içi
```

### Dış Linkler / External Links

```markdown
✅ [Kaynak Adı](https://example.com) - Açıklayıcı metin
✅ [RFC 7231](https://tools.ietf.org/html/rfc7231) - HTTP/1.1 spesifikasyonu
```

**Kurallar:**
- Link metni açıklayıcı olmalı (sadece "buraya" değil)
- Dış linkler için güvenilir kaynaklar kullanın
- Mümkünse HTTPS kullanın

### Referans Formatı / Reference Format

```markdown
## Kaynaklar / References

- [Dokümantasyon Başlığı](https://example.com/docs) - Kısa açıklama
- [Makale Başlığı](https://example.com/article) - Yazar, Yıl (opsiyonel)
- RFC 7231 - [Hypertext Transfer Protocol](https://tools.ietf.org/html/rfc7231)
```

---

## ⚠️ Özel Durumlar / Special Cases

### Siber Güvenlik İçerikleri / Cybersecurity Content

**ZORUNLU EKLEMELER / REQUIRED ADDITIONS:**

```markdown
## ⚠️ Etik ve Yasal Uyarı / Ethical and Legal Warning

Bu içerik **sadece eğitim ve yasal savunma amaçlı** kullanım için hazırlanmıştır.

**ÖNEMLİ:**
- Bu teknikleri sadece **sahip olduğunuz sistemlerde** veya **açık izin verilen sistemlerde** kullanın
- Yetkisiz erişim yasadışıdır ve cezai sorumluluk doğurabilir
- Etik hackleme için mutlaka yazılı izin (penetration testing contract) alın
- Bu bilgileri kötü niyetle kullanmayın

**Yasal Sorumluluk Reddi:** Bu içeriği kullanarak yapılan herhangi bir eylemden 
proje sahipleri veya katkıda bulunanlar sorumlu tutulamaz.
```

### Güncel Olmayan İçerik / Outdated Content

Eğer içerik güncel değilse:

```markdown
> **⚠️ Güncel Olmayan İçerik / Outdated Content**
> 
> Bu makale [Tarih] tarihinde yazılmıştır ve bazı bilgiler güncel olmayabilir.
> Güncelleme planlanmaktadır. Son güncelleme: [Tarih]
```

### Work-in-Progress (WIP) / İnşa Halinde

```markdown
> **🚧 İnşa Halinde / Work in Progress**
> 
> Bu makale hala yazılmaktadır. İçerik eksik veya değişebilir.
> Tahmini tamamlanma: [Tarih]
```

---

## ✅ Kontrol Listesi / Checklist

Makale göndermeden önce:

### İçerik / Content
- [ ] Özet bölümü var mı?
- [ ] Gereksinimler belirtilmiş mi?
- [ ] Ana içerik tam ve doğru mu?
- [ ] Örnekler çalışır durumda mı?
- [ ] Sonuç bölümü var mı?

### Formatlama / Formatting
- [ ] Markdown syntax doğru mu?
- [ ] Başlık hiyerarşisi doğru mu?
- [ ] Kod blokları doğru dil etiketiyle mi?
- [ ] Linkler çalışıyor mu?
- [ ] Görseller varsa alt text var mı?

### Etik ve Yasal / Ethical and Legal
- [ ] Güvenlik içeriği için uyarı eklendi mi?
- [ ] Hassas bilgi (API key, şifre) yok mu?
- [ ] Kaynaklar belirtilmiş mi?
- [ ] Telif hakkı ihlali yok mu?

### Kalite / Quality
- [ ] Yazım hatası kontrolü yapıldı mı?
- [ ] Teknik doğruluk kontrol edildi mi?
- [ ] Anlaşılır ve profesyonel dil kullanıldı mı?

---

## 📚 Ek Kaynaklar / Additional Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)
- [Technical Writing Best Practices](https://developers.google.com/tech-writing)
- [CONTRIBUTING.md](CONTRIBUTING.md) - Katkı süreci

---

**Son Güncelleme / Last Updated:** 2024 Q1

