# 🤖 Programador VMC - Sistema de Automatización de Asignaciones

Este proyecto automatiza la creación del programa para la reunión **Vida y Ministerio Cristianos**.  
Pasa de un proceso manual en Excel a un flujo de trabajo inteligente basado en datos (JSON/CSV) y algoritmos de rotación.

---

## 🏗️ Arquitectura del Proyecto

El sistema funciona en **4 Fases** secuenciales:

1.  **🕷️ FASE 1 (Extractor):** Descarga el programa semanal desde *wol.jw.org* y crea un "mapa" vacío en JSON.
2.  **✍️ FASE 2 (Registro Manual):** Permite al usuario asignar manualmente partes específicas (ej. Presidente, Lector) y guarda esa decisión en el historial.
3.  **🧠 FASE 3 (Motor Híbrido):** Lee el historial y **rellena automáticamente los huecos vacíos**, seleccionando al hermano más apto (basado en fechas de descanso).
4.  **🎨 FASE 4 (Generador PDF):** (En desarrollo) Convierte el programa final en un archivo PDF listo para imprimir.

---

## 📂 Estructura de Archivos

A continuación, los archivos activos y su función dentro del sistema:

```text
Programador_VMC/
│
├── 🐍 SCRIPTS PRINCIPALES (El Código)
│   ├── fase1_extractor_universal.py   # (v5.0) Scraper web. Genera el JSON base.
│   ├── registrador_manual_v3_6.py     # (v3.6) Interfaz CLI para cargar datos manuales.
│   ├── fase3_motor_hibrido.py         # (v2.0) El Cerebro. Rellena huecos automáticamen.
│   └── migrador_historial_v3.py       # Utilidad para importar datos de Excel antiguos.
│
├── 💾 DATOS (La Memoria)
│   ├── data_reuniones_2026.json       # El "Mapa" de las semanas y sus partes.
│   ├── historial_asignaciones.csv     # Registro histórico de quién hizo qué y cuándo.
│   ├── base_datos_hermanos.csv        # Lista maestra de publicadores (IDs, Nombres).
│   └── programa_completo_asignado.json# RESULTADO FINAL: Programa lleno sin huecos.
│
└── 📦 _LEGACY_ARCHIVE/                # Scripts antiguos (Excel) obsoletos.
