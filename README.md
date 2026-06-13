# 🔬 Test Munsell Profesional - ADC
> **Sistema Digital de Evaluación de Percepción Cromática para Aseguramiento de Calidad.**

Este proyecto es una aplicación web interactiva diseñada para auditar y evaluar la agudeza visual y la capacidad de discriminación del color en el personal del laboratorio de Control de Calidad (ADC). Está basado conceptualmente en los principios del test Farnsworth-Munsell 100 Hue.

---

## 🚀 Características del Sistema

- **Espectro Dinámico Aleatorio:** Cada vez que se inicia una prueba, el sistema genera un arco cromático único y aleatorio de 22 fichas (2 anclas fijas en los extremos y 20 fichas móviles desordenadas). Esto evita que los evaluados memoricen las posiciones.
- **Cómputo Automatizado de Error (TES):** Calcula en tiempo real el Puntaje de Error Total (Total Error Score) basándose en la diferencia absoluta de la posición de los IDs adyacentes.
- **Sincronización Bifásica de Datos:** 1. **Local:** Almacenamiento local asíncrono para auditorías rápidas en el dispositivo mediante panel administrador protegido (`adminADC`).
  2. **Nube (Cloud):** Inyección automatizada mediante API (Google Apps Script) hacia una base de datos centralizada en **Google Sheets** sin intermediarios.
- **Interfaz Responsiva Panorámica:** Diseñado para ejecutarse en dispositivos móviles en orientación horizontal para simular las líneas de examen físicas.

---

## 📊 Matriz de Diagnóstico y Calibración

El sistema categoriza automáticamente el desempeño de los auxiliares de acuerdo al puntaje de error neto obtenido:

| Puntaje de Error (TES) | Clasificación en Laboratorio | Aptitud en Flexografía / Color |
| :---: | :--- | :--- |
| **0** | 🟢 Discriminación Perfecta | Excelente / Perfil Formulador Avanzado |
| **1 a 8** | 🟢 Discriminación Superior | Excelente para Control de Calidad (ADC) |
| **9 a 24** | 🔵 Discriminación Promedio | Estándar Comercial Aceptable |
| **> 24** | 🔴 Discriminación Baja | Requiere Supervisión en Aprobación de Color |

---

## 🛠️ Tecnologías Utilizadas

- **Frontend:** HTML5 nativo, CSS3 avanzado (Variables CSS, transiciones fluidas, Media Queries de orientación), JavaScript Vanilla (ES6+).
- **Diseño Gráfico Integrado:** Isotipo vectorizado en formato SVG embebido de alta resolución.
- **Backend de Sincronización:** Google Apps Script (Motor V8 Engine con exclusión mutua de hilos mediante `LockService`).
- **Base de Datos:** Google Sheets API REST.

---

## 📂 Estructura del Repositorio

- `index.html`: Código fuente unificado de la aplicación (Estructura, estilos y lógica lógica).
- `README.md`: Documentación técnica del proyecto (Este archivo).

---

## 🔒 Notas de Seguridad Industrial y Privacidad

- El sistema utiliza un canal unidireccional por método `POST` cifrado. Los dispositivos de los evaluados **nunca** tienen credenciales de acceso ni permisos de lectura sobre la cuenta máster de Google o Google Drive.
- Para proteger el endpoint de inyección contra spam automatizado externo, se recomienda limitar la distribución del código QR estrictamente al entorno físico del laboratorio.

---
*Diseño, ingeniería de software y desarrollo elaborado por **Josué Sánchez**.*
