# SpecsDetector

**Download the latest version:** [SpecsDetector releases](https://github.com/Lieztz3r/SpecsDetector/releases/latest)

| Platform | Download | Requires |
|---|---|---|
| Android | [SpecsDetector.apk](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector.apk) | Android 8.0 or later |
| Windows | [SpecsDetector-Windows-x64.zip](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Windows-x64.zip) | Windows 10 or 11, 64-bit |
| Linux | [SpecsDetector-Linux-x64.tar.gz](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Linux-x64.tar.gz) | x86-64 with glibc 2.31+ (Ubuntu 20.04+, Debian 11+, Fedora 32+) |

SpecsDetector checks a phone or a computer with measured evidence instead of guesses. It shows what is happening, keeps a light history and runs repeatable tests that say whether a change really made things faster. When the data is not enough, it says "inconclusive" instead of guessing. No account, no ads, no analytics.

**Use only files attached to this official repository's releases.** `latest.json` lists the version, SHA-256 and size of every download so you can verify it.

## Android

1. On the phone, download [SpecsDetector.apk](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector.apk) and open it.
2. If Android asks, allow your browser to install unknown apps, then tap **Install**.

- **Now:** memory (including Android's low-memory flag), thermal status and headroom, battery temperature, battery saver and storage, with rules over the last minute that separate what was measured from what it does not prove.
- **History:** one sample every ~15 minutes, even with the app closed, summarised per day.
- **Lab:** a 5-minute sustained-performance test and an A-B-A comparison of a change (battery saver, charger, airplane mode, closing apps) with a 95 % interval. You apply the change; when Android exposes it, the app verifies it.
- **Verdict (indicative).**
- **Device:** every component of the phone (processor, RAM, storage, graphics, battery, display) with a **1-10 score diagnosed on the phone itself**: CPU on one core and on all cores, memory copy, forced writes to the internal storage and a GPU shader. The same scale as the computer app, so you can compare your phone with your PC. It runs by itself the first time (about 15 s with the app open) and gives phone-specific advice (battery, free space, temperature), since phone RAM and processors cannot be upgraded.

The APK is signed with the project key.

## Windows

1. Download [SpecsDetector-Windows-x64.zip](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Windows-x64.zip) and extract it anywhere. No installation needed.
2. Open `SpecsDetector\SpecsDetector.exe`. The dashboard opens in your browser at `http://127.0.0.1:8765`. Close the SpecsDetector console window to quit.

The executable is not commercially signed, so SmartScreen may show "Windows protected your PC". Check its SHA-256 against `latest.json`, then choose **More info → Run anyway**.

## Linux

```sh
curl -LO https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Linux-x64.tar.gz
tar -xzf SpecsDetector-Linux-x64.tar.gz
./SpecsDetector/SpecsDetector            # opens the dashboard in your browser
./SpecsDetector/crear-acceso.sh          # optional: adds it to the applications menu
```

Runs as a normal user; root is not needed. Without root, Linux does not expose memory modules and slots, so the app does not suggest RAM upgrades. User activity is read on X11 and GNOME; on other Wayland desktops it is reported as "no data".

## What the computer app does

- **Components:** the state of every part with a **1-10 score**, in the spirit of the Windows Experience Index: processor (cores, clocks, cache, socket, usage, temperature), RAM (modules, type, speed, slots, maximum supported, usage), storage (type, health, free space, speed), graphics (VRAM, driver, display), battery (health against its design capacity and cycles) and system (board, BIOS, uptime). The overall score is the weakest of processor, RAM and storage. **Every score is diagnosed on the computer running the app**, never estimated from the specifications: the diagnosis runs by itself the first time (waiting for a quiet moment), again if the hardware changes or after 30 days, and on demand. The GPU is measured with a shader in the dashboard's browser on the same computer. On Windows the official WinSAT scores are shown too, with their date.
- **Recommended upgrades:** ranked by priority, with the evidence behind each one: more RAM with the exact option for your computer (for example, "replace the 4 GB module with a 16 GB one → 24 GB"), an SSD, freeing space, a worn battery or temperature. When your measured use does not justify a purchase, it says so.
- **Live:** CPU, memory, pages read from disk, disk latency, CPU run queue and processor performance, grouped by what processes are for (apps, browsers, development, services, system, background). Rules work over a 60-second window, use hysteresis and abstain when data is missing; a full swap or page file is not reported as a problem without measured paging.
- **History:** friction minutes per hour over 7 days, capture gaps and episodes you save.
- **Lab:** an AB/BA experiment with its own test task. The plan is fixed with a seed before measuring, you approve the exact processes, and the only action is to lower the priority of SpecsDetector's own test workers and restore it, verified after every block. The result comes with a paired 95 % interval and a dossier that can be recomputed on any computer. Real actions stay disabled until **Verify this computer** passes.
- **Capacity (indicative):** real hardware inventory and an upgrade verdict that defaults to "don't buy" or "insufficient data". RAM prices from SoloTodo (Chile) only when you ask.
- **Optional AI:** if [Ollama](https://ollama.com) runs on the same computer, a local model can explain evidence that was already calculated. Without it, a deterministic summary is shown.

## Privacy

Measurements stay on the device. The computer app only listens on `127.0.0.1`, so no other device can connect, and it never touches processes it did not create. The only Internet request is to SoloTodo's public API over HTTPS, and only when you ask for prices. Read the [full privacy policy](PRIVACY.md).

This repository distributes ready-to-use releases and end-user information; it does not contain the development source code.

---

# SpecsDetector (español)

**Descarga la última versión:** [publicaciones de SpecsDetector](https://github.com/Lieztz3r/SpecsDetector/releases/latest)

| Plataforma | Descarga | Requisitos |
|---|---|---|
| Android | [SpecsDetector.apk](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector.apk) | Android 8.0 o posterior |
| Windows | [SpecsDetector-Windows-x64.zip](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Windows-x64.zip) | Windows 10 u 11 de 64 bits |
| Linux | [SpecsDetector-Linux-x64.tar.gz](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Linux-x64.tar.gz) | x86-64 con glibc 2.31 o superior (Ubuntu 20.04+, Debian 11+, Fedora 32+) |

SpecsDetector revisa un teléfono o un computador con evidencia medida en vez de suposiciones. Muestra lo que está pasando, guarda un historial liviano y hace pruebas repetibles que dicen si un cambio realmente mejoró algo. Cuando los datos no alcanzan, responde "inconcluso" en vez de adivinar. Sin cuentas, sin anuncios y sin analítica.

**Usa únicamente archivos adjuntos a las publicaciones oficiales de este repositorio.** `latest.json` contiene la versión, el SHA-256 y el tamaño de cada descarga para que puedas verificarla.

## Android

1. En el teléfono, descarga [SpecsDetector.apk](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector.apk) y ábrelo.
2. Si Android lo solicita, permite instalar aplicaciones desde el navegador y pulsa **Instalar**.

- **Ahora:** memoria (incluido el aviso de memoria baja de Android), estado y margen térmico, temperatura de la batería, ahorro de batería y almacenamiento. Las reglas sobre el último minuto separan lo medido de lo que no permite concluir.
- **Historial:** una muestra cada ~15 minutos, aunque la app esté cerrada, resumida por día.
- **Laboratorio:** prueba de rendimiento sostenido de 5 minutos y comparación A-B-A de un cambio (ahorro de batería, cargador, modo avión, cerrar apps) con intervalo del 95 %. Tú aplicas el cambio y, cuando Android lo permite, la app lo verifica.
- **Veredicto (orientativo).**
- **Equipo:** cada componente del teléfono (procesador, RAM, almacenamiento, gráficos, batería, pantalla) con un **puntaje de 1 a 10 diagnosticado en el mismo teléfono**: CPU en un núcleo y en todos, copia de memoria, escritura forzada en la memoria interna y un sombreador en la GPU. Es la misma escala que la app de computador, así que puedes comparar tu teléfono con tu PC. Se ejecuta solo la primera vez (unos 15 s con la app abierta) y da consejos propios de un teléfono (batería, espacio libre, temperatura), porque en un teléfono no se amplían la RAM ni el procesador.

El APK se firma con la clave del proyecto.

## Windows

1. Descarga [SpecsDetector-Windows-x64.zip](https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Windows-x64.zip) y descomprímelo donde quieras. No necesita instalación.
2. Abre `SpecsDetector\SpecsDetector.exe`. El panel se abre en el navegador en `http://127.0.0.1:8765`. Para salir, cierra la ventana de consola de SpecsDetector.

El ejecutable no tiene firma comercial, así que SmartScreen puede mostrar "Windows protegió su PC". Compara su SHA-256 con `latest.json` y elige **Más información → Ejecutar de todas formas**.

## Linux

```sh
curl -LO https://github.com/Lieztz3r/SpecsDetector/releases/latest/download/SpecsDetector-Linux-x64.tar.gz
tar -xzf SpecsDetector-Linux-x64.tar.gz
./SpecsDetector/SpecsDetector            # abre el panel en el navegador
./SpecsDetector/crear-acceso.sh          # opcional: lo agrega al menú de aplicaciones
```

Funciona como usuario normal; no necesita root. Sin root, Linux no informa los módulos ni las ranuras de memoria, así que la app no sugiere ampliar la RAM. La actividad del usuario se lee en X11 y en GNOME; en otros escritorios Wayland aparece como "sin dato".

## Qué hace la app de computador

- **Componentes:** el estado de cada pieza con un **puntaje de 1 a 10**, al estilo del índice de experiencia de Windows: procesador (núcleos, frecuencias, caché, socket, uso, temperatura), RAM (módulos, tipo, velocidad, ranuras, máximo admitido, uso), almacenamiento (tipo, salud, espacio libre, velocidad), gráficos (VRAM, driver, pantalla), batería (salud frente a su capacidad de fábrica y ciclos) y sistema (placa, BIOS, tiempo encendido). El puntaje general es el del más débil entre procesador, RAM y almacenamiento. **Todos los puntajes se diagnostican en el computador donde corre la app**, nunca se estiman por especificaciones: el diagnóstico se hace solo la primera vez (espera un momento tranquilo), otra vez si cambia el hardware o cada 30 días, y cuando lo pidas. La GPU se mide con un sombreador en el navegador del panel, en el mismo equipo. En Windows también se muestran los puntajes oficiales de WinSAT, con su fecha.
- **Mejoras recomendadas:** ordenadas por prioridad y con la evidencia de cada una: más RAM con la opción exacta para tu equipo (por ejemplo, "reemplazar el módulo de 4 GB por uno de 16 GB → 24 GB"), un SSD, liberar espacio, una batería desgastada o la temperatura. Cuando tu uso medido no justifica una compra, lo dice.
- **En vivo:** CPU, memoria, páginas leídas de disco, latencia de disco, cola de CPU y rendimiento del procesador, agrupados por función (aplicaciones, navegadores, desarrollo, servicios, sistema, segundo plano). Las reglas usan una ventana de 60 segundos con histéresis y se abstienen cuando faltan datos; un swap o archivo de paginación lleno no se informa como problema si no hay paginación medida.
- **Historial:** minutos de fricción por hora durante 7 días, huecos de captura y episodios que guardes.
- **Laboratorio:** experimento AB/BA con una tarea de prueba propia. El plan se fija con una semilla antes de medir, tú apruebas los procesos exactos y la única acción es bajar la prioridad de los workers de prueba de SpecsDetector y restaurarla, verificada después de cada bloque. El resultado trae un intervalo del 95 % emparejado y un expediente que se puede recalcular en cualquier equipo. Las acciones reales quedan bloqueadas hasta aprobar **Verificar este equipo**.
- **Capacidad (orientativo):** inventario real del hardware y un veredicto de ampliación que por defecto es "no compres" o "datos insuficientes". Precios de RAM en SoloTodo (Chile) solo si los pides.
- **IA opcional:** si [Ollama](https://ollama.com) corre en el mismo equipo, un modelo local puede explicar la evidencia ya calculada. Sin él, se muestra un resumen determinista.

## Privacidad

Las mediciones se quedan en el dispositivo. La app de computador solo escucha en `127.0.0.1`, así que ningún otro equipo puede conectarse, y nunca toca procesos que no haya creado. La única conexión a Internet es a la API pública de SoloTodo, por HTTPS, y solo cuando pides precios. Consulta la [política de privacidad completa](PRIVACY.md).

Este repositorio distribuye versiones listas para usar e información para usuarios; no contiene el código fuente de desarrollo.
