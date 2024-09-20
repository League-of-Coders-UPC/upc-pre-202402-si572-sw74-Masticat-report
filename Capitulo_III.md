# 3.1.  To-Be Scenario Mapping.
<div align="center">
  <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/to_be_mapping.png" alt="to_be">
</div>

# 3.2. User Stories

| Epic / Story ID | Título | Descripción | Criterios de Aceptación | Relacionado con (Epic ID) |
|-----------------|--------|-------------|-------------------------|---------------------------|
| E01 | Gestión de perfil | Como usuario, quiero poder gestionar mi perfil y el de mis mascotas para personalizar mi experiencia con Masticat | - | - |
| US01 | Crear perfil de usuario | Como nuevo usuario, quiero crear mi perfil en la aplicación Masticat para comenzar a utilizar el sistema | Given que soy un nuevo usuario<br>When ingreso mis datos personales y creo una contraseña<br>Then se crea mi perfil de usuario y puedo acceder a la aplicación | E01 |
| US02 | Añadir perfil de mascota | Como usuario registrado, quiero añadir el perfil de mi mascota para personalizar su plan de alimentación | Given que estoy autenticado en la aplicación<br>When ingreso los datos de mi mascota (nombre, especie, raza, edad, peso)<br>Then se crea un perfil para mi mascota asociado a mi cuenta | E01 |
| E02 | Configuración del dispensador | Como usuario, quiero poder configurar y controlar el dispensador Masticat para automatizar la alimentación de mi mascota | - | - |
| US03 | Conectar dispensador | Como usuario, quiero conectar mi dispensador Masticat a la red WiFi para controlarlo a través de la aplicación | Given que tengo un dispensador Masticat<br>When sigo las instrucciones de configuración en la app<br>Then el dispensador se conecta exitosamente a mi red WiFi y aparece como dispositivo activo en mi app | E02 |
| US04 | Programar horarios de alimentación | Como dueño de mascota, quiero programar horarios de alimentación para que mi mascota reciba sus comidas de forma regular | Given que tengo un dispensador conectado y un perfil de mascota<br>When establezco horarios de alimentación en la aplicación<br>Then el dispensador libera alimento en los horarios programados | E02 |
| E03 | Monitoreo y notificaciones | Como usuario, quiero recibir notificaciones y monitorear la alimentación de mi mascota para estar informado y asegurar su bienestar | - | - |
| US05 | Recibir notificaciones de alimentación | Como dueño de mascota, quiero recibir notificaciones cuando mi mascota ha sido alimentada para estar al tanto de su rutina | Given que tengo configuradas las notificaciones<br>When el dispensador libera alimento<br>Then recibo una notificación en mi dispositivo móvil | E03 |
| US06 | Ver historial de alimentación | Como dueño de mascota, quiero ver un historial de alimentación de mi mascota para monitorear sus hábitos alimenticios | Given que estoy autenticado en la aplicación<br>When accedo a la sección de historial de mi mascota<br>Then puedo ver un registro detallado de las alimentaciones, incluyendo fechas, horas y cantidades | E03 |
| E04 | Análisis y reportes | Como usuario, quiero acceder a análisis y reportes detallados sobre la alimentación de mi mascota para tomar decisiones informadas sobre su salud | - | - |
| US07 | Generar reporte mensual | Como usuario premium, quiero generar un reporte mensual de los hábitos alimenticios de mi mascota para compartirlo con mi veterinario | Given que soy un usuario premium<br>When solicito un reporte mensual en la aplicación<br>Then se genera un informe detallado con gráficos y estadísticas de alimentación que puedo descargar o compartir | E04 |
| E05 | Funcionalidades premium | Como usuario premium, quiero acceder a características avanzadas para maximizar los beneficios de Masticat | - | - |
| US08 | Activar control de temperatura | Como usuario premium, quiero activar el control de temperatura del dispensador para mantener el alimento en condiciones óptimas | Given que soy un usuario premium con un dispensador compatible<br>When activo la función de control de temperatura en la app<br>Then el dispensador mantiene el alimento a la temperatura configurada | E05 |
| E06 | Sitio web estático (Landing Page) | Como visitante, quiero acceder a información sobre Masticat para decidir si es el producto adecuado para mí | - | - |
| US09 | Explorar características del producto | Como visitante del sitio web, quiero explorar las características de Masticat para entender cómo puede beneficiar a mi mascota | Given que soy un visitante del sitio web de Masticat<br>When navego por la página de características del producto<br>Then puedo ver descripciones detalladas e imágenes de las funcionalidades de Masticat | E06 |
| US10 | Comparar planes de suscripción | Como visitante interesado, quiero comparar los diferentes planes de suscripción para elegir el más adecuado para mis necesidades | Given que estoy en la sección de planes del sitio web<br>When veo la tabla comparativa de planes<br>Then puedo identificar claramente las diferencias entre los planes estándar y premium | E06 |
| E07 | API para desarrolladores | Como desarrollador, quiero acceder a la API de Masticat para integrar sus funcionalidades en mis aplicaciones | - | - |
| TS01 | Autenticar con API | Como desarrollador, quiero autenticarme en la API de Masticat para acceder a los endpoints protegidos | Given que tengo credenciales de desarrollador válidas<br>When envío una solicitud de autenticación con mis credenciales<br>Then recibo un token de acceso válido | E07 |
| TS02 | Obtener datos de alimentación | Como desarrollador, quiero obtener datos de alimentación de una mascota específica a través de la API para integrarlos en mi aplicación | Given que estoy autenticado en la API<br>When hago una solicitud GET al endpoint `/api/v1/pets/{petId}/feeding-data`<br>Then recibo un JSON con los datos de alimentación de la mascota especificada | E07 |

# 3.3. Impact Mapping

<div align="center">
  <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/impact_mapping.png" alt="to_be">
</div>

<div align="center">
  <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/impact_mapping_2.png" alt="to_be">
</div>

<div align="center">
  <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/impact_mapping_3.png" alt="to_be">
</div>

# 3.4. Product Backlog

| # Orden | User Story Id | Título | Descripción | Story Points |
|---------|---------------|--------|-------------|--------------|
| 1 | US09 | Explorar características del producto | Como visitante del sitio web, quiero explorar las características de Masticat para entender cómo puede beneficiar a mi mascota | 3 |
| 2 | US10 | Comparar planes de suscripción | Como visitante interesado, quiero comparar los diferentes planes de suscripción para elegir el más adecuado para mis necesidades | 2 |
| 3 | US01 | Crear perfil de usuario | Como nuevo usuario, quiero crear mi perfil en la aplicación Masticat para comenzar a utilizar el sistema | 3 |
| 4 | US02 | Añadir perfil de mascota | Como usuario registrado, quiero añadir el perfil de mi mascota para personalizar su plan de alimentación | 2 |
| 5 | US03 | Conectar dispensador | Como usuario, quiero conectar mi dispensador Masticat a la red WiFi para controlarlo a través de la aplicación | 5 |
| 6 | US04 | Programar horarios de alimentación | Como dueño de mascota, quiero programar horarios de alimentación para que mi mascota reciba sus comidas de forma regular | 5 |
| 7 | US05 | Recibir notificaciones de alimentación | Como dueño de mascota, quiero recibir notificaciones cuando mi mascota ha sido alimentada para estar al tanto de su rutina | 3 |
| 8 | US06 | Ver historial de alimentación | Como dueño de mascota, quiero ver un historial de alimentación de mi mascota para monitorear sus hábitos alimenticios | 3 |
| 9 | TS01 | Autenticar con API | Como desarrollador, quiero autenticarme en la API de Masticat para acceder a los endpoints protegidos | 5 |
| 10 | TS02 | Obtener datos de alimentación | Como desarrollador, quiero obtener datos de alimentación de una mascota específica a través de la API para integrarlos en mi aplicación | 5 |
| 11 | US07 | Generar reporte mensual | Como usuario premium, quiero generar un reporte mensual de los hábitos alimenticios de mi mascota para compartirlo con mi veterinario | 8 |
| 12 | US08 | Activar control de temperatura | Como usuario premium, quiero activar el control de temperatura del dispensador para mantener el alimento en condiciones óptimas | 8 |