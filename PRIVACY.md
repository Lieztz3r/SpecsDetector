# Política de privacidad — SpecsDetector para Android

*Vigente desde el 8 de octubre de 2026.*

SpecsDetector es una herramienta de diagnóstico del teléfono. Funciona sin cuentas, sin anuncios, sin analítica y sin Google Play Services. Esta política explica qué datos usa la app y adónde van.

## Datos que se quedan en tu teléfono

- **Mediciones.** Memoria disponible, aviso de memoria baja, estado y margen térmico, nivel y temperatura de la batería, si está cargando, ahorro de batería, almacenamiento libre y frecuencia de la CPU. Se leen con las interfaces normales de Android y con archivos del sistema de solo lectura que Android permite a cualquier app. No se leen tus archivos, contactos, mensajes, fotos, ubicación ni la lista de apps.
- **Historial.** Una muestra cada ~15 minutos se guarda durante 14 días en el almacenamiento privado de la app.
- **Expedientes del laboratorio.** Los resultados de cada prueba (tiempos, condiciones y cálculo) se guardan en el almacenamiento privado de la app.
- Nada de lo anterior se incluye en los respaldos en la nube de Android. Solo sale del teléfono si tú compartes un expediente con el botón **Compartir**. En ese caso eliges la app y el destino. El expediente incluye la marca, el modelo, el procesador, la RAM y la versión de Android, pero no identificadores personales.

## Servicios externos que usa la app

| Servicio | Cuándo | Qué recibe |
|---|---|---|
| [SoloTodo](https://www.solotodo.cl) (API pública) | Solo cuando tocas **Ver opciones en Chile** en Veredicto | Una consulta HTTPS por la lista de teléfonos ordenada por precio y la dirección IP del teléfono. No se envían tus mediciones; los filtros de RAM y almacenamiento se aplican dentro de la app |

El desarrollador no recibe datos de la app ni mantiene servidores o cuentas de usuarios.

## Permisos

- **Internet:** solo para la consulta opcional a SoloTodo.
- **Ejecutar al iniciar:** para que la muestra periódica siga funcionando después de reiniciar el teléfono.

La app no pide ubicación, cámara, micrófono, contactos, almacenamiento compartido ni acceso de uso.

## Borrar los datos

Desinstalar la app borra todas las mediciones e historiales. También puedes borrarlos en Ajustes de Android → Apps → SpecsDetector → Almacenamiento → Borrar datos.

## Cambios

Si esta política cambia, la nueva versión se publicará en este repositorio con su fecha.

---

# Privacy policy — SpecsDetector for Android

*Effective October 8, 2026.*

SpecsDetector is a phone diagnostics tool with no accounts, ads, analytics or Google Play Services. Measurements (memory, thermal status and headroom, battery level and temperature, charging, battery saver, free storage, CPU frequency), the 14-day history and lab results are stored only in the app's private storage and are excluded from Android backups. They leave the phone only if you share a lab dossier yourself. The only network request is an optional HTTPS query to SoloTodo's public API when you tap the prices button; it receives the request and your IP address, not your measurements. Permissions: Internet (that optional query) and run at startup (to keep the periodic sample after a reboot). Uninstalling the app deletes all its data.
