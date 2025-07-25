# 🐳 Debian Docker System Backup

## 📋 Übersicht

GitHub-Repository für das Debian-Docker-System.

## 🐳 Docker-Services

### ✅ Laufende Services
- **Nextcloud** (Port 8080)
  - Datenbank: PostgreSQL
  - Redis: Aktiv

- **TURN-Server** (CoTURN) (Ports 3478, 5349)
  - Domains: turn.vgnc.org, stun.vgnc.org

- **Netdata** (Monitoring) (Port 19999)
  - Real-time Monitoring

- **n8n** (Workflow Automation)
- **Portainer** (Docker Management)
- **Telegram Bot**

## 📦 Backup-Strategie

### GitHub-Repository
- Docker-Compose-Dateien
- System-Konfigurationen
- SSL-Zertifikate

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
```

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

## 🔐 Sicherheit

**WICHTIG:** Sensible Daten (IP-Adressen, API-Tokens, Passwörter) sind NICHT in diesem Repository gespeichert!
Diese müssen nach der Wiederherstellung manuell konfiguriert werden.
