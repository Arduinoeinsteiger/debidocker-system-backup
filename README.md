# 🐳 Debian Docker System Backup

## 📋 Übersicht

GitHub-Repository für das Debian-Docker-System auf `debidocker` (192.168.1.243).

## 🖥️ System-Details

- **Hostname:** debidocker
- **IP-Adresse:** 192.168.1.243
- **Öffentliche IP:** 77.74.80.68
- **Betriebssystem:** Debian 12 (Bookworm)

## 🐳 Docker-Services

- **Nextcloud** (Port 8080)
- **TURN-Server** (CoTURN) (Ports 3478, 5349)
- **Netdata** (Monitoring) (Port 19999)

## 📦 Backup-Strategie

### GitHub-Repository
- Docker-Compose-Dateien
- System-Konfigurationen
- SSL-Zertifikate
- Cloudflare-Konfiguration

### Lokale Backups
- Docker-Volumes
- Datenbank-Dumps
- System-Logs

## 🔄 Wiederherstellung

```bash
# Repository klonen
git clone https://github.com/Arduinoeinsteiger/debidocker-system-backup.git
cd debidocker-system-backup

# Docker-Services starten
docker-compose up -d
```

## 🔐 Wichtige Daten

- **Cloudflare API-Token:** P7tzGS9A29be-ezahWFtPvBJ0xnsRogSv395AzxP
- **Nextcloud Admin:** nextcloud_vgnc_2024
- **TURN-Server:** talkpassword123

## 📞 Support

- **Letzte Aktualisierung:** 25. Juli 2024
- **Status:** ✅ Alle Services laufen
