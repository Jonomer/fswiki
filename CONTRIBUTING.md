# Katkıda Bulunma Rehberi / Contributing Guide

Bu belge, FS DEV Knowledge Base projesine nasıl katkıda bulunabileceğinizi açıklar.

This document explains how you can contribute to the FS DEV Knowledge Base project.

---

## 📋 İçindekiler / Table of Contents

- [Davranış Kuralları / Code of Conduct](#-davranış-kuralları--code-of-conduct)
- [Katkı Türleri / Types of Contributions](#-katkı-türleri--types-of-contributions)
- [İlk Adımlar / Getting Started](#-ilk-adımlar--getting-started)
- [İş Akışı / Workflow](#-iş-akışı--workflow)
- [Yazım Standartları / Writing Standards](#-yazım-standartları--writing-standards)
- [İnceleme Süreci / Review Process](#-inceleme-süreci--review-process)

---

## 📜 Davranış Kuralları / Code of Conduct

Bu projeye katkıda bulunurken [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) dosyasındaki kurallara uymanız beklenir. Kısa özet:

By contributing to this project, you are expected to follow the rules in [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Brief summary:

- ✅ Saygılı ve kapsayıcı olun
- ✅ Yapıcı geri bildirimde bulunun
- ✅ Profesyonel dil kullanın
- ❌ Kişisel saldırılar yapmayın
- ❌ Spam veya off-topic içerik göndermeyin

---

## 🎯 Katkı Türleri / Types of Contributions

### 1. İçerik Ekleme / Adding Content

- Yeni makaleler yazma
- Mevcut makaleleri iyileştirme
- Eksik konuları tamamlama
- Örnek kod ve senaryolar ekleme

### 2. Düzeltmeler / Fixes

- Yazım hatalarını düzeltme
- Formatlama sorunlarını çözme
- Güncel olmayan bilgileri güncelleme
- Broken link'leri düzeltme

### 3. Dokümantasyon / Documentation

- README'leri iyileştirme
- Yönergeleri netleştirme
- Örnekler ekleme
- Çeviriler (EN/TR)

### 4. Organizasyon / Organization

- İçerik kategorizasyonu
- Navigasyon iyileştirmeleri
- Cross-referencing ekleme

---

## 🚀 İlk Adımlar / Getting Started

### 1. Repository'yi Fork Edin

GitHub'da projeyi fork edin ve local'e klonlayın:

```bash
git clone https://github.com/YOUR_USERNAME/fswiki.git
cd fswiki
```

### 2. Remote Repository Ekleyin

```bash
git remote add upstream https://github.com/Jonomer/fswiki.git
```

### 3. Branch Oluşturun

Her katkı için yeni bir branch oluşturun:

```bash
git checkout -b feature/your-contribution-name
# veya
git checkout -b fix/issue-description
```

**Branch İsimlendirme Kuralları:**
- `feature/` - Yeni içerik veya özellik
- `fix/` - Hata düzeltmesi
- `docs/` - Dokümantasyon değişikliği
- `update/` - Mevcut içerik güncellemesi

---

## 📝 İş Akışı / Workflow

### 1. Değişikliklerinizi Yapın

- [STYLE_GUIDE.md](STYLE_GUIDE.md) dosyasındaki standartları takip edin
- Yüksek kaliteli, doğru içerik üretin
- Gerekli yerlerde kaynak ekleyin

### 2. Commit Mesajları / Commit Messages

Açıklayıcı ve kısa commit mesajları yazın:

```
feat(cybersecurity): Add defensive security best practices article

- Add network segmentation guide
- Include firewall configuration examples
- Add monitoring recommendations

Closes #123
```

**Commit Mesaj Formatı:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Commit Types:**
- `feat`: Yeni içerik/özellik
- `fix`: Hata düzeltmesi
- `docs`: Dokümantasyon
- `style`: Formatlama
- `refactor`: Kod/içerik yeniden yapılandırma
- `update`: Güncelleme

### 3. Test Edin

- Markdown syntax kontrolü yapın
- Link'lerin çalıştığından emin olun
- Formatlamanın doğru olduğunu kontrol edin

### 4. Push Edin ve PR Açın

```bash
git add .
git commit -m "feat(category): Description"
git push origin feature/your-contribution-name
```

Sonra GitHub'da Pull Request oluşturun.

---

## ✍️ Yazım Standartları / Writing Standards

### Genel Kurallar

1. **Dil ve Ton**: Profesyonel, teknik, ancak anlaşılır
2. **Format**: Markdown (.md)
3. **Uzunluk**: Makaleler 500-3000 kelime arası ideal
4. **Yapı**: Açık başlıklar, alt başlıklar, liste kullanımı

### İçerik Gereksinimleri

#### Her Makale İçermeli:

```markdown
# Makale Başlığı / Article Title

## Özet / Summary
Kısa açıklama (2-3 cümle)

## Gereksinimler / Prerequisites
- Gerekli bilgi/araçlar
- Ön koşullar

## İçerik / Content
[Ana içerik burada]

## Örnekler / Examples
[Kod örnekleri, senaryolar]

## Kaynaklar / References
- [Link 1](url)
- [Link 2](url)

## İlgili Makaleler / Related Articles
- [Makale 1](path)
- [Makale 2](path)
```

### Etik ve Yasal Gereksinimler

⚠️ **KRİTİK**: Siber güvenlik içerikleri için:

- ✅ Sadece **defansif** ve **etik hackleme** odaklı
- ✅ **Eğitim amaçlı** olduğunu belirt
- ✅ **Yasal uyarılar** ekle
- ✅ **Yetki gerektirdiğini** vurgula
- ❌ Exploit kodları veya saldırı araçları **YOK**
- ❌ Yetkisiz erişim yöntemleri **YOK**

---

## 🔍 İnceleme Süreci / Review Process

### PR Göndermeden Önce Kontrol Listesi

- [ ] [STYLE_GUIDE.md](STYLE_GUIDE.md) standartlarına uygun mu?
- [ ] Markdown formatı doğru mu?
- [ ] Yazım hatası var mı? (Spell-check yapıldı mı?)
- [ ] Link'ler çalışıyor mu?
- [ ] Görseller varsa, alt text eklenmiş mi?
- [ ] Etik ve yasal uyarılar gerektiğinde eklenmiş mi?
- [ ] Commit mesajları açıklayıcı mı?
- [ ] "Özet" bölümü var mı?

### İnceleme Aşamaları

1. **Otomatik Kontroller**: CI/CD (eğer varsa)
2. **İlk İnceleme**: Maintainer tarafından format kontrolü
3. **Teknik İnceleme**: İçerik doğruluğu kontrolü
4. **Nihai Onay**: Merge kararı

### Geri Bildirim

- İncelemeler yapıcı ve saygılı olacaktır
- Her geri bildirim için açıklama yapılacaktır
- Küçük değişiklikler için direkt düzeltme önerilebilir

---

## 📚 Kaynaklar / Resources

- [STYLE_GUIDE.md](STYLE_GUIDE.md) - Detaylı yazım standartları
- [ROADMAP.md](ROADMAP.md) - Proje yol haritası
- [Markdown Guide](https://www.markdownguide.org/) - Markdown referansı

---

## ❓ Sorular / Questions

Katkıda bulunurken sorularınız olursa:

1. [GitHub Discussions](https://github.com/Jonomer/fswiki/discussions) bölümüne bakın
2. Yeni bir Discussion açın
3. Issue oluşturun (kısa sorular için)

---

**Teşekkürler! / Thank you for contributing! 🙏**

