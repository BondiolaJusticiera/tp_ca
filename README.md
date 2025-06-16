# Backup Automático en Debian

Este repositorio contiene los archivos y configuraciones necesarias para realizar backups automáticos en un sistema Debian, utilizando scripts personalizados y tareas programadas con `cron`.

## grupo 7

- Enzo Caporali
- Hector Moreno
- Tomas Ignacio Muñoz Noto
- Carlos Emanuel Orlandini

## Contenido del repositorio

- `backup_full.sh`: Script principal de backup ubicado en `/opt/scripts`.
- Archivos comprimidos de los siguientes directorios:
  - `/root` → `root.tar.gz`
  - `/etc` → `etc.tar.gz`
  - `/opt` → `opt.tar.gz`
  - `/proc` → `proc.tar.gz`
  - `/www_dir` → `www_dir.tar.gz`
  - `/backup_dir` → `backup_dir.tar.gz`
  - `/var` → dividido en partes: `var.tar.gz.part_aa`, `var.tar.gz.part_ab`, etc.

## Instrucciones

1. El script `backup_full.sh` acepta dos argumentos: directorio origen y destino.
2. Valida que ambos directorios existan antes de ejecutar el backup.
3. Comprime el contenido con nombre que incluye la fecha en formato `YYYYMMDD`.
4. Se ejecuta automáticamente mediante `cron`:
   - Todos los días a las 00:00: backup de `/var/logs`.
   - Lunes, miércoles y viernes a las 23:00: backup de `/www_dir`.


