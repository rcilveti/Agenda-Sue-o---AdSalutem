# Agenda de Sueño digital — AdSalutem

Diario de sueño de tres semanas en formato digital. Aplicación de un solo archivo,
sin servidor ni base de datos, pensada para funcionar en móvil, tableta y ordenador.

**Versión actual:** v4.3.9 — MODO PILOTO (datos ficticios, sin cifrado)

---

## ⚠️ AVISO CRÍTICO DE PROTECCIÓN DE DATOS

**En este repositorio SOLO se aloja la aplicación. NUNCA los datos de pacientes.**

Este repositorio es público: cualquier archivo subido aquí queda visible para todo
internet e indexable por buscadores. Subir un diario de un paciente sería una brecha
de datos de salud (RGPD, categoría especial del art. 9).

Los diarios viajan **como archivo adjunto o como enlace** entre profesional y paciente,
y se guardan **en sus dispositivos**, nunca en este repositorio.

El archivo `.gitignore` bloquea automáticamente los nombres que genera la aplicación
(`agenda-sueno_*`, `*.csv`, `copia_seguridad_*`), pero es una red de seguridad, no
una garantía: revisa siempre qué subes antes de confirmar un cambio.

---

## Contenido del repositorio

| Archivo | Función |
|---|---|
| `index.html` | La aplicación completa (incluye la librería QR incrustada) |
| `manifest.json` | Permite instalarla como app en el móvil |
| `icon-192.png`, `icon-512.png` | Iconos de la app instalada |
| `.gitignore` | Bloquea la subida accidental de datos clínicos |

La aplicación no necesita conexión a internet salvo para cargarse la primera vez:
no depende de ningún servicio externo.

---

## Cómo funciona

Dos roles, una sola pantalla de acceso. El sistema reconoce por las credenciales
si quien entra es profesional o paciente.

**Profesional** (usuario y contraseña). Gestiona los diarios, ve el análisis clínico
de cada caso y las exportaciones. En la demo: `medico` / `clinica`.

**Paciente** (PIN de 3 cifras en modo piloto). Rellena su diario cada día. El PIN lo
genera el profesional al crear el diario y tiene una validez de 2 meses. En la demo
también existe el acceso `paciente` / `demo`.

### Circuito de uso

1. El profesional crea un diario nuevo. La aplicación genera un **PIN de acceso** y
   permite enviarlo junto con el enlace o el archivo del diario (por WhatsApp, correo,
   o mediante un **código QR** si el paciente está en consulta).
2. El paciente entra con su PIN y rellena el diario cada día. En su dispositivo, el
   diario se guarda solo y se genera una copia de seguridad automática.
3. Al terminar, el paciente devuelve su diario como **archivo** o como **enlace**.
4. El profesional lo recibe y lo carga en su base con un toque.

### Formas de intercambiar los datos

- **Archivo** (CSV, ~2 KB): se ve como un archivo normal, se abre en Excel y es la vía
  recomendada para el envío diario.
- **Enlace**: el diario viaja dentro del enlace (comprimido). Útil como copia de
  seguridad y para recuperar el diario en otro dispositivo. Es un texto largo.
- **Pegar contenido**: alternativa universal cuando el móvil no deja elegir el archivo.

---

## Cómo se publica

1. Crear un repositorio **público** en GitHub (por ejemplo `agenda-sueno`).
2. Subir estos archivos.
3. Ajustes → Pages → Origen: rama `main`, carpeta `/ (root)` → Guardar.
4. Esperar 1–2 minutos. La dirección será:
   `https://USUARIO.github.io/agenda-sueno/`

En el móvil conviene «Añadir a pantalla de inicio» para usarla como una app.

## Cómo se actualiza

Sustituir `index.html` por la versión nueva y confirmar el cambio. La web se
actualiza sola en 1–2 minutos. Todos los usuarios pasan a la versión nueva sin
tener que reinstalar nada.

Al publicar una versión nueva conviene avisar a los pacientes activos de que
guarden una copia de su diario antes de recargar.

---

## Estado y limitaciones

Fase **piloto con datos ficticios**. La aplicación muestra un distintivo naranja
permanente mientras el modo piloto está activo.

No apta todavía para datos clínicos reales en producción:

- El acceso se comprueba en el navegador, así que no es un control de acceso real.
- El PIN de 3 cifras es adecuado solo para datos de prueba.
- Los datos se guardan sin cifrar en el dispositivo.
- No hay sincronización entre dispositivos ni trazabilidad de accesos.

Para uso con pacientes reales hace falta un backend (autenticación real, cifrado en
reposo, registro de accesos y cumplimiento del RGPD). El cifrado por paciente ya está
implementado en el código y se activa poniendo `MODO_PILOTO = false`, pero el paso a
producción requiere además la infraestructura anterior y la validación del DPO.
