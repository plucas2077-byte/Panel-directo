# 🏐 Panel en directo para DataVolley + Banquillo en el móvil

Estadísticas de voleibol **en directo** mientras scouteas un partido con **DataVolley 4**, en el ordenador y en el **móvil del entrenador**, sin instalar ningún programa.

Creado por Pedro (CV Voleibol Barberà) para usarlo en partidos reales. Es gratis y cualquiera puede usarlo con su equipo.

```
 Ordenador del scout                        Internet                     Móvil del entrenador
┌───────────────────────┐            ┌──────────────────┐            ┌──────────────────────┐
│ DataVolley 4          │            │                  │            │                      │
│   ↓ (lee los datos)   │  ───────►  │  Supabase        │  ───────►  │  banquillo.html      │
│ panel-directo.html    │   envía    │  (buzón gratuito)│   recoge   │  (página web)        │
└───────────────────────┘            └──────────────────┘            └──────────────────────┘
```

---

## Índice

1. [Qué hace](#1-qué-hace)
2. [Qué hay en este proyecto](#2-qué-hay-en-este-proyecto)
3. [Qué necesitas](#3-qué-necesitas)
4. [Cómo descargar el proyecto desde GitHub](#4-cómo-descargar-el-proyecto-desde-github)
5. [Usar el panel en tu ordenador (sin banquillo)](#5-usar-el-panel-en-tu-ordenador-sin-banquillo)
6. [Compartir con el banquillo: preparación (una sola vez)](#6-compartir-con-el-banquillo-preparación-una-sola-vez)
7. [El día del partido, paso a paso](#7-el-día-del-partido-paso-a-paso)
8. [Cómo se usa el banquillo en el móvil](#8-cómo-se-usa-el-banquillo-en-el-móvil)
9. [Personalizar lo que se ve](#9-personalizar-lo-que-se-ve)
10. [Actualizar a una versión nueva](#10-actualizar-a-una-versión-nueva)
11. [Solución de problemas](#11-solución-de-problemas)
12. [Seguridad y privacidad](#12-seguridad-y-privacidad)
13. [Preguntas frecuentes](#13-preguntas-frecuentes)
14. [Glosario para no perderse](#14-glosario-para-no-perderse)
15. [Créditos y licencias](#15-créditos-y-licencias)

---

## 1. Qué hace

**En el ordenador del scout (`panel-directo.html`):**

- Lee el partido de DataVolley y muestra al momento:
  - marcador y evolución del set;
  - side-out y break, nuestros y del rival;
  - rotaciones;
  - jugadores en pista;
  - tiempos muertos y cambios;
  - avisos («parcial 4–0 del rival», «colocador en 2: solo 3/14 en side-out»…);
  - estadísticas por jugador de saque, recepción, ataque, bloqueo, defensa y colocación.
- Se actualiza solo **cada vez que guardas** en DataVolley. Con el modo «Detectar el partido en directo» se actualiza **sin necesidad de guardar**.
- Reconoce la **alineación inicial** y la **rotación** en cuanto la marcas en DataVolley, antes del primer punto.
- Compara cada set con el anterior, con flechas ▲▼.

**En el móvil del entrenador (`banquillo.html`):**

- Ve lo mismo, adaptado al móvil, actualizado en 1–2 segundos.
- Tiene **plantillas** preparadas:
  - **Jose:** recepción, saque y jugadores en pista.
  - **Edurne:** estado del partido y ataque individual por posiciones.
  - **Rápida:** todo en una sola pantalla, sin deslizar.
  - **Lista.**
- Tiene un **chat privado** entre el scout y el banquillo, con mensajes rápidos.
- Puede **mantener la pantalla encendida** y usar **modo oscuro**.
- Puede **descargar el .dvw** del partido.

---

## 2. Qué hay en este proyecto

| Archivo | Para qué sirve | ¿Dónde se usa? |
|---|---|---|
| `panel-directo.html` | El panel principal. Lee DataVolley y muestra las estadísticas. | En el **ordenador** donde está DataVolley (Chrome o Edge). |
| `banquillo.html` | La página para el móvil del entrenador. | Publicada en internet con **GitHub Pages** y abierta desde el **móvil**. |
| `index.html` | Redirige la dirección principal del sitio a `banquillo.html`, para que no salga el error 404. | GitHub Pages (no hay que tocarlo). |
| `supabase/supabase-panel-directo.sql` | Las instrucciones para crear el «buzón» en Supabase. | Se pega **una sola vez** en Supabase. |
| `README.md` | Esta guía. | Para leer. |

> Cada `.html` es **un único archivo autónomo**: lleva dentro todo lo que necesita (diseño, código y librerías). No hay que instalar nada, ni compilar, ni usar la terminal.

---

## 3. Qué necesitas

### Para usar solo el panel en el ordenador

- Un ordenador con **Windows** y **DataVolley 4**. Vale cualquier edición, incluida *Data Volley 4 Media*.
- **Google Chrome** o **Microsoft Edge**, actualizados.
  > ⚠️ Firefox y Safari **no sirven para el panel**, porque no permiten que una página vigile un archivo del ordenador. El banquillo del móvil sí funciona en cualquier navegador.

### Para compartir con el móvil del entrenador

- Conexión a internet en el ordenador. Vale con compartir datos desde un móvil.
- Una cuenta gratuita en **[Supabase](https://supabase.com)**.
- Una cuenta gratuita en **[GitHub](https://github.com)**. Si estás leyendo esto en GitHub, ya sabes lo que es.
- Un móvil con cualquier navegador (Safari, Chrome…), con datos o wifi.

**Coste: 0 €.** Los planes gratuitos de Supabase y GitHub dan de sobra para esto.

---

## 4. Cómo descargar el proyecto desde GitHub

Elige **una** de estas tres formas. La **A** es la más fácil.

### Opción A — Descargar el ZIP (recomendada, sin conocimientos técnicos)

1. En la página principal de este repositorio en GitHub, busca el botón verde **`<> Code`**, arriba a la derecha de la lista de archivos.
2. Pulsa **`<> Code`** → **Download ZIP**.
3. Se descarga un archivo llamado algo como `panel-en-directo-voleibol-main.zip` en tu carpeta **Descargas**.
4. Ve a **Descargas**, haz **clic derecho** sobre el ZIP → **Extraer todo…** → **Extraer**.
   > ⚠️ **No abras los archivos desde dentro del ZIP sin extraerlo.** El panel no podría guardar sus permisos.
5. Mueve la carpeta extraída a un sitio fácil de encontrar, por ejemplo **Documentos** o el **Escritorio**.

### Opción B — Con Git (si ya usas Git)

```bash
git clone https://github.com/USUARIO/NOMBRE-DEL-REPOSITORIO.git
```

Cambia `USUARIO` y `NOMBRE-DEL-REPOSITORIO` por los de esta página: los ves en la barra de direcciones del navegador. Para actualizar más adelante: `git pull`.

### Opción C — Descargar un solo archivo

1. Pulsa sobre el archivo en GitHub, por ejemplo `panel-directo.html`.
2. Arriba a la derecha del contenido, pulsa el icono **⬇ Download raw file**.

### Opción D — Hacer tu propia copia en GitHub (*Fork*), para tener tu propio banquillo

Hazlo si quieres publicar **tu** banquillo sin subir archivos a mano (ver el [paso 6.2](#62-publicar-el-banquillo-en-internet-con-github-pages-5-minutos)):

1. Inicia sesión en GitHub.
2. Pulsa **Fork** (arriba a la derecha) → **Create fork**.
3. Tendrás una copia en `https://github.com/TU-USUARIO/NOMBRE-DEL-REPOSITORIO`.

---

## 5. Usar el panel en tu ordenador (sin banquillo)

### 5.1 Abrir el panel

1. Entra en la carpeta que extrajiste.
2. Haz **doble clic** en `panel-directo.html`.
   - Si se abre con un navegador que no es Chrome ni Edge: **clic derecho** → **Abrir con** → **Google Chrome** (o **Microsoft Edge**).
   - También puedes arrastrar el archivo encima de una ventana de Chrome.
3. Verás la pantalla de bienvenida **«Panel en directo»**.

> 💡 Consejo: en Chrome, pulsa **Ctrl + D** para guardarlo en Favoritos y abrirlo rápido el día del partido.

### 5.2 Elegir de dónde leer el partido

En la pantalla de bienvenida hay tres formas:

| Botón | Qué hace | Cuándo usarlo |
|---|---|---|
| **Elegir el archivo del partido (.dvw)** | Vigila un `.dvw` concreto y se actualiza **cada vez que pulsas Guardar** en DataVolley. | La opción más sencilla y segura. |
| **Seguir una carpeta (el .dvw guardado más reciente)** | Vigila una carpeta y abre siempre el último `.dvw` que se haya guardado. | Si guardas cada partido con un nombre nuevo. |
| **🔎 Detectar el partido en directo en la carpeta de DataVolley** | Lee los datos que DataVolley escribe por dentro mientras scouteas, **sin tener que guardar**. | Si quieres que se actualice solo en cada punto. |

La primera vez, Chrome te preguntará si permites que la página **vea** (y, si hace falta, **edite**) los archivos. Pulsa **Ver archivos** / **Permitir**. La página solo los **lee**: nunca modifica tus partidos.

La próxima vez que abras el panel aparecerá **«Seguir con …»** para continuar con el mismo archivo o carpeta con un solo clic.

### 5.3 El modo «Detectar el partido en directo» (DataVolley 4 Media)

1. Pulsa **🔎 Detectar el partido en directo en la carpeta de DataVolley**.
2. Elige **la carpeta principal de DataVolley**: la que contiene las subcarpetas **`Data`**, **`Log`** y **`Multimedia`**. Suele llamarse `Data Volley 4 Media` o `Data Volley 4`.
3. El panel revisa los archivos cada pocos segundos:
   - Al **abrir un partido y marcar los jugadores y los titulares** en DataVolley, el panel lee `Data/TElenco.DB` (la plantilla: dorsal, nombre, posición y alineación inicial de cada set) y `Data/TNote.DB` (los nombres de los equipos y los sets).
   - Mientras scouteas, va leyendo los puntos.
4. Antes del primer punto de cada set, en **«En pista ahora»**, pulsa el equipo que **saca primero**. El sacador se marcará en la pista y en el móvil del banquillo. En cuanto scouteas el primer saque, se hace solo.
5. Si no detecta tu partido, pulsa **Copiar informe para Claude**. Copia un informe técnico con los archivos que han cambiado y lo que se ha leído de cada uno, para poder ajustarlo.

> Los jugadores se identifican siempre por **equipo + dorsal**. Si dos se apellidan igual, se distinguen con la inicial: «Avilez E.» y «Avilez L.».

### 5.4 Probarlo sin partido real

En la pantalla de bienvenida, usa **«Simular con un partido guardado»** y elige cualquier `.dvw` que ya tengas. El panel lo reproduce punto a punto, como si fuera en directo, y puedes elegir la velocidad (1×, 2×…). Así puedes practicar antes del primer partido.

### 5.5 Lo que ves en el panel

- **Arriba:** **📊 Estadísticas** (páginas por fundamento, nuestras y del rival), **⚙ Personalizar**, **Set actual / Partido**, **Nosotros:** (para elegir cuál es tu equipo), **Compartir con el banquillo** y **Cambiar archivo**.
- **Bloques:**
  - marcador y evolución;
  - en pista ahora;
  - tiempos muertos y cambios;
  - comparación con el set anterior;
  - side-out y break;
  - rotaciones;
  - avisos;
  - jugadores;
  - rival;
  - origen de los puntos;
  - fases;
  - últimos puntos.

---

## 6. Compartir con el banquillo: preparación (una sola vez)

Se hace **una vez** y sirve para todos los partidos. Se tarda unos 15–20 minutos.

### 6.1 Crear el «buzón» en Supabase (10 minutos)

Supabase es una base de datos en internet. Aquí funciona como un buzón: el ordenador deja el partido y el móvil lo recoge.

1. Entra en **[supabase.com](https://supabase.com)** → **Start your project** → inicia sesión, por ejemplo con tu cuenta de GitHub.
2. Pulsa **New project** y rellena:
   - **Name:** `panel-directo` (o el que quieras).
   - **Database password:** cualquiera. Guárdala, aunque para esto no la vas a necesitar.
   - **Region:** una de Europa, por ejemplo *West EU (Paris)* o *Central EU (Frankfurt)*.
   - Pulsa **Create new project** y espera 1–2 minutos.
3. En el menú de la izquierda, entra en **SQL Editor** → **New query**.
4. Abre el archivo `supabase/supabase-panel-directo.sql` de este proyecto con el **Bloc de notas** (clic derecho → *Abrir con* → *Bloc de notas*). Copia **todo** el texto (**Ctrl + A**, **Ctrl + C**), pégalo en Supabase (**Ctrl + V**) y pulsa **Run**.
   - Debe salir **«Success. No rows returned»**.
   - Si sale un error, comprueba que has copiado el archivo **entero**, desde la primera línea hasta la última.
5. Copia **dos datos** desde **Project Settings** (⚙ abajo a la izquierda) → **API Keys**, o desde el botón **Connect** de arriba:
   - **Project URL:** algo como `https://abcdxyz.supabase.co`. ¡Ojo, es **supabase.co**, sin la «m» final!
   - **Clave pública:** la llamada **anon public** o **publishable**. Empieza por `eyJ…` o por `sb_publishable_…`.

> ⚠️ **NUNCA uses ni compartas la clave `service_role` ni la `secret`.** Esas dan control total de la base de datos. Solo hace falta la **pública**.

### 6.2 Publicar el banquillo en internet con GitHub Pages (5 minutos)

El móvil necesita una **dirección web** (`https://…`) para abrir el banquillo; no basta con enviarle el archivo. GitHub Pages la da gratis.

**Si hiciste Fork (opción D del paso 4)**, ve directamente al punto 3.

1. En GitHub: botón **+** (arriba a la derecha) → **New repository**.
   - **Repository name:** por ejemplo `panel-banquillo`.
   - Marca **Public**.
   - Pulsa **Create repository**.
2. En el repositorio nuevo, pulsa **uploading an existing file**. Arrastra **`banquillo.html`** e **`index.html`** y pulsa **Commit changes**.
   > ⚠️ El archivo tiene que llamarse **exactamente `banquillo.html`**, todo en minúsculas, sin espacios ni números. Si el navegador lo descargó como `banquillo (1).html`, **renómbralo antes de subirlo**. Si no, verás el error 404.
3. Ve a **Settings** (pestaña del repositorio) → **Pages** (menú de la izquierda):
   - **Source:** *Deploy from a branch*.
   - **Branch:** `main` y carpeta `/ (root)`.
   - Pulsa **Save**.
4. Espera **1–3 minutos**. Puedes ver el progreso en la pestaña **Actions**: cuando salga el ✅ verde, está listo.
5. Tu banquillo estará en:
   ```
   https://TU-USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/banquillo.html
   ```
   Por ejemplo: `https://mi-club.github.io/panel-banquillo/banquillo.html`.
6. **Comprueba** que funciona: abre esa dirección en el móvil. Debe aparecer **«Banquillo»** pidiendo un enlace. Si sale **404**, mira la [solución de problemas](#11-solución-de-problemas).

> `banquillo.html` **no contiene ninguna clave**. La dirección de tu Supabase y el código del partido viajan dentro del enlace o del QR que se genera cada día.

### 6.3 Conectar el panel con Supabase y con tu banquillo (2 minutos)

1. Abre `panel-directo.html` en Chrome o Edge y elige tu archivo o carpeta (paso 5.2).
2. Pulsa **Compartir con el banquillo** → **Configuración** y rellena:
   - **Project URL:** el de Supabase (paso 6.1.5).
   - **Clave pública «anon public»:** la clave pública (paso 6.1.5).
   - **Dirección de la página del banquillo:** la del paso 6.2.5.
3. Pulsa **Probar conexión**. Debe salir todo en verde ✓. Si algo sale en rojo, el mensaje explica qué falla.
4. Pulsa **Guardar**. Queda guardado en ese navegador para todos los partidos siguientes.

---

## 7. El día del partido, paso a paso

**Antes del partido (en casa):**

- Entra en supabase.com y comprueba que tu proyecto no está **pausado**. El plan gratuito lo pausa tras unos días sin uso; si lo está, pulsa **Restore**.

**En el pabellón:**

1. Conecta el ordenador a internet (wifi o datos compartidos desde el móvil).
2. Abre DataVolley y crea o abre el partido:
   - En modo **archivo** o **carpeta**: **guárdalo una vez** para que exista el `.dvw`.
   - En modo **detectar**: basta con abrir el partido y marcar jugadores y titulares.
3. Abre `panel-directo.html` → **Seguir con …** (o elige el archivo o la carpeta).
4. Pulsa **Compartir con el banquillo** → **Empezar a compartir «…»**. Aparecen un **código QR** y un código del tipo `BAR-7F3K-9QXM`.
5. El entrenador **escanea el QR con la cámara del móvil**. Se le abre el banquillo con el partido.
   - También puedes pulsar **Copiar enlace** y enviárselo por WhatsApp.
6. Scoutea como siempre. El móvil se actualiza en 1–2 segundos:
   - en modo archivo o carpeta, cada vez que pulsas **Guardar** en DataVolley;
   - en modo detectar, solo.

**Cómo saber que funciona:**

- **En el ordenador:** el botón pasa a **Banquillo conectado** y en la ventana de compartir pone *«✓ Enviado a las 18:42 · versión 12»*.
- **En el móvil:** arriba sale el marcador, el set, un punto verde y la hora de la última actualización.

**Al terminar:** pulsa **Dejar de compartir y borrar del servidor**, o déjalo compartido para que el entrenador lo revise después.

> Si se corta internet, el panel sigue funcionando en el ordenador y vuelve a enviar los datos solo cuando vuelve la conexión.

---

## 8. Cómo se usa el banquillo en el móvil

- **Abajo hay 5 pestañas:** **Resumen** · **Pista** · **Nosotros** · **Rival** · **Mensajes**.
- **En Resumen, arriba**, se elige la plantilla:
  - **Jose:**
    - recepción individual nuestra y del rival (% positiva);
    - saque por jugador (si tocas un jugador, ves sus **direcciones de saque**);
    - los 12 jugadores **en pista** con el colocador y el sacador marcados.
  - **Edurne:**
    - **estado del partido**: side-out, break, ataque, recepción, puntos directos y errores regalados, con ▲▼ en lo que vamos mejor o peor;
    - **ataque individual**, con barras en la misma escala para comparar jugadores; se puede ver **por posición** o en **ranking**.
  - **Rápida:** lo más importante **en una sola pantalla, sin deslizar**.
  - **Lista:** todos los bloques uno debajo de otro.
- **Set / Partido** (arriba a la derecha): elige si los datos son del set actual o de todo el partido.
- **Toca cualquier recuadro** para abrir el **detalle** desde abajo. Se cierra con la ✕, tocando fuera o deslizando hacia abajo.
- **Menú ⋯** (arriba a la derecha):
  - elegir nuestro equipo;
  - **Al abrir el banquillo**: qué plantilla sale al abrir;
  - mantener la pantalla encendida;
  - modo claro u oscuro;
  - actualizar ahora;
  - descargar el `.dvw`.
- **Mensajes:** chat privado entre scout y banquillo, con mensajes rápidos. En el ordenador está en el botón **💬 Mensajes**.

> 💡 **Tenerlo como una app:**
> - **iPhone:** en Safari pulsa **Compartir** → **Añadir a pantalla de inicio**.
> - **Android:** en Chrome, menú **⋮** → **Añadir a pantalla de inicio**.
>
> El móvil recuerda el último partido, así que si cierras la página sigue conectado al volver a abrirla.

---

## 9. Personalizar lo que se ve

En el panel (**⚙ Personalizar**) y en el banquillo (menú **⋯** → *Elegir qué datos y gráficos ver*) puedes:

- usar **configuraciones rápidas**: *Completo*, *Esencial*, *Banquillo, letra grande* o *Todos los gráficos*;
- **activar o desactivar** cada bloque, cambiar su **orden** (↑ ↓) y su **ancho**;
- cambiar el **tamaño** de todo;
- elegir qué **avisos** salen y qué **columnas** tiene la tabla de jugadores.

Cada dispositivo guarda su propia configuración. **Restablecer lo de fábrica** la deja como al principio.

---

## 10. Actualizar a una versión nueva

1. Descarga el proyecto otra vez (paso 4) o solo los archivos que hayan cambiado.
2. **En el ordenador:** reemplaza tu `panel-directo.html` por el nuevo. La configuración de Supabase **no se pierde**, porque está guardada en el navegador.
3. **En tu repositorio de GitHub Pages:** entra en `banquillo.html` → **…** → **Delete file**, y sube el nuevo con **Add file → Upload files**. Más fácil: arrastra el nuevo y GitHub lo reemplaza si tiene **el mismo nombre exacto**. Pulsa **Commit changes**.
4. Espera 1–3 minutos (pestaña **Actions** ✅). **El enlace y el QR siguen siendo los mismos.**
5. Si el móvil sigue mostrando la versión antigua, recarga la página. Si no basta, cierra la pestaña y vuelve a abrir el enlace.

> Si una versión nueva cambia el archivo `supabase-panel-directo.sql`, vuelve a ejecutarlo en Supabase (paso 6.1.3–4). Se puede ejecutar varias veces sin problema.

---

## 11. Solución de problemas

| Problema | Causa probable | Solución |
|---|---|---|
| **El móvil muestra «404 File not found»** | En GitHub, el archivo no se llama exactamente `banquillo.html`, o aún no se ha publicado. | Comprueba el nombre exacto, en minúsculas y sin `(1)`. Espera al ✅ en **Actions**. Comprueba que la dirección del panel (6.3) coincide letra por letra con tu usuario y repositorio. |
| Los botones de elegir archivo están **desactivados** o dan error | El navegador no es Chrome ni Edge, o el panel se ha abierto dentro de otra página o de una vista previa. | Abre `panel-directo.html` directamente con Chrome o Edge desde tu carpeta. |
| El panel no se actualiza | En modo archivo, DataVolley solo escribe el `.dvw` al **Guardar**. | Pulsa Guardar en DataVolley, o usa el modo **🔎 Detectar el partido en directo**. |
| «Todavía no se detecta ningún partido» | La carpeta elegida no es la principal de DataVolley, o aún no se ha marcado nada. | Elige la carpeta que contiene `Data`, `Log` y `Multimedia`. Abre el partido y marca titulares. Si sigue, pulsa **Copiar informe para Claude**. |
| Chrome pregunta permisos cada vez | Es normal en algunos equipos. | Pulsa **Permitir**. Con **Seguir con …** es un solo clic. |
| «Falta preparar la base de datos» | El SQL no se ejecutó en Supabase. | Repite el paso 6.1.3–4. |
| «La clave pública no es correcta» | Se ha copiado otra clave o falta un trozo. | Copia otra vez la clave **anon public / publishable** en **Configuración**. |
| «Sin conexión» | No hay internet, o el Project URL está mal escrito (por ejemplo `suabase.co`). | Revisa la conexión y el Project URL. Pulsa **Probar conexión**: indica el motivo exacto. |
| El móvil dice «Esperando a que el ordenador empiece a compartir» | En el ordenador no se ha pulsado **Empezar a compartir**, o el QR es de otro partido. | Pulsa **Empezar a compartir** y vuelve a escanear el QR. |
| Supabase dice **Project paused** | El plan gratuito lo pausa tras días sin uso. | supabase.com → tu proyecto → **Restore**. Hazlo el día antes. |
| Los nombres salen como códigos (`243414252455241…`) | Versión antigua del panel. | Actualiza a la última versión (apartado 10). |
| No se marca quién saca antes del primer punto | DataVolley no guarda en esos archivos quién saca primero. | Pulsa el equipo en **«Saca primero»** dentro de *En pista ahora*. Tras el primer saque es automático. |
| En el iPhone los desplegables no se ven bien | Versión antigua del banquillo. | Actualiza `banquillo.html` en GitHub (apartado 10). |
| La pantalla del móvil se apaga | El móvil no permite mantenerla encendida desde una web. | Menú ⋯ → *Mantener la pantalla encendida*. Si no basta, sube el tiempo de bloqueo en los ajustes del móvil. |

---

## 12. Seguridad y privacidad

- **Tus partidos no salen del ordenador** salvo que pulses **Empezar a compartir**.
- En Supabase, la tabla es **privada**: nadie puede listar los partidos. Solo quien tiene el **código del partido** (que va dentro del QR) puede leerlo.
- Solo **tu ordenador**, con una clave secreta que genera solo y que nunca se muestra, puede **publicar o borrar** un partido.
- `banquillo.html` y este repositorio **no contienen ninguna clave**. Tu Project URL y tu clave pública viajan dentro del enlace del partido; por eso conviene compartir el QR **solo con tu cuerpo técnico**.
- La clave **anon / publishable** está pensada para ir en páginas públicas. **Nunca** uses la `service_role` ni la `secret`.
- El chat tiene un límite de mensajes por minuto y de longitud, para evitar abusos.

---

## 13. Preguntas frecuentes

**¿Tengo que instalar algo?**
No. Solo Chrome o Edge en el ordenador. Todo lo demás son páginas web y cuentas gratuitas.

**¿Funciona con Mac?**
El panel funciona en Chrome o Edge de Mac, pero DataVolley 4 es un programa de Windows. Lo normal es usar el panel en el mismo ordenador Windows de DataVolley.

**¿Puede haber varios entrenadores mirando a la vez?**
Sí. Todos los que escaneen el QR ven el partido a la vez.

**¿Puedo usarlo sin internet?**
El **panel** sí, en el ordenador. El **banquillo** del móvil necesita que el ordenador y el móvil tengan internet.

**¿Modifica mis archivos de DataVolley?**
No. Solo los **lee**.

**¿Sirve para otro club?**
Sí. El panel detecta qué equipo es «Nosotros» (por defecto busca *Barberà*). Elige tu equipo en **Nosotros:** (panel) o en el menú **⋯** (banquillo).

**¿Cuánto ocupa en Supabase?**
Muy poco: un `.dvw` pesa menos de 1 MB. El plan gratuito tiene espacio para miles de partidos.

---

## 14. Glosario para no perderse

| Palabra | Qué significa |
|---|---|
| **Repositorio** | La «carpeta» del proyecto en GitHub. |
| **Fork** | Hacer tu propia copia de un repositorio en tu cuenta de GitHub. |
| **Commit** | Guardar un cambio en GitHub (por ejemplo, después de subir un archivo). |
| **GitHub Pages** | Servicio gratuito de GitHub que convierte los archivos de un repositorio en una página web. |
| **Supabase** | Base de datos en internet. Aquí hace de buzón entre el ordenador y el móvil. |
| **Project URL / clave pública** | La dirección de tu Supabase y la llave «de visitante» que permite usar el buzón. |
| **SQL** | El idioma de las bases de datos. Solo hay que copiar y pegar el archivo una vez. |
| **.dvw** | El archivo de partido de DataVolley. |
| **Side-out / Break** | % de puntos ganados recibiendo / sacando. |

---

## 15. Créditos y licencias

- Idea, pruebas y uso en partidos reales: **Pedro**, entrenador y scout del **CV Voleibol Barberà**.
- Librerías incluidas dentro de los archivos (licencia MIT):
  - [supabase-js](https://github.com/supabase/supabase-js), para la conexión con Supabase;
  - [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator), para crear los códigos QR.
- *DataVolley* es una marca de Data Project. Este proyecto no está afiliado a Data Project: solo lee los archivos que DataVolley guarda en tu ordenador.

¿Dudas o mejoras? Abre un **Issue** en este repositorio (pestaña **Issues** → **New issue**).
