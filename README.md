# LVM - Logical Volume Manager

Este repositorio contiene documentación, ejemplos y scripts para administrar volúmenes lógicos utilizando **LVM (Logical Volume Manager)** en sistemas Linux.

---

## Contenido

- [¿Qué es LVM?](#qué-es-lvm)
- [Ventajas de usar LVM](#ventajas-de-usar-lvm)
- [Componentes principales](#componentes-principales)
- [Arquitectura de LVM (diagrama)](#arquitectura-de-lvm-diagrama)
- [Comandos básicos](#comandos-básicos)
- [Ejemplo paso a paso](#ejemplo-paso-a-paso)
- [Scripts útiles](#scripts-útiles)
- [Recursos adicionales](#recursos-adicionales)

---

## ¿Qué es LVM?

**LVM** es una herramienta de administración de volúmenes que permite crear volúmenes lógicos sobre discos físicos, brindando una mayor flexibilidad para el manejo del almacenamiento.

---

## Ventajas de usar LVM

- Redimensionar volúmenes en caliente
- Crear snapshots
- Combinar varios discos en un solo volumen lógico
- Mejor uso del espacio en servidores

---

## Componentes principales

- **PV (Physical Volume)**: Dispositivo físico (disco o partición).
- **VG (Volume Group)**: Agrupación de PVs.
- **LV (Logical Volume)**: Volumen lógico creado dentro de un VG, sobre el cual se monta el sistema de archivos.

---

## Arquitectura de LVM (diagrama)

```text
+-------------------+   +-------------------+
| /dev/sda (PV)     |   | /dev/sdb (PV)     |
+-------------------+   +-------------------+
           \               /
            \             /
             \           /
           +---------------------+
           | Volume Group (VG)   |
           |   "vg_data"         |
           +---------------------+
             |     |        |
             |     |        |
     +-------+  +--+--+  +--+--+
     | Logical | | LV2 |  | LV3 |
     | Volume  | |     |  |     |
     |  LV1    | +-----+  +-----+
     +--------+   (ej. /home, /var, /data)

