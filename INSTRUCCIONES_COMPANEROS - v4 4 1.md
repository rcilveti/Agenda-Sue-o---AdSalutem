# Agenda de Sueño digital — Instrucciones para la evaluación
# R. Cilveti - AdSalutem - versión 4.4.1

Gracias por participar en las pruebas de evaluación y validación del diario de sueño digital.

**Importante: usa solo casos y datos ficticios.** La aplicación está en fase piloto y
todavía no tiene cifrado ni control de accesos real. No introduzcas datos de pacientes reales.

---

## 1. Abrir la aplicación

Entra en esta dirección desde el móvil, la tableta o el ordenador:

**https://rcilveti.github.io/agenda-sueno/**

### En móvil o tableta, instálala (muy recomendable)

Al entrar, la propia app te ofrecerá instalarla. Hazlo: el diario se guarda de forma más fiable y se abre de un toque.

- **iPhone / iPad:** botón Compartir (el cuadrado con la flecha) → *Añadir a pantalla de  inicio* → *Añadir*.
- **Android:** menú de tres puntos → *Añadir a pantalla de inicio* (o pulsa el botón  «Cómo» del aviso, que lo instala directamente).

Sabrás que quedó instalada porque, al abrir el icono, la app se ve **a pantalla completa, sin la barra del navegador**.

---

## 2. Entrar

Una sola pantalla de acceso: el sistema reconoce por las credenciales si eres profesional o paciente.

| Rol | Acceso de prueba |
|---|---|
| Profesional | usuario `medico` · contraseña `clinica` |
| Paciente (demo) | usuario `paciente` · contraseña `demo` |

Empieza como **profesional**: verás 16 casos clínicos de ejemplo ya cargados
(insomnio de conciliación, retraso de fase, apnea, trabajo a turnos, hipersomnia…).

En uso real, cada paciente entra con un **PIN de 3 cifras** que genera el profesional al crear el diario (válido 2 meses). Para probarlo, crea un caso nuevo y verás aparecer su PIN.

---

## 3. Qué probar

**Como profesional:**
- Revisa varios casos de ejemplo y su análisis.
- Crea un caso ficticio nuevo con **+ NUEVO**: se genera un PIN de acceso para el paciente.
- Rellena algunos días pintando la rejilla.
- Mira la vista **Análisis**: informe clínico, métricas y evolución longitudinal.
- Prueba las exportaciones (Excel, PDF, Word).

**Como paciente (en el móvil):**
- Comprueba si rellenar el diario resulta intuitivo.
- Fíjate en el bloqueo de edición (botón **🔒 Solo ver / ✏️ Editando**): en móvil arranca
  bloqueado para que no marques sin querer.
- Mira si las instrucciones se entienden sin explicación previa.

---

## 4. Cómo circulan los diarios (importante)

El diario puede viajar de dos formas. Para la evaluación, cualquiera vale:

- **Archivo** (recomendado para el día a día): en **Enviar diario**, se abre el menú de
  compartir del móvil (WhatsApp, correo) o se descarga un `.csv` en el ordenador. Pesa
  unos 2 KB.
- **Enlace**: en **Enlace de respaldo**, el diario viaja dentro de un enlace. Es un texto
  largo; sirve sobre todo como copia de seguridad y para recuperar el diario en otro
  dispositivo.

### ⚠️ Regla de oro en el móvil, sobre todo en iPhone

**Una vez instalada la app, rellena siempre desde el icono, no desde los enlaces de
WhatsApp.**

En iPhone, el icono instalado y el navegador (Safari) son dos espacios separados: un
enlace de un mensaje **siempre abre Safari**, no el icono. Si mezclas las dos cosas
puedes acabar con **dos diarios distintos** sin darte cuenta.

El uso correcto es:
1. La primera vez, abre el enlace que te envíen → carga el diario → **instala la app en
   ese momento** (con el diario ya dentro).
2. A partir de ahí, abre siempre el **icono** para rellenar cada día.
3. Los enlaces quedan solo para el primer contacto o para recuperar el diario si cambias
   de dispositivo.

La app te avisa si detecta que podrías estar mezclando espacios, pero conviene tenerlo
claro de antemano.

---

## 5. Enviarme tu caso de prueba

Cuando tengas un caso rellenado, pulsa **📤 Enviar diario** y mándamelo por WhatsApp o
correo. Si me lo pasas como enlace, al abrirlo se cargará directamente en mi base.

---

## 6. Qué me interesa saber

Más que los fallos técnicos y el formato, sobretodo me interesa tu criterio clínico:

- ¿El registro por franjas horarias refleja bien lo que ves en consulta o en tu entorno de investigación/intervención?
- ¿Las métricas del análisis son las que usarías? ¿Falta alguna? ¿Sobra alguna?
- ¿Los puntos de corte por edad te parecen adecuados?
- ¿Se lo darías a un paciente o a un sujeto de uno de tus proyectos de investigación/intervención? Si no, ¿qué lo impide?
- ¿Qué le faltaría para ser relmnte útil en tu práctica?

Cualquier comentario, por menor que parezca, me sirve.

---

## Notas

- Si algo no funciona, dime **qué dispositivo y navegador** usabas.
- Si ves un aviso rojo diciendo que el diario no se guardará, es que has abierto un
  archivo descargado en vez de la dirección web. Usa siempre el enlace de arriba o el icono.
- La franja horaria del diario empieza a las 20:00 y cubre 24 horas.
- En la rejilla del móvil: desliza en horizontal para ver las 24 horas; la columna del  día queda fija.
