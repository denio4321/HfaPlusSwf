# HfaPlusSwf

Repositorio público de **distribución de clientes HFA** — el `HabboAir.swf` oficial de Habbo
parcheado por [HfaPlus](https://github.com/denio4321) (hooks + customs de HFA).

El launcher HFA (fuente **AIR_HFA**) descarga desde aquí el cliente ya parcheado, **por versión**,
replicando el mecanismo de descarga de AirPlus (en lugar de exigir un build local).

## Estructura

```
versions/<versión>/HabboAir.swf   ← cliente parcheado para esa versión oficial de Habbo
latest/HabboAir.swf               ← copia del último build publicado
versions.json                     ← manifiesto de versiones disponibles
```

La `<versión>` coincide con el `flash-windows-version` que reporta el servidor oficial, de modo
que los identificadores del cliente cuadran con los de AIR (Official).

## Descarga directa (raw)

```
https://raw.githubusercontent.com/denio4321/HfaPlusSwf/main/versions/<versión>/HabboAir.swf
https://raw.githubusercontent.com/denio4321/HfaPlusSwf/main/latest/HabboAir.swf
```

---

Repo: <https://github.com/denio4321/HfaPlusSwf>
