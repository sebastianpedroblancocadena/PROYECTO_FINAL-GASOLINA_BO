
# 🛢️ FuelChain Bolivia - Custodia Digital de Combustible

![FuelChain Bolivia](https://img.shields.io/badge/Status-Prototipo-brightgreen)
![Tech](https://img.shields.io/badge/Tech-HTML%20%7C%20CSS%20%7C%20Vanilla%20JS-blue)

**FuelChain Bolivia** es una prueba de concepto (PoC) en un solo archivo HTML que simula el centro de control para la custodia digital de transporte de combustible desde la Planta de Senkata hasta estaciones de destino en La Paz. 

El sistema integra simulaciones de **Blockchain**, **Sensores IoT** y un **HSM (Hardware Security Module)** para garantizar la inmutabilidad y seguridad de la cadena de suministro.

## ✨ Características Principales

- **⛓️ Blockchain en el Navegador**: Utiliza la Web Crypto API (SHA-256) para enlazar bloques criptográficos de eventos críticos (creación de lote, lecturas de sensores, autorizaciones).
- **📡 Sensores IoT Simulados**: Generación de datos de volumen, temperatura, densidad y coordenadas GPS en tiempo real a lo largo de la ruta.
- **🔐 Firmas HSM (Simulado)**: Firma digital de las lecturas (Dual Handshake) para prevenir la manipulación de datos en tránsito.
- **🚚 Monitoreo de Ruta y Entregas**: Verificación estricta de GPS, capacidad del tanque, firmas criptográficas y precintos antes de autorizar la descarga de combustible.
- **🚨 Simulaciones de Ataque**: 
  - Simulación de *ordeño* (pérdida de combustible anormal o robo en ruta).
  - Simulación de *ataque a sensores* (intento de manipulación de datos bloqueado por el HSM).
- **💾 Persistencia Local**: Los datos se guardan en el `localStorage` del navegador o `window.storage` para simular una base de datos sin necesidad de backend.

## 🚀 Cómo usar (Instalación)

Al ser una aplicación de una sola página (**Single-File Web App**), no requiere de servidores, bases de datos externas ni instalación de dependencias.

1. Descarga el código y guárdalo en un archivo llamado `index.html`.
2. Ábrelo directamente haciendo doble clic con cualquier navegador web moderno (Chrome, Firefox, Edge, Safari).
3. ¡Listo! Empieza a interactuar con el panel de control. No se requiere conexión a internet tras la carga (a menos que se bloqueen las fuentes externas de Google Fonts).

## 🗺️ Estructura del Panel de Control

El menú lateral te permite navegar por diferentes módulos de la operación:

### 📦 Operaciones
* **Control Center (Dashboard)**: Resumen en tiempo real (KPIs) del estado operativo.
* **Envíos**: Creación y gestión de lotes de combustible (MINT_FUEL_BATCH).
* **Monitoreo en Vivo**: Seguimiento por mapa GPS y gráficos a lo largo de la ruta (Senkata → El Alto → Autopista → La Paz).
* **Sensores IoT**: Historial de lecturas criptográficamente firmadas.
* **Centro de Alertas**: Registro de anomalías, advertencias y eventos de seguridad críticos.
* **Simulaciones**: Área interactiva para ejecutar ataques simulados y evaluar la respuesta defensiva del sistema.
* **Control de Entrega**: Ejecución del *Dual Handshake* para autorizar o bloquear las válvulas de descarga en destino.

### 🛡️ Confianza & Registro
* **Blockchain**: Explorador de bloques generados y botón para verificar la integridad (hashes consecutivos). Permite simular una alteración manual para ver cómo falla la validación.
* **Base de Datos**: Visor de las tablas internas de registros (Camiones, Envíos, Eventos, Bloques).
* **Auditoría**: Línea de tiempo inmutable con toda la traza técnica y logística de los lotes.
* **Modo Demostración**: Ejecución automatizada (1-click) de un viaje normal o un escenario de robo para fines de presentación rápida.

## 🛠️ Tecnologías Utilizadas

- **HTML5 & CSS3**: Interfaz de usuario moderna estilo *dashboard* oscuro, diseño responsivo basado en variables CSS nativas.
- **Vanilla JavaScript (ES6+)**: Lógica de negocio completa, persistencia, manejo del DOM y simulaciones, sin uso de frameworks de terceros (React/Vue).
- **Web Crypto API**: Generación asíncrona de firmas y validaciones mediante criptografía nativa SHA-256 en el cliente.

## 🔒 Notas de Seguridad 
> **Advertencia:** Esta aplicación es un **entorno de demostración arquitectónico**. 
> - La "llave HSM" (`HSM_KEY`) se encuentra *hardcodeada* en el código fuente con propósitos ilustrativos.
> - La red "Blockchain" vive enteramente en la memoria del cliente local.
> - **No debe utilizarse en entornos de producción** sin ser integrado a un backend protegido, dispositivos criptográficos físicos (HSM reales) y una red de base de datos distribuida real (DLT/Blockchain).

---
*Documentación autogenerada para el proyecto de Custodia Digital de Combustible - YPFB / ANH (Prototipo).*
