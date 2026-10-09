# Política de privacidad — SpecsDetector

*Vigente desde el 9 de octubre de 2026. La sección de Android rige sin cambios desde el 8 de octubre de 2026.*

SpecsDetector es una herramienta de diagnóstico para teléfonos Android y computadores con Windows o Linux. Funciona sin cuentas, sin anuncios y sin analítica. El desarrollador no recibe datos de ninguna de las versiones ni mantiene servidores o cuentas de usuarios. Esta política explica qué datos usa cada versión y adónde van.

## SpecsDetector para Android

### Datos que se quedan en tu teléfono

- **Mediciones.** Memoria disponible, aviso de memoria baja, estado y margen térmico, nivel y temperatura de la batería, si está cargando, ahorro de batería, almacenamiento libre y frecuencia de la CPU. Se leen con las interfaces normales de Android y con archivos del sistema de solo lectura que Android permite a cualquier app. No se leen tus archivos, contactos, mensajes, fotos, ubicación ni la lista de apps.
- **Historial.** Una muestra cada ~15 minutos se guarda durante 14 días en el almacenamiento privado de la app.
- **Expedientes del laboratorio.** Los resultados de cada prueba (tiempos, condiciones y cálculo) se guardan en el almacenamiento privado de la app.
- Nada de lo anterior se incluye en los respaldos en la nube de Android. Solo sale del teléfono si tú compartes un expediente con el botón **Compartir**. En ese caso eliges la app y el destino. El expediente incluye la marca, el modelo, el procesador, la RAM y la versión de Android, pero no identificadores personales.

### Servicios externos

| Servicio | Cuándo | Qué recibe |
|---|---|---|
| [SoloTodo](https://www.solotodo.cl) (API pública) | Solo cuando tocas **Ver opciones en Chile** en Veredicto | Una consulta HTTPS por la lista de teléfonos ordenada por precio y la dirección IP del teléfono. No se envían tus mediciones; los filtros de RAM y almacenamiento se aplican dentro de la app |

### Permisos

- **Internet:** solo para la consulta opcional a SoloTodo.
- **Ejecutar al iniciar:** para que la muestra periódica siga funcionando después de reiniciar el teléfono.

La app no pide ubicación, cámara, micrófono, contactos, almacenamiento compartido ni acceso de uso.

### Borrar los datos

Desinstalar la app borra todas las mediciones e historiales. También puedes borrarlos en Ajustes de Android → Apps → SpecsDetector → Almacenamiento → Borrar datos.

## SpecsDetector para Windows y Linux

### Datos que se quedan en tu computador

- **Mediciones.** Uso de CPU y memoria, contadores de presión del sistema (lectura de páginas, latencia y ocupación del disco, cola de CPU, rendimiento del procesador), batería y espacio en disco. Por cada proceso: nombre, uso de CPU, memoria y disco, y su categoría. No se guardan títulos de ventanas, líneas de comando ni rutas de archivos, y no se leen contenidos de archivos, historial de navegación ni pulsaciones de teclas. Para saber si estás usando el equipo, solo se lee el tiempo desde la última entrada del teclado o el mouse, nunca qué se escribió.
- **Inventario.** Fabricante y modelo del equipo, procesador, GPU, módulos de memoria (fabricante y número de pieza), discos y versión del sistema. No se leen números de serie.
- **Historial.** Las muestras detalladas se guardan 30 minutos; los resúmenes por minuto (incluidos los nombres de los procesos que más memoria usaron), 7 días, con un tope de 200 MB. Los episodios que guardes y los expedientes del laboratorio se conservan hasta que los borres.
- **Ubicación de los datos:** `%LOCALAPPDATA%\SpecsDetector\data` en Windows y `~/.local/share/specsdetector` en Linux.

### Red y procesos

- El panel solo escucha en `127.0.0.1` (este equipo). Otros equipos de tu red no pueden conectarse, y cada sesión del navegador usa un token que se genera al iniciar la app.
- El laboratorio crea sus propios procesos de prueba y solo cambia la prioridad de esos procesos. No modifica ni termina otros programas, el registro, los servicios ni los drivers.

### Servicios externos

| Servicio | Cuándo | Qué recibe |
|---|---|---|
| [SoloTodo](https://www.solotodo.cl) (API pública) | Solo cuando pides precios de RAM en Capacidad | Una consulta HTTPS con el tipo, el formato y el tamaño de módulo buscados, y la dirección IP del equipo. No se envían tus mediciones |
| [Ollama](https://ollama.com) (opcional) | Solo cuando pides una explicación y Ollama está instalado | Por defecto se usa en el mismo equipo (`127.0.0.1`) y nada sale de él. Si tú configuras un servidor remoto (`OLLAMA_HOST` y `SPECS_ALLOW_REMOTE_LLM=1`), ese servidor recibe el resumen de evidencia (cifras de las reglas, del laboratorio o de capacidad), y la app lo marca como "NO privada" |

### Borrar los datos

Cierra la app y borra su carpeta y la carpeta de datos indicada arriba.

## Cambios

Si esta política cambia, la nueva versión se publicará en este repositorio con su fecha.

---

# Privacy policy — SpecsDetector

*Effective October 9, 2026. The Android section is unchanged since October 8, 2026.*

SpecsDetector is a diagnostics tool for Android phones and Windows or Linux computers, with no accounts, ads or analytics. The developer receives no data from any version and runs no servers or user accounts.

**Android.** Measurements (memory, thermal status and headroom, battery level and temperature, charging, battery saver, free storage, CPU frequency), the 14-day history and lab results are stored only in the app's private storage and are excluded from Android backups. They leave the phone only if you share a lab dossier yourself. The only network request is an optional HTTPS query to SoloTodo's public API when you tap the prices button; it receives the request and your IP address, not your measurements. Permissions: Internet (that optional query) and run at startup (to keep the periodic sample after a reboot). Uninstalling the app deletes all its data.

**Windows and Linux.** The app measures CPU, memory, system pressure counters, battery and disk space, plus each process's name, CPU, memory and disk use. It never stores window titles, command lines or file paths, and never reads file contents, browsing history or keystrokes; for user activity it only reads the time since the last keyboard or mouse input. The hardware inventory excludes serial numbers. Detailed samples are kept for 30 minutes and per-minute summaries (including the names of the processes using the most memory) for 7 days, capped at 200 MB, in `%LOCALAPPDATA%\SpecsDetector\data` (Windows) or `~/.local/share/specsdetector` (Linux). The dashboard only listens on `127.0.0.1` with a per-launch session token. The lab only changes the priority of processes it created itself. Network use: SoloTodo's public API over HTTPS only when you ask for RAM prices (it receives the module type and size searched and your IP address), and Ollama only if you installed it — on the same computer by default, or on a remote server only if you configure one, in which case that server receives the evidence summary and the app labels it "NOT private". To delete everything, close the app and delete its folder and the data folder.
