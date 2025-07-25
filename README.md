# 🐳 Debian Docker System Backup

## 📋 Übersicht

GitHub-Repository für das Debian-Docker-System auf `debidocker` (192.168.1.243).

## 🖥️ System-Details

- **Hostname:** debidocker
- **IP-Adresse:** 192.168.1.243
- **Öffentliche IP:** 77.74.80.68
- **Betriebssystem:** Debian 12 (Bookworm)

## 🐳 Docker-Services

### ✅ Laufende Services
- **Nextcloud** (Port 8080)
  - Datenbank: PostgreSQL
  - Admin: nextcloud_vgnc_2024
  - Redis: Aktiv

- **TURN-Server** (CoTURN) (Ports 3478, 5349)
  - Domains: turn.vgnc.org, stun.vgnc.org
  - Credentials: talk / talkpassword123

- **Netdata** (Monitoring) (Port 19999)
  - Domain: monitoring.vgnc.org
  - Real-time Monitoring

## 📦 Backup-Strategie

### GitHub-Repository
- Docker-Compose-Dateien
- System-Konfigurationen
- SSL-Zertifikate
- Cloudflare-Konfiguration

### Lokale Backups
- **ALLE Docker-Volumes** (sehr wichtig!)
- Datenbank-Dumps (PostgreSQL)
- System-Logs
- Redis-Dumps

## 🔄 Wiederherstellung

```bash
# Repository klonen
git clone https://github.com/Arduinoeinsteiger/debidocker-system-backup.git
cd debidocker-system-backup

# Docker-Services starten
docker-compose up -d

# Prüfe Services
docker ps
```

## 🔐 Wichtige Daten

- **Cloudflare API-Token:** P7tzGS9A29be-ezahWFtPvBJ0xnsRogSv395AzxP
- **Nextcloud Admin:** nextcloud_vgnc_2024
- **TURN-Server:** talkpassword123

## 🚨 WICHTIG: Alle Docker-Volumes sichern!

```bash
# Alle Volumes auflisten
docker volume ls

# Alle Volumes sichern
for volume in $(docker volume ls --format "{{.Name}}"); do
    docker run --rm -v $volume:/data -v $(pwd):/backup alpine tar czf /backup/$volume.tar.gz -C /data .
done
```

## 📞 Support

- **Letzte Aktualisierung:** 25. Juli 2024
- **Status:** ✅ Alle Services laufen
- **Backup-Status:** ✅ Alle Docker-Volumes gesichert
