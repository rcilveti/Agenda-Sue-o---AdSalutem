# Agenda de Sueño digital — AdSalutem

Diario de sueño de tres semanas en formato digital. Aplicación de un solo archivo,
sin servidor ni base de datos, pensada para funcionar en móvil, tableta y ordenador.

**Versión actual:** v4.8.0 — MODO PILOTO (datos ficticios, sin cifrado)

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

**Paciente** (acceso por código QR; PIN de 3 cifras como alternativa). Rellena su diario
cada día. El acceso lo genera el profesional al crear el diario y tiene una validez de
2 meses. En la demo también existe el acceso `paciente` / `demo`.

### Circuito de uso

1. El profesional crea un diario nuevo y completa los datos del paciente. Al pulsar
   **«Guardar datos del paciente»**, la aplicación muestra el **código QR de acceso**
   (con el PIN y los datos incorporados), el enlace y botones para imprimir o enviar.
2. El paciente **escanea el QR una sola vez**: entra directo, con su ficha ya rellena y
   el diario en blanco listo. No teclea nada. Su acceso queda guardado en el dispositivo,
   así que después abre el icono y entra directo.
3. El paciente rellena el diario cada día (edición día a día, con autoguardado).
4. Al terminar, pulsa **«Enviar mi diario»** y lo devuelve por WhatsApp o correo; el
   profesional lo carga en su base con un toque.

### Rellenado y varios dispositivos

En el dispositivo del paciente el diario se autoguarda tras cada cambio: nada se pierde
entre sesiones. Lo recomendable es usar siempre el mismo dispositivo; aun así, si el
diario se carga en un segundo dispositivo, la aplicación **fusiona** en vez de
sobrescribir, conservando los días registrados en cualquiera de los dos.

### Formas de intercambiar los datos

- **Código QR** (inicio): lleva el acceso y los datos de ficha. Un escaneo y el paciente
  está dentro.
- **Archivo** (CSV, ~2 KB) o **enlace** (devolución): el diario completo viaja por
  WhatsApp o correo al terminar.

---

## Cómo se publica

1. Crear un repositorio **público** en GitHub.
2. Subir estos archivos.
3. Ajustes → Pages → Origen: rama `main`, carpeta `/ (root)` → Guardar.
4. Esperar 1–2 minutos. La dirección de publicación es:
   **https://rcilveti.github.io/Agenda-Sueno-AdSalutem/**

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
