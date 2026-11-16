# Historias de Usuario con Criterios de Aceptación

## HU-01: Control automático de temperatura por zona
**Como** Operador energético
**Quiero** que la plataforma ajuste automáticamente la temperatura de cada zona según la ocupación real y el clima exterior
**Para** reducir el consumo eléctrico sin afectar el confort de los ocupantes

**Criterios de Aceptación:**
- [ ] Dado que una zona tiene 0 ocupantes detectados por sensores de presencia, cuando el sistema calcula la demanda, entonces ajusta el setpoint de HVAC a modo ahorro.
- [ ] Dado que una zona supera el 80% de ocupación, cuando la temperatura medida se desvía más de 1.5 °C del setpoint objetivo, entonces el sistema envía una orden de corrección al termostato en menos de 30 segundos.

## HU-02: Alerta predictiva de fallo en equipo HVAC
**Como** Técnico de mantenimiento
**Quiero** recibir una alerta automática cuando el sistema IoT detecte una alta probabilidad de fallo en un motor o compresor
**Para** intervenir antes de que ocurra la avería y evitar paradas no planificadas

**Criterios de Aceptación:**
- [ ] Dado que el modelo de IA estima una probabilidad de fallo ≥ 70% en las próximas 24 horas, cuando se ejecuta la inferencia, entonces se genera una alerta con el ID del equipo y acción recomendada.
- [ ] Dado que se genera la alerta, cuando el técnico la recibe, entonces puede marcarla como "atendida" o "falsa alarma".

## HU-03: Dashboard de consumo energético por zona
**Como** Gerente energético
**Quiero** visualizar en un dashboard el consumo en tiempo real y el ahorro acumulado por zona
**Para** validar el impacto de las estrategias de optimización y tomar decisiones

**Criterios de Aceptación:**
- [ ] Dado que el usuario accede al dashboard, cuando selecciona un rango de fechas, entonces se muestran gráficos de consumo por zona, línea base y porcentaje de ahorro.
- [ ] Dado que no hay datos para una zona en el rango seleccionado, cuando se carga el gráfico, entonces se muestra un mensaje de "Sin datos disponibles".

## HU-04: Control manual/programado de actuadores
**Como** Administrador del edificio
**Quiero** controlar manualmente o programar la apertura/cierre de ventanas motorizadas y compuertas de aire
**Para** mantener la calidad del aire y responder a eventos imprevistos

**Criterios de Aceptación:**
- [ ] Dado que el administrador envía un comando de apertura al 50%, cuando el actuador confirma la acción, entonces el estado de la ventana se actualiza en el dashboard en ≤ 5 segundos.
- [ ] Dado que se detecta una alerta de CO₂ alto y la ventilación mecánica está apagada, cuando la regla automática está activa, entonces el sistema abre las compuertas al 100% y notifica al operador.

## HU-05: Ingesta y almacenamiento de datos de sensores
**Como** Sistema de Monitoreo
**Quiero** recibir y almacenar los datos de sensores (CO₂, presencia, temperatura, luz) vía MQTT
**Para** tener un histórico de datos que alimente al motor de IA

**Criterios de Aceptación:**
- [ ] Dado que un sensor envía un dato vía MQTT, cuando el broker lo recibe, entonces se almacena en la base de datos de series temporales en menos de 1 segundo.
- [ ] Dado que un sensor pierde conexión, cuando pasan 5 minutos, entonces se genera una alerta de dispositivo offline.

## HU-06: API de consulta de consumo y estado
**Como** Desarrollador Frontend
**Quiero** contar con endpoints REST que devuelvan el estado actual de las zonas y el consumo
**Para** construir el dashboard de la plataforma de forma dinámica

**Criterios de Aceptación:**
- [ ] Dado que el frontend solicita GET /api/v1/zones, cuando el backend procesa la petición, entonces devuelve un JSON con los datos de temperatura y ocupación en < 200ms.
- [ ] Dado que el usuario no tiene permisos (token inválido), cuando intenta acceder al endpoint, entonces devuelve un error 403.

## HU-07: Gestión de umbrales de confort y reglas de negocio
**Como** Administrador del edificio
**Quiero** configurar los umbrales de temperatura, CO₂ e iluminación permitidos por zona
**Para** adaptar las políticas de eficiencia energética a las necesidades específicas de cada área

**Criterios de Aceptación:**
- [ ] Dado que el administrador ingresa un nuevo rango de temperatura, cuando guarda los cambios, entonces el sistema actualiza los setpoints límite para el motor de IA.
- [ ] Dado que se intenta ingresar un umbral fuera del rango de seguridad permitido, cuando se guarda, entonces el sistema muestra un mensaje de error.

## HU-08: Historial de alertas y mantenimiento por equipo
**Como** Técnico de mantenimiento
**Quiero** consultar el historial de alertas predictivas y las acciones tomadas para cada equipo
**Para** llevar un control del estado de salud de los activos y planificar el mantenimiento preventivo

**Criterios de Aceptación:**
- [ ] Dado que el técnico busca un equipo en específico, cuando accede a su perfil, entonces visualiza una línea de tiempo con todas las alertas pasadas, fechas y resoluciones.
- [ ] Dado que una alerta fue marcada como "falsa alarma", cuando se consulta el historial, entonces se muestra dicha etiqueta.

## HU-09: Reportes exportables (PDF/CSV) de ahorro
**Como** Gerente energético
**Quiero** poder descargar reportes mensuales de ahorro energético en formato PDF y CSV
**Para** presentar los resultados a la junta directiva y justificar el retorno de inversión

**Criterios de Aceptación:**
- [ ] Dado que el usuario solicita un reporte, cuando el sistema termina la generación, entonces descarga un archivo PDF con gráficos y tablas del ahorro.
- [ ] Dado que el reporte no tiene datos, cuando se genera, entonces muestra una advertencia de "Periodo sin registros".

## HU-10: Integración con calendario de ocupación
**Como** Operador energético
**Quiero** integrar los calendarios de Google/Outlook de la empresa con la plataforma
**Para** predecir la ocupación del edificio antes de que los empleados lleguen

**Criterios de Aceptación:**
- [ ] Dado que hay un evento de reunión programado, cuando inicia, entonces la plataforma precarga el setpoint de confort para esa zona.
- [ ] Dado que no hay eventos, cuando es día festivo, entonces la plataforma asume ocupación cero y activa el modo ahorro.
