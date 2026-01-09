# Linux & Sistem Yönetimi / Linux & System Administration

Linux sistem yönetimi, konfigürasyon, otomasyon ve containerization konularında pratik rehberler.

Practical guides on Linux system administration, configuration, automation, and containerization.

## 📂 Klasör Yapısı / Folder Structure

### Konfigürasyon / Configuration
- Sistem konfigürasyon dosyaları
- Service management (systemd, init.d)
- Network configuration
- User ve permission management
- Environment variables ve PATH

### Containerization
- Docker fundamentals
- Docker Compose kullanımı
- Podman ve alternatifler
- Container security
- Multi-stage builds

### Otomasyon / Automation
- Shell scripting (bash, zsh)
- Python automation scripts
- Cron jobs ve task scheduling
- Configuration management (Ansible basics)
- Backup automation

### Monitoring
- System monitoring tools
- Log management (rsyslog, journald)
- Performance monitoring
- Resource usage tracking
- Alerting systems

### Security Hardening
- System hardening guidelines
- SSH security configuration
- Firewall setup (iptables, ufw, firewalld)
- SELinux/AppArmor basics
- Security auditing tools

## 🎯 Odak Alanları / Focus Areas

### Pratik Senaryolar
- Yaygın problemler ve çözümleri
- Production-ready configurations
- Troubleshooting workflows
- Disaster recovery

### Dağıtım Agnostik
- Ubuntu/Debian örnekleri
- RHEL/CentOS örnekleri
- Arch Linux notları (gerekirse)
- Distribution-agnostic çözümler

## 📝 İçerik Standartları / Content Standards

Her makale:
- Belirli bir Linux dağıtımını belirtmelidir (veya dağıtım agnostik olmalıdır)
- Komut çıktıları içermelidir
- Güvenlik notları eklenmelidir
- Backup önerileri içermelidir

Detaylı standartlar için [STYLE_GUIDE.md](../STYLE_GUIDE.md) dosyasına bakın.

## 🔗 İlgili Kategoriler / Related Categories

- [Siber Güvenlik](../cybersecurity/) - Security hardening
- [Yazılım Geliştirme](../software-development/) - DevOps ve automation

## ⚠️ Önemli Notlar / Important Notes

- Tüm komutlar production sistemlerde test edilmelidir
- Önemli değişiklikler öncesi backup alınmalıdır
- Root yetkisi gerektiren komutlar için uyarılar eklenmelidir

## 🤝 Katkıda Bulunma / Contributing

Yeni içerik eklerken:
1. Hangi Linux dağıtımı için olduğunu belirtin
2. Komut çıktılarını gösterin
3. Hata senaryolarını ele alın
4. Güvenlik ve backup notları ekleyin

---

**Unutmayın:** Sistem yönetimi komutları yanlış kullanıldığında veri kaybına neden olabilir. Test ortamında deneyin.

