# HfaPlusSwf

Repositorio público de **distribución de clientes HFA** — el `HabboAir.swf` oficial de Habbo
parcheado (hooks + customs de HFA).

El launcher HFA (fuente **AIR_HFA**) descarga desde aquí el cliente ya parcheado, **por versión**,
replicando el mecanismo de descarga de AirPlus (en lugar de exigir un build local).

## Estructura

```
versions/<versión>/HabboAir.swf   ← cliente parcheado para esa versión oficial de Habbo
latest/HabboAir.swf               ← copia del último build publicado
versions.json                     ← manifiesto de versiones disponibles (swfVersion = "<v>-b<build>")
```

La `<versión>` coincide con el `flash-windows-version` que reporta el servidor oficial, de modo
que los identificadores del cliente cuadran con los de AIR (Official). El `swfVersion` interno
(`5-b3`, `5-b7`…) sube en cada re-parche aunque la versión oficial no cambie, para forzar la
re-descarga en el launcher.

## Descarga directa (raw)

```
https://raw.githubusercontent.com/denio4321/HfaPlusSwf/master/versions/<versión>/HabboAir.swf
https://raw.githubusercontent.com/denio4321/HfaPlusSwf/master/latest/HabboAir.swf
```

---

# Comandos del cliente HFA

Se escriben en el **chat** con `:` delante (p. ej. `:figure 12345 M`). Dos atajos útiles:
- **`:commands`** — abre una ventana buscable con todos los comandos y su estado.
- **`:status`** — muestra solo lo que tienes activado/desactivado.

## ⚠ Comandos arriesgados (USE AT OWN RISK)

Estos comandos **pueden causar mute, kick o sanción del servidor** según el hotel. Se conservan
porque pueden ser útiles, pero aparecen marcados con **⚠** en `:commands` y **avisan la primera
vez que los usas** en cada sesión. Úsalos bajo tu responsabilidad.

| Comando | Qué hace | Riesgo |
|---|---|---|
| `:respect` | Da respeto al usuario clicado (consume uno de tus respetos del día) | Acción server-side; abuso = sospechoso |
| `:ping` | Mide y muestra tu latencia (RTT) | Envía un paquete interstitial bajo demanda |
| `:pingsay` | Mide el ping y lo **publica en el chat** | Igual que `:ping` + spam de chat (mute) |
| `:typing` | **Oculta** que estás escribiendo (no envía el indicador) | Algunos servers lo detectan/flaggean |
| `:adblock` | Quita los anuncios MPU de la sala | Manipula objetos de sala (server-side) |
| `:give` / `:pass` | Entrega tu handitem al usuario/mascota clicado | Conflictos server-side, sobre todo en mascotas |

> **Comandos peligrosos RETIRADOS** (no están en el cliente HFA por riesgo elevado): `:handitem`,
> `:fx`, `:calendar`, `:linkevent`, `:aprilfools`, `:spawn`.

## Apariencia / tema

| Comando | Qué hace |
|---|---|
| `:theme [hfa/classic/pink]` | Aplica un tema de colores |
| `:color [hex/classic/pink/hfa]` | Color de la barra de título |
| `:barcolor [hex/…]` | Color de la barra inferior |
| `:bgcolor [H S L]` | Color de fondo de la sala |
| `:winblend [0-1]` · `:barblend [0-1]` | Transparencia de ventana / barra |
| `:barstyle` | Barra inferior alternativa |
| `:seasonal` | Colores de temporada |

## Looks

| Comando | Qué hace |
|---|---|
| `:figure [code] [M/F]` | Cambia tu figura |
| `:clone [M/F]` | Copia el look del usuario clicado |
| `:savelook [nombre]` · `:uselook [nombre]` · `:removelook [nombre]` | Guardar/usar/borrar look |
| `:showlooks` · `:clearlooks` | Listar / borrar todos los looks |

## Sala e interacción

| Comando | Qué hace |
|---|---|
| `:playing` | **Click-through**: clicar kekos/furni te hace caminar a la baldosa (no los selecciona) |
| `:clickuser [id]` · `:clickfurni [id]` · `:usefurni [id]` · `:movetofurni [id]` | Interacción por id |
| `:acceptquest [id]` | Acepta una quest |
| `:rotate` | Efecto de rotación de la sala |
| `:backlight [0-255]` · `:roomlight [0-255]` | Luces de la sala |
| `:zoomf [0-5]` · `:zoomgestures` | Zoom fraccional / gestos de zoom |
| `:walkblock` · `:swb` · `:turnblock` | Bloquear caminar (siempre / con Shift) / girar |
| `:dc` · `:nodc` · `:ctrl` | Usar furni con 1 clic / bloquear doble clic / Ctrl = 1 clic |
| `:tradeblock` · `:wcublock` | Bloquear intercambios / wired-click-user |
| `:autoclick` · `:autoclickdelay [ms]` | Autoclick del último furni |

## Chat

| Comando | Qué hace |
|---|---|
| `:say [texto]` · `:shout [texto]` · `:whisper [user texto]` | Decir / gritar / susurrar |
| `:chatmute` | Silencia el chat de la sala (no ves burbujas) |
| `:mutepets` · `:mutebots` | Silencia mascotas / bots |
| `:chatcolor` · `:chatsize [12-40]` | Color / tamaño del chat |
| `:hideignoredbubble` | Oculta las burbujas de usuarios ignorados |
| `:cmdcolor` · `:mutecmd` | Color/autocompletado y avisos de comandos |
| `:chatalarm [texto]` | Alarma sonora al recibir un texto |
| `:flood [texto]` · `:flooddelay [ms]` | Repetir un texto en bucle (cuidado: mute) |
| `:clearchat` · `:clearhist` | Limpiar chat de sala / historial |

## Avatar / gestos

| Comando | Qué hace |
|---|---|
| `:dance [0-4]` · `:laugh` · `:sit` · `:stand` | Bailar / reír / sentarse / levantarse |
| `:lightsaber` | Efecto sable de luz |
| `:crash` | Fuerza un crash del cliente (debug) |

## Usuarios

| Comando | Qué hace |
|---|---|
| `:hidefigures` | Oculta usuarios con tu misma figura |
| `:hidepoints [max]` | Oculta usuarios con ≤ N puntos |
| `:fon [0-2]` | Aviso de amigo conectado |
| `:friendhl` · `:caution` | Resaltar entrada de amigos / alertas de moderación |
| `:infostand` | Oculta el panel de info de furni/usuario |

## Red

| Comando | Qué hace |
|---|---|
| `:pingbeforetext [t]` · `:pingaftertext [t]` · `:pingbubble [auto]` | Formato del `:pingsay` |

(ver `:ping`/`:pingsay` en la tabla ⚠ de arriba)

## Rendimiento

| Comando | Qué hace |
|---|---|
| `:boost` | Paquete: quality low (UI 2D) + throttle de ratón + caché HTTP |
| `:fps [1-999]` · `:unlockfps` | Capar / desbloquear FPS (capar reduce CPU y churn) |
| `:quality [low/medium/high/best]` | Calidad de render 2D (no afecta a la sala, que va en CPU) |
| `:mousefix [0-10]` | Limitar eventos de ratón por frame |
| `:fpsmeter` · `:lagspikes` · `:bench [seg]` | Monitor de FPS / log de tirones / benchmark A/B |
| `:gc` | Forzar recolección de basura (úsalo solo para probar) |

> Nota: la sala se renderiza **por software (CPU)**, no GPU. Las palancas reales son menos sprites
> (`tsearch`), capar FPS y ventana más pequeña. `:gcsmooth` se retiró por empeorar el rendimiento.

## tsearch (filtrar furnis)

| Comando | Qué hace |
|---|---|
| `:initsearch` | Captura los furnis de ESTA sala como whitelist y activa tsearch |
| `:tsearch` | Activa/desactiva el bloqueo de furnis fuera de la whitelist |
| `:tsearchlist` · `:tsearchadd [tipo]` · `:tsearchdel [tipo]` | Ver / añadir / quitar tipos |

## Hotkeys

| Comando | Qué hace |
|---|---|
| `:f1`…`:f12 [comando]` | Liga una tecla F a un comando (p. ej. `:f1 :dance 2`) |
| `:hkset [comando]` | Liga la SIGUIENTE tecla que pulses a un comando |
| `:hkshow` · `:hkclear` · `:hkmode` | Mostrar / borrar / alternar modo de hotkeys |

## Ventanas / varios

| Comando | Qué hace |
|---|---|
| `:youtube` · `:vimeo` | Abrir los visores de vídeo |
| `:donate` | Donar (función del hotel) |
| `:safetybook` · `:habboway` · `:furnitech` | Abrir páginas/widgets del cliente |
| `:linkport` | Teletransporte enlazado |
| `:commands` · `:status` | Ventana de comandos / estado |
| `:about` · `:version` | Info del cliente |
| `:showerrors` · `:resetvars` | Mostrar errores críticos / resetear ajustes guardados |

---

Repo: <https://github.com/denio4321/HfaPlusSwf>
