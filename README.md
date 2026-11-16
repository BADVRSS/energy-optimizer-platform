# Plataforma de Optimización Energética Automatizada para Edificios Corporativos

## 📌 Descripción del Proyecto
El desperdicio masivo de energía eléctrica y climatización en edificios corporativos ocurre porque los sistemas funcionan bajo horarios fijos, ignorando la ocupación real y los cambios climáticos del día. Esta plataforma utiliza Inteligencia Artificial (IA) e Internet de las Cosas (IoT) para regular automáticamente la temperatura y la iluminación zona por zona, reduciendo el consumo sin sacrificar el confort.

## 🖥️ Tipo de Aplicación y Funcionalidades
Es una **aplicación web** con arquitectura backend en la nube/edge y microservicios orientados a eventos. 
**Funcionalidades principales:**
*   **Monitoreo energético:** Consumo en tiempo real por zona.
*   **Control inteligente IA:** Ajuste de HVAC e iluminación basado en ocupación y clima.
*   **Gestión de ocupación:** Sensores de presencia y conteo de accesos.
*   **Calidad del aire:** Monitoreo de CO₂ y ventilación bajo demanda.
*   **Mantenimiento predictivo IoT:** Detección temprana de fallos en motores y compresores.
*   **Gestión de actuadores:** Control de ventanas y compuertas.

## 👥 Actores del Sistema
1.  **Administrador del edificio:** Configura zonas, umbrales y reglas de negocio.
2.  **Operador/Gerente energético:** Supervisa consumo, valida ahorros y ajusta estrategias.
3.  **Técnico de mantenimiento:** Atiende alertas predictivas y gestiona equipos.
4.  **Usuario final (ocupante):** Reporta incidencias y consulta el estado de su zona.

## 🛠️ Herramientas de Desarrollo
*   **Frontend:** React / Next.js, TypeScript, Tailwind CSS.
*   **Backend:** Python / FastAPI, MQTT Broker.
*   **IA / ML:** TensorFlow Lite / PyTorch, Scikit-learn.
*   **Bases de Datos:** PostgreSQL, InfluxDB / TimescaleDB.
*   **IoT / Edge:** Raspberry Pi 5 / Jetson Orin Nano, MQTT, Modbus, Zigbee.
*   **Infraestructura:** Docker, GitHub Actions.
*   **Gestión:** GitHub Projects.

## 🤖 Aplicación de la IA
La IA cumple dos roles centrales:
1.  **Control adaptativo:** Modelos LSTM/GRU y aprendizaje por refuerzo que predicen la demanda y ajustan los setpoints de climatización e iluminación en tiempo real.
2.  **Mantenimiento predictivo:** Detección de anomalías en datos de vibración y temperatura de los equipos para alertar al técnico antes de que ocurra una avería.

## 📡 Aplicación de IoT
La plataforma integra sensores de presencia, contadores de acceso, sensores de CO₂, temperatura, humedad y vibración. Los datos se envían a un *Gateway Edge* (Raspberry Pi/Jetson) mediante MQTT/Modbus y desde ahí a la nube para su análisis.

## 🗂️ Organización del Repositorio (Arquitectura Hexagonal)
El código está estructurado para separar la lógica de negocio de la infraestructura:
*   `docs/`: Documentación del proyecto y manuales.
*   `domain/`: Entidades y lógica de negocio pura.
*   `application/`: Casos de uso y orquestación.
*   `infrastructure/`: Adaptadores de bases de datos, brokers MQTT y APIs.
*   `frontend/`: Interfaz web (Next.js/React).
*   `tests/`: Pruebas unitarias e integración.
*   `.github/workflows/`: Integración Continua (CI/CD).

## 📋 Planeación y Gestión Ágil
*   **Tablero Kanban:** Gestión visual de tareas en GitHub Projects.
*   **Historias de Usuario y Criterios de Aceptación:** Ver carpeta `docs/historias-de-usuario.md`.
*   **Product Backlog Priorizado:** Ver carpeta `docs/product-backlog.md`.

## 🎨 Maquetado de la Aplicación
El diseño de la interfaz (UI/UX) se puede consultar en la carpeta `docs/maquetado/`.
