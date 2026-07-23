# Agenda de Sueño digital — AdSalutem

Diario de sueño de tres semanas en formato digital. Aplicación de un solo archivo,
sin servidor ni base de datos.

**Versión actual:** v4.2.8 — MODO PILOTO (datos ficticios, sin cifrado)

---

## ⚠️ AVISO CRÍTICO DE PROTECCIÓN DE DATOS

**En este repositorio SOLO se aloja la aplicación. NUNCA los datos de pacientes.**

Este repositorio es público: cualquier archivo subido aquí queda visible para todo
internet e indexable por buscadores. Subir un diario de un paciente sería una brecha
de datos de salud (RGPD, categoría especial del art. 9).

Los diarios viajan **como archivo adjunto** entre profesional y paciente, y se guardan
**en sus dispositivos**, nunca en este repositorio.

El archivo `.gitignore` bloquea automáticamente los nombres que genera la aplicación
(`agenda-sueno_*`, `*.csv`, `copia_seguridad_*`), pero es una red de seguridad, no
una garantía: revisa siempre qué subes antes de confirmar un cambio.

---

## Contenido del repositorio

| Archivo | Función |
|---|---|
| `index.html` | La aplicación completa |
| `manifest.json` | Permite instalarla como app en el móvil |
| `icon-192.png`, `icon-512.png` | Iconos de la app instalada |
| `.gitignore` | Bloquea la subida accidental de datos clínicos |

---

## Cómo se publica

1. Crear un repositorio en GitHub (por ejemplo `agenda-sueno`).
2. Subir estos archivos.
3. Ajustes → Pages → Origen: rama `main`, carpeta `/ (root)` → Guardar.
4. Esperar 1–2 minutos. La dirección será:
   `https://USUARIO.github.io/agenda-sueno/`

## Cómo se actualiza

Sustituir `index.html` por la versión nueva y confirmar el cambio. La web se
actualiza sola en 1–2 minutos. Todos los usuarios pasan a la versión nueva sin
tener que reinstalar nada.

Al publicar una versión nueva conviene avisar a los pacientes activos de que
guarden una copia de su diario antes de recargar.

---

## Estado

Piloto. No apto todavía para datos clínicos reales en producción:
las contraseñas se guardan sin cifrar en el dispositivo y no hay
control de accesos ni trazabilidad. Para eso hace falta un backend.
