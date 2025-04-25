# ☁️ Nextcloud + Collabora + Cloudflare Tunnel en OMV 7

[![Status](https://img.shields.io/badge/status-en%20desarrollo-yellow)](https://github.com/sisku78/nextcloud-collabora-omv-cloudflare)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![Nextcloud](https://img.shields.io/badge/Nextcloud-30.x-brightgreen)](https://nextcloud.com)
[![Collabora](https://img.shields.io/badge/Collabora%20Online-Compatible-blueviolet)](https://www.collaboraoffice.com/)

> Infraestructura autosuficiente y segura para montar tu nube personal en casa con edición de documentos online, certificados wildcard con Let's Encrypt, y túnel sin puertos abiertos mediante Cloudflare Tunnel.

---

## 📌 Características principales

✅ Nextcloud + MariaDB con edición en línea gracias a Collabora  
✅ Certificados SSL wildcard automáticos con Let's Encrypt (Cloudflare DNS)  
✅ Cloudflare Tunnel sin necesidad de abrir puertos en el router  
✅ Red interna macvlan con IPs fijas para comunicación directa entre contenedores  
✅ Configuración avanzada de NGINX, seguridad y compatibilidad con Cloudflare  
✅ Listo para automatización futura con scripts de despliegue

---

## 📁 Estructura del proyecto

```
nextcloud-collabora-omv-cloudflare/
├── compose/                # Archivos docker-compose.yml por servicio
├── config/                 # Archivos de configuración (NGINX, PHP, Collabora)
├── docs/                   # Documentación técnica paso a paso
├── scripts/                # Scripts de automatización
├── README.md               # Este archivo
└── LICENSE                 # Licencia (MIT por defecto)
```

---

## 🚀 Despliegue rápido

> ⚠️ Asegúrate de tener OMV 7, Docker y docker-compose instalados correctamente.

1. Configura tu zona DNS en Cloudflare para `*.tudominio.com`
2. Lanza el script `scripts/generar_certificados.sh` (requiere tu `cloudflare.ini`)
3. Ejecuta `scripts/configurar_red_macvlan.sh` para crear la red local
4. Inicia los servicios con `scripts/deploy_stack.sh`

---

## 🧠 Documentación paso a paso

- [`docs/00_requisitos.md`](docs/00_requisitos.md) — Requisitos y herramientas necesarias  
- [`docs/01_certificados_letsencrypt.md`](docs/01_certificados_letsencrypt.md) — Certificados wildcard con Cloudflare  
- [`docs/02_cloudflare_tunnel.md`](docs/02_cloudflare_tunnel.md) — Configuración del túnel  
- [`docs/03_docker_networking_macvlan.md`](docs/03_docker_networking_macvlan.md) — Red macvlan  
- [`docs/04_docker_compose_files.md`](docs/04_docker_compose_files.md) — Docker Compose por servicio  
- [`docs/05_configuracion_coolwsd.md`](docs/05_configuracion_coolwsd.md) — Config Collabora  
- [`docs/06_configuracion_nextcloud.md`](docs/06_configuracion_nextcloud.md) — Config Nextcloud  
- [`docs/07_solucion_errores_comunes.md`](docs/07_solucion_errores_comunes.md) — Problemas típicos y solución

---

## 🔐 Seguridad y privacidad

- Cloudflare actúa como proxy inverso con HTTPS
- Certificados wildcard en origen (Let's Encrypt)
- Headers de seguridad recomendados por Mozilla
- Acceso limitado por IP/Red en NGINX y `config.php`

---

## 📦 Licencia

Este proyecto está licenciado bajo la licencia [MIT](LICENSE).

---

## 🙌 Créditos

Inspirado por la comunidad de Nextcloud, Collabora, y Deepsek Linux (¡gracias!).  
Proyecto documentado y mantenido por [TuNombre o TuGitHub].

