# SpecsDetector

**Install the latest version:** [Download SpecsDetector](https://github.com/Lieztz3r/SpecsDetector/releases/latest)

SpecsDetector checks your Android phone with measured evidence instead of guesses. It shows memory, temperature, battery and storage, keeps a light history, and runs repeatable tests: whether the phone loses performance when it heats up, and whether a change (battery saver, charger, airplane mode, closing apps, removing the case) really makes it faster or slower. When the data is not enough, it says so.

## Install

1. On Android, download [SpecsDetector.apk](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector.apk) and open it.
2. If Android asks, allow your browser to install unknown apps.
3. Tap **Install**.

Requires Android 8.0 (Android 26) or later. No account, no ads, no analytics.

**Use only APKs attached to this official repository's releases.** APKs are signed with the project key; `latest.json` includes the app version and the SHA-256 of the APK so you can verify the download.

## What it does

- **Now:** memory (including Android's low-memory flag and the kernel's MemAvailable), thermal status and headroom, battery temperature, battery saver, storage. Rules over the last minute separate what was measured from what it does not prove.
- **History:** one sample every ~15 minutes, even with the app closed, summarised per day (low-memory time, thermal limiting, battery drain per hour).
- **Lab:** a 5-minute sustained-performance test and an A-B-A comparison of a change, with a 95 % interval. The app never changes your settings; you apply the change and, when Android exposes it, the app verifies it.
- **Verdict (indicative):** by default "don't buy" or "insufficient data". Phone prices from SoloTodo (Chile) only when you ask.
- **Device:** full specs of the phone.

## Privacy

Measurements stay on the phone and are not included in Android backups. The only Internet request is to SoloTodo's public API, over HTTPS, and only when you tap the prices button. Read the [full privacy policy](PRIVACY.md).

This repository distributes ready-to-install releases and end-user information; it does not contain the development source code.

---

# SpecsDetector (español)

**Instala la última versión:** [Descargar SpecsDetector](https://github.com/Lieztz3r/SpecsDetector/releases/latest)

SpecsDetector revisa tu teléfono Android con evidencia medida en vez de suposiciones. Muestra memoria, temperatura, batería y almacenamiento, guarda un historial liviano y hace pruebas repetibles: si el teléfono pierde rendimiento cuando se calienta y si un cambio (ahorro de batería, cargador, modo avión, cerrar apps, quitar la funda) realmente lo hace más rápido o más lento. Cuando los datos no alcanzan, lo dice.

## Instalación

1. En tu teléfono Android, descarga [SpecsDetector.apk](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector.apk) y ábrelo.
2. Si Android lo solicita, permite instalar aplicaciones desde el navegador.
3. Pulsa **Instalar**.

Requiere Android 8.0 (Android 26) o posterior. Sin cuentas, sin anuncios y sin analítica.

**Usa únicamente APK adjuntos a las publicaciones oficiales de este repositorio.** Los APK se firman con la clave del proyecto; `latest.json` contiene la versión y el SHA-256 del APK para que puedas verificar la descarga.

## Qué hace

- **Ahora:** memoria (incluido el aviso de memoria baja de Android y el MemAvailable del kernel), estado y margen térmico, temperatura de la batería, ahorro de batería y almacenamiento. Las reglas sobre el último minuto separan lo medido de lo que no permite concluir.
- **Historial:** una muestra cada ~15 minutos, aunque la app esté cerrada, resumida por día (tiempo con memoria baja, limitación térmica y gasto de batería por hora).
- **Laboratorio:** prueba de rendimiento sostenido de 5 minutos y comparación A-B-A de un cambio, con intervalo del 95 %. La app nunca cambia tus ajustes: tú aplicas el cambio y, cuando Android lo permite, la app lo verifica.
- **Veredicto (orientativo):** por defecto "no compres" o "datos insuficientes". Precios de teléfonos en SoloTodo (Chile) solo si los pides.
- **Equipo:** las especificaciones completas del teléfono.

## Privacidad

Las mediciones se quedan en el teléfono y no se incluyen en los respaldos de Android. La única conexión a Internet es a la API pública de SoloTodo, por HTTPS, y solo cuando tocas el botón de precios. Consulta la [política de privacidad completa](PRIVACY.md).

Este repositorio distribuye versiones listas para instalar e información para usuarios; no contiene el código fuente de desarrollo.
