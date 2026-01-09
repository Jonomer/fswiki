# İçerik Standartları Özeti / Content Standards Summary

Bu belge, FS DEV Knowledge Base için içerik standartlarının kısa özetidir. Detaylı bilgi için [STYLE_GUIDE.md](../../STYLE_GUIDE.md) dosyasına bakın.

This document is a brief summary of content standards for FS DEV Knowledge Base. See [STYLE_GUIDE.md](../../STYLE_GUIDE.md) for detailed information.

## Hızlı Referans / Quick Reference

### Dosya İsimlendirme / File Naming

```
✅ doğru: network-segmentation-guide.md
❌ yanlış: Network_Segmentation_Guide.md
```

**Kural:** Küçük harf, kebab-case, açıklayıcı

### Makale Yapısı / Article Structure

Her makale şunları içermelidir:

1. ✅ **Başlık / Title** (H1)
2. ✅ **Özet / Summary** (H2)
3. ✅ **Gereksinimler / Prerequisites** (H2)
4. ✅ **İçerik / Content** (H2)
5. ✅ **Örnekler / Examples** (H2)
6. ✅ **Sonuç / Conclusion** (H2)
7. ✅ **Kaynaklar / References** (H2)
8. ✅ **İlgili Makaleler / Related Articles** (H2)

### Siber Güvenlik İçerikleri / Cybersecurity Content

**ZORUNLU / REQUIRED:**

```markdown
## ⚠️ ETİK VE YASAL UYARI / ETHICAL AND LEGAL WARNING

[Detaylı uyarı metni - template'e bakın]
```

### Kod Örnekleri / Code Examples

```markdown
```language
// Kod buraya
// Açıklayıcı yorumlar ekleyin
```
```

**Kurallar:**
- Çalışır kod olmalı
- Açıklayıcı yorumlar
- Gerçek API key/şifre YOK
- Output gösterimi (gerekirse)

### Görseller / Images

```markdown
![Alt text açıklaması](path/to/image.png)

*Şekil 1: Açıklama / Figure 1: Description*
```

**Kurallar:**
- Alt text zorunlu
- Açıklayıcı başlık
- Maksimum 1200px genişlik
- <500KB dosya boyutu

### Linkler / Links

```markdown
✅ [Açıklayıcı Metin](https://example.com)
❌ [buraya](https://example.com)  # Açıklayıcı değil
```

### Dil ve Ton / Language and Tone

- ✅ Profesyonel ama erişilebilir
- ✅ Aktif ses kullanımı
- ✅ Net talimatlar
- ✅ İkinci şahıs (siz/sen)

## Kontrol Listesi / Checklist

Makale göndermeden önce:

### İçerik / Content
- [ ] Özet var mı?
- [ ] Gereksinimler belirtilmiş mi?
- [ ] Ana içerik tam mı?
- [ ] Örnekler çalışır durumda mı?

### Formatlama / Formatting
- [ ] Markdown syntax doğru mu?
- [ ] Başlık hiyerarşisi doğru mu?
- [ ] Kod blokları doğru dil etiketiyle mi?
- [ ] Linkler çalışıyor mu?

### Etik ve Yasal / Ethical and Legal
- [ ] Güvenlik içeriği için uyarı var mı?
- [ ] Hassas bilgi yok mu?
- [ ] Kaynaklar belirtilmiş mi?

### Kalite / Quality
- [ ] Yazım hatası kontrolü yapıldı mı?
- [ ] Teknik doğruluk kontrol edildi mi?
- [ ] Profesyonel dil kullanıldı mı?

---

**Detaylı bilgi için:** [STYLE_GUIDE.md](../../STYLE_GUIDE.md)

