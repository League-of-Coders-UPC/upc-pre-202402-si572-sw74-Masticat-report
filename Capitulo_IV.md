# Capítulo IV: Strategic-Level Software Design

## 4.1. Strategic-Level Attribute-Driven Design

### 4.1.1. Design Purpose

Propósito del Diseño: El propósito del diseño estratégico de Masticat es crear una solución automatizada de dispensación de alimentos para mascotas que elimine la necesidad de intervención humana constante y proporciona un control preciso sobre la alimentación de las mascotas. Esta solución busca ofrecer a los dueños de mascotas y clínicas veterinarias una herramienta confiable para la gestión de la alimentación, mejorando la salud y el bienestar de las mascotas a través de una nutrición controlada y monitorizada. Además, se busca proporcionar una plataforma que permita a los usuarios gestionar perfiles, recibir notificaciones, analizar hábitos alimenticios y acceder a funcionalidades premium para una experiencia completa y personalizada.

### 4.1.2. Attribute-Driven Design Inputs

#### 4.1.2.1. Primary Functionality (Primary User Stories)

| Epic / User Story ID | Título | Descripción | Criterios de Aceptación | Relacionado con (Epic ID) |
|----------------------|--------|-------------|-------------------------|---------------------------|
| US01 | Crear perfil de usuario | Como nuevo usuario, quiero crear mi perfil en la aplicación Masticat para comenzar a utilizar el sistema | Given que soy un nuevo usuario<br>When ingreso mis datos personales y creo una contraseña<br>Then se crea mi perfil de usuario y puedo acceder a la aplicación | E01 |
| US02 | Añadir perfil de mascota | Como usuario registrado, quiero añadir el perfil de mi mascota para personalizar su plan de alimentación | Given que estoy autenticado en la aplicación<br>When ingreso los datos de mi mascota (nombre, especie, raza, edad, peso)<br>Then se crea un perfil para mi mascota asociado a mi cuenta | E01 |
| US03 | Conectar dispensador | Como usuario, quiero conectar mi dispensador Masticat a la red WiFi para controlarlo a través de la aplicación | Given que tengo un dispensador Masticat<br>When sigo las instrucciones de configuración en la app<br>Then el dispensador se conecta exitosamente a mi red WiFi y aparece como dispositivo activo en mi app | E02 |
| US04 | Programar horarios de alimentación | Como dueño de mascota, quiero programar horarios de alimentación para que mi mascota reciba sus comidas de forma regular | Given que tengo un dispensador conectado y un perfil de mascota<br>When establecer horarios de alimentación en la aplicación<br>Then el dispensador libera alimento en los horarios programados | E02 |

#### 4.1.2.2. Quality Attribute Scenarios

**Scenario 1: Reliability**
- Atributo: Continuidad del servicio
- Estímulo: Corte de energía eléctrica
- Artefacto: Sistema de dispensación Masticat
- Entorno: Condiciones normales de operación
- Respuesta: El sistema debe continuar funcionando con la batería de respaldo
- Medida: Tiempo de operación continua sin energía eléctrica (mínimo 24 horas)

**Scenario 2: Usability**
- Atributo: Facilidad de configuración
- Estímulo: Primera instalación del dispositivo
- Artefacto: Aplicación móvil de Masticat
- Entorno: Hogar del usuario
- Respuesta: El usuario debe poder configurar el dispositivo y programar la primera alimentación
- Medida: Tiempo para completar la configuración inicial (menos de 15 minutos)

**Scenario 3: Performance**
- Atributo: Tiempo de respuesta
- Estímulo: Detección de mascota cerca del dispensador
- Artefacto: Sensores y mecanismo de dispensación
- Entorno: Operación normal
- Respuesta: El sistema debe identificar a la mascota y dispensar el alimento
- Medida: Tiempo desde la detección hasta la dispensación (menos de 5 segundos)

#### 4.1.2.3. Constraints

1. El dispositivo debe ser compatible con diferentes tipos y tamaños de alimento seco para mascotas.
2. La aplicación móvil debe funcionar en sistemas iOS y Android.
3. El sistema debe cumplir con las regulaciones de seguridad alimentaria para mascotas.
4. La comunicación entre el dispositivo y la aplicación debe ser segura y encriptada.
5. El consumo de energía del dispositivo debe ser optimizado para una larga duración de la batería.
6. La integración con sistemas de terceros debe realizarse a través de una API segura y documentada.

### 4.1.3. Architectural Drivers Backlog

**Driver 1: Precisión en la Dispensación**
- Descripción: La precisión en la medición y dispensación de alimentos es crucial para mantener dietas controladas.
- Importancia para Stakeholders: Alta
- Impacto en Architecture Technical Complexity: Media

**Driver 2: Conectividad y Control Remoto**
- Descripción: La capacidad de controlar y monitorear el dispositivo remotamente es esencial para la comodidad del usuario.
- Importancia para Stakeholders: Alta
- Impacto en Architecture Technical Complexity: Alta

**Driver 3: Identificación de Mascotas**
- Descripción: La habilidad de identificar diferentes mascotas permite una alimentación personalizada y un seguimiento preciso.
- Importancia para Stakeholders: Media
- Impacto en Architecture Technical Complexity: Alta

**Driver 4: Análisis de Datos y Reportes**
- Descripción: La capacidad de generar informes detallados y análisis de hábitos alimenticios es clave para el valor añadido del producto.
- Importancia para Stakeholders: Alta
- Impacto en Architecture Technical Complexity: Media

### 4.1.4. Architectural Design Decisions

1. Implementar un sistema de sensores RFID para la identificación precisa de mascotas.
2. Utilizar una arquitectura basada en la nube para el almacenamiento de datos y el control remoto.
3. Desarrollar una aplicación móvil híbrida utilizando React Native para asegurar la compatibilidad con iOS y Android.
4. Implementar un sistema de medición basado en peso para garantizar la precisión en la dispensación de alimentos.
5. Utilizar una arquitectura de microservicios para facilitar la escalabilidad y el mantenimiento del backend.
6. Implementar un sistema de notificaciones push para mantener a los usuarios informados en tiempo real.

### 4.1.5. Quality Attribute Scenario Refinements

**Scenario Refinement for Reliability**
- Scenario(s): Continuidad del servicio durante cortes de energía
- Business Goals: Asegurar la alimentación constante de las mascotas
- Relevant Quality Attributes: Confiabilidad, Disponibilidad
- Stimulus: Corte de energía eléctrica
- Scenario Components: Activación de la batería de respaldo, mantenimiento de funciones críticas
- Stimulus Source: Falla en el suministro eléctrico
- Environment: Hogar o clínica veterinaria
- Artifact (if Known): Sistema de alimentación Masticat
- Response: Continuación de la operación normal del dispositivo
- Response Measure: Duración de la operación con batería (mínimo 24 horas)
- Questions: 
  - ¿Cómo se notifica al usuario sobre el cambio a batería? 
  - ¿Cómo se prioriza el uso de energía en modo batería?
- Issues: Balancear la duración de la batería con la funcionalidad del dispositivo

**Scenario Refinement for Usability**
- Scenario(s): Facilidad de configuración inicial
- Business Goals: Maximizar la adopción y satisfacción del usuario
- Relevant Quality Attributes: Usabilidad, Experiencia de Usuario
- Stimulus: Primera instalación y configuración del dispositivo
- Scenario Components: Guía paso a paso, configuración de perfil de mascota, programación de primera alimentación
- Stimulus Source: Nuevo usuario
- Environment: Aplicación móvil y dispositivo Masticat
- Artifact (if Known): Interfaz de usuario de la aplicación móvil
- Response: Configuración completa y exitosa del dispositivo
- Response Measure: Tiempo para completar la configuración (objetivo: menos de 15 minutos)
- Questions: 
  - ¿Cómo se puede simplificar aún más el proceso de configuración? 
  - ¿Qué pasos son absolutamente necesarios?
- Issues: Equilibrar la simplicidad con la necesidad de recopilar información esencial sobre la mascota

**Scenario Refinement for Performance**
- Scenario(s): Respuesta rápida en la dispensación de alimentos
- Business Goals: Asegurar una experiencia fluida y confiable para las mascotas y sus dueños
- Relevant Quality Attributes: Rendimiento, Eficiencia
- Stimulus: Mascota se acerca al dispensador durante un horario programado de alimentación
- Scenario Components: Detección de la mascota, verificación del horario, medición y dispensación del alimento
- Stimulus Source: Presencia de la mascota
- Environment: Hogar del usuario, condiciones normales de operación
- Artifact (if Known): Sensores del dispensador Masticat, mecanismo de dispensación
- Response: Dispensación precisa y oportuna del alimento
- Response Measure: Tiempo total desde la detección hasta la dispensación completa (objetivo: menos de 5 segundos)
- Questions: 
  - ¿Cómo se maneja la situación si múltiples mascotas se acercan al mismo tiempo? 
  - ¿Cómo se asegura la precisión en la cantidad dispensada?
- Issues: Balancear la velocidad de respuesta con la precisión en la medición del alimento

#### 4.1.2.3. Constraints (Expanded)

1. **Compatibilidad con diferentes tipos de alimento:** El dispositivo debe ser compatible con distintos tipos y tamaños de alimento seco para mascotas, asegurando que funcione de manera eficiente sin obstrucciones.

2. **Compatibilidad con sistemas iOS y Android:** La aplicación móvil de Masticat debe ser completamente funcional en los sistemas operativos iOS y Android, proporcionando una experiencia de usuario uniforme y sin errores en ambas plataformas.

3. **Cumplimiento de regulaciones de seguridad alimentaria:** El sistema debe cumplir con todas las normativas y regulaciones relacionadas con la seguridad alimentaria para mascotas, garantizando que el alimento dispensado mantenga su calidad y frescura.

4. **Seguridad en la comunicación:** Toda la comunicación entre el dispositivo dispensador y la aplicación móvil debe estar protegida mediante encriptación, para asegurar la privacidad y seguridad de los datos del usuario y las mascotas.

5. **Optimización del consumo energético:** El sistema debe estar diseñado para minimizar el consumo de energía, especialmente cuando el dispensador funcione en modo de batería, garantizando una larga duración de operación sin comprometer el rendimiento.

6. **API segura y documentada:** La integración con sistemas de terceros debe realizarse a través de una API segura, bien documentada y fácil de utilizar por desarrolladores externos para extender las funcionalidades de Masticat sin comprometer la seguridad del sistema.



# 4.2 Bounded Context:

## 4.2.1 Profile Bounded Context

### 4.2.1.1 Domain Layer

#### Entities

- **Usuario**
  - Atributos: Id, Nombre, Email, etc.
  - Métodos: Crear(), Actualizar(), Eliminar(), etc.
- **Mascota**
  - Atributos: Id, Nombre, Microchip, etc.
  - Métodos: Registrar(), Actualizar(), Eliminar(), etc.
- **Preferencias**
  - Atributos: Id, UsuarioId, Preferencia, etc.
  - Métodos: Guardar(), Cargar(), Eliminar(), etc.

#### Aggregates
Usuario y Mascota pueden formar un agregado si la relación es fuerte.

#### Domain Services
Servicios para gestionar relaciones entre Usuario y Mascota.

#### Repositories
- IUsuarioRepository
- IMascotaRepository

### 4.2.1.2 Interface Layer

#### Controllers
- UsuarioController: Gestiona operaciones CRUD para usuarios.
- MascotaController: Gestiona operaciones CRUD para mascotas.
- PreferenciasController: Gestiona preferencias de usuario.

### 4.2.1.2 Application Layer

#### Command Handlers
- CreateUsuarioCommandHandler
- UpdateMascotaCommandHandler

#### Event Handlers
- UsuarioCreatedEventHandler
- MascotaUpdatedEventHandler

### 4.2.1.3 Infrastructure Layer

#### Implementaciones de Repositories
- UsuarioRepository: Implementación de IUsuarioRepository.
- MascotaRepository: Implementación de IMascotaRepository.

#### Servicios Externos
Conexión a bases de datos, APIs externas para gestión de perfiles, etc.

### 4.2.1.4 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- UsuarioService
- MascotaService
- PreferenciasService

[![Image from Gyazo](https://i.gyazo.com/f2ff03a1578e31ba0aff7e627093d80e.png)](https://gyazo.com/f2ff03a1578e31ba0aff7e627093d80e)

###  4.2.1.5 Bounded Context Software Architecture Code Level Diagrams

####  4.2.1.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/0b2ac6a0943876b5074af96cf7a8e1f4.png)](https://gyazo.com/0b2ac6a0943876b5074af96cf7a8e1f4)

####  4.2.1.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/0b2ac6a0943876b5074af96cf7a8e1f4.png)](https://gyazo.com/0b2ac6a0943876b5074af96cf7a8e1f4)

## 2. IAM (Identity and Access Management) Bounded Context

### 4.2.2.1 Domain Layer

#### Entities

- **Credenciales**
  - Atributos: Id, UsuarioId, ContraseñaHash, etc.
  - Métodos: Validar(), CambiarContraseña(), etc.
- **Roles**
  - Atributos: Id, Nombre, Descripción, etc.
  - Métodos: Asignar(), Eliminar(), etc.
- **Permisos**
  - Atributos: Id, RolId, Recurso, etc.
  - Métodos: Asignar(), Revocar(), etc.

#### Value Objects
Información de credenciales y permisos.

#### Aggregates
Credenciales, Roles, y Permisos.

#### Domain Services
- AuthenticationService
- AuthorizationService

#### Repositories
- ICredencialesRepository
- IRolesRepository
- IPermisosRepository

### 4.2.2.2 Interface Layer

#### Controllers
- AuthController: Gestión de autenticación.
- RoleController: Gestión de roles y permisos.

### 4.2.2.3 Application Layer

#### Command Handlers
- LoginCommandHandler
- AssignRoleCommandHandler

#### Event Handlers
- UserAuthenticatedEventHandler
- RoleAssignedEventHandler

### 4.2.2.4 Infrastructure Layer

#### Implementaciones de Repositories
- CredencialesRepository
- RolesRepository
- PermisosRepository

#### Servicios Externos
Conexiones a sistemas de autenticación, servicios de identidad, etc.

### 4.2.2.5 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- AuthenticationService
- AuthorizationService
 
 [![Image from Gyazo](https://i.gyazo.com/4cdcb28e28274072fd5e56287e9e1f52.png)](https://gyazo.com/4cdcb28e28274072fd5e56287e9e1f52)

### 4.2.2 Bounded Context Software Architecture Code Level Diagrams

#### 4.2.2.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/40668b834745e4c9685d015b0ec1b323.png)](https://gyazo.com/40668b834745e4c9685d015b0ec1b323)

#### 4.2.2.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/fcf783eb71a37d0aab9567ffb493eb91.png)](https://gyazo.com/fcf783eb71a37d0aab9567ffb493eb91)

## 3. Subscriptions and Payments Bounded Context

### 4.2.3.1 Domain Layer

#### Entities

- **PlanDeSuscripcion**
  - Atributos: Id, Nombre, Precio, etc.
  - Métodos: Crear(), Actualizar(), etc.
- **Pago**
  - Atributos: Id, UsuarioId, Monto, Fecha, etc.
  - Métodos: Procesar(), Reembolsar(), etc.
- **Factura**
  - Atributos: Id, PagoId, Detalles, etc.
  - Métodos: Emitir(), Cancelar(), etc.

#### Value Objects
Información de pago, detalles de factura.

#### Aggregates
PlanDeSuscripcion, Pago, Factura.

#### Domain Services
- SubscriptionService
- PaymentService

#### Repositories
- IPlanDeSuscripcionRepository
- IPagoRepository
- IFacturaRepository

### 4.2.3.2 Interface Layer

#### Controllers
- SubscriptionController: Gestión de suscripciones.
- PaymentController: Gestión de pagos y facturación.

### 4.2.3.3 Application Layer

#### Command Handlers
- CreateSubscriptionCommandHandler
- ProcessPaymentCommandHandler

#### Event Handlers
- SubscriptionCreatedEventHandler
- PaymentProcessedEventHandler

###  4.2.3.4 Infrastructure Layer

#### Implementaciones de Repositories
- PlanDeSuscripcionRepository
- PagoRepository
- FacturaRepository

#### Servicios Externos
Integración con pasarelas de pago, sistemas de facturación, etc.

###  4.2.3.5 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- SubscriptionService
- PaymentService

  [![Image from Gyazo](https://i.gyazo.com/63cfff9660b5b13ff3aaf4fbed9c0037.png)](https://gyazo.com/63cfff9660b5b13ff3aaf4fbed9c0037)

### 4.2.3. Bounded Context Software Architecture Code Level Diagrams

####  4.2.3.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/afa9477d3180a15a9d93c1c88a83d8bd.png)](https://gyazo.com/afa9477d3180a15a9d93c1c88a83d8bd)

#### 4.2.3.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/fc0239d35ad93876834ba5ca3b3696b8.png)](https://gyazo.com/fc0239d35ad93876834ba5ca3b3696b8)

## 4. Configuration and Planning Bounded Context

### 4.2.4.1 Domain Layer

#### Entities

- **ConfiguracionDeDispositivo**
  - Atributos: Id, DispositivoId, Configuracion, etc.
  - Métodos: Configurar(), Obtener(), etc.
- **HorarioDeAlimentacion**
  - Atributos: Id, MascotaId, Hora, etc.
  - Métodos: Programar(), Actualizar(), etc.
- **ConfiguracionDeSensores**
  - Atributos: Id, SensorId, Configuracion, etc.
  - Métodos: Configurar(), Leer(), etc.

#### Value Objects
Información de configuración.

#### Aggregates
ConfiguracionDeDispositivo, HorarioDeAlimentacion, ConfiguracionDeSensores.

#### Domain Services
- DeviceConfigurationService
- FeedingScheduleService

#### Repositories
- IConfiguracionDeDispositivoRepository
- IHorarioDeAlimentacionRepository
- IConfiguracionDeSensoresRepository

### 4.2.4.2 Interface Layer

#### Controllers
- DeviceConfigurationController: Gestión de configuraciones de dispositivos.
- FeedingScheduleController: Gestión de horarios de alimentación.
- SensorConfigurationController: Gestión de configuraciones de sensores.

### 4.2.4.3 Application Layer

#### Command Handlers
- ConfigureDeviceCommandHandler
- ScheduleFeedingCommandHandler

#### Event Handlers
- DeviceConfiguredEventHandler
- FeedingScheduledEventHandler

### 4.2.4.4 Infrastructure Layer

#### Implementaciones de Repositories
- ConfiguracionDeDispositivoRepository
- HorarioDeAlimentacionRepository
- ConfiguracionDeSensoresRepository

#### Servicios Externos
Integración con dispositivos, sistemas de programación, etc.

### 4.2.4.5 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- DeviceConfigurationService
- FeedingScheduleService

[![Image from Gyazo](https://i.gyazo.com/4ed4bc077e969a7c25a1cebc84fd633f.png)](https://gyazo.com/4ed4bc077e969a7c25a1cebc84fd633f)

### 4.2.4. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.4.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/96b3b7525ad75f68412baf5f7c7d6fa3.png)](https://gyazo.com/96b3b7525ad75f68412baf5f7c7d6fa3)

#### 4.2.4.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/7a987562a205f9fa45d4c079ffadf996.png)](https://gyazo.com/7a987562a205f9fa45d4c079ffadf996)

## 5. Operation Bounded Context

### 4.2.5.1 Domain Layer

#### Entities

- **Dispensado**
  - Atributos: Id, DispositivoId, Cantidad, Hora, etc.
  - Métodos: Dispensar(), ObtenerHistorial(), etc.
- **LecturaDeSensores**
  - Atributos: Id, SensorId, Valor, Fecha, etc.
  - Métodos: Leer(), Analizar(), etc.
- **EstadoDelDispositivo**
  - Atributos: Id, DispositivoId, Estado, etc.
  - Métodos: ActualizarEstado(), ObtenerEstado(), etc.

#### Value Objects
Información de dispensado y estado del dispositivo.

#### Aggregates
Dispensado, LecturaDeSensores, EstadoDelDispositivo.

#### Domain Services
- DispensingService
- SensorReadingService

#### Repositories
- IDispensadoRepository
- ILecturaDeSensoresRepository
- IEstadoDelDispositivoRepository

### 4.2.5.2 Interface Layer

#### Controllers
- DispensingController: Gestión del dispensado de comida y agua.
- SensorReadingController: Gestión de lecturas de sensores.
- DeviceStatusController: Gestión del estado del dispositivo.

### 4.2.5.3 Application Layer

#### Command Handlers
- DispenseFoodCommandHandler
- ReadSensorDataCommandHandler

#### Event Handlers
- FoodDispensedEventHandler
- SensorDataReadEventHandler

### 4.2.5.4 Infrastructure Layer

#### Implementaciones de Repositories
- DispensadoRepository
- LecturaDeSensoresRepository
- EstadoDelDispositivoRepository

#### Servicios Externos
Integración con dispositivos de dispensado y sensores, etc.

### 4.2.5.5 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- DispensingService
- SensorReadingService
  
[![Image from Gyazo](https://i.gyazo.com/7f641470b464c4f0ec51da2cb5993b80.png)](https://gyazo.com/7f641470b464c4f0ec51da2cb5993b80)

### 4.2.5 Bounded Context Software Architecture Code Level Diagrams

#### 4.2.5.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/4cea9dd883ed38b5c9ead78606becbe6.png)](https://gyazo.com/4cea9dd883ed38b5c9ead78606becbe6)

#### 4.2.5.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/0dc5e482773c62624805cb1d9697f190.png)](https://gyazo.com/0dc5e482773c62624805cb1d9697f190)

## 6. Service Execution Bounded Context

### 4.2.6.1 Domain Layer

#### Entities

- **AnalisisDeHabitos**
  - Atributos: Id, MascotaId, Datos, etc.
  - Métodos: Analizar(), GenerarReporte(), etc.
- **Reporte**
  - Atributos: Id, AnalisisId, Contenido, etc.
  - Métodos: Generar(), Enviar(), etc.
- **ServicioPremium**
  - Atributos: Id, UsuarioId, Caracteristica, etc.
  - Métodos: Activar(), Desactivar(), etc.

#### Value Objects
Información de análisis, reportes y características premium.

#### Aggregates
AnalisisDeHabitos, Reporte, ServicioPremium.

#### Domain Services
- HabitAnalysisService
- ReportGenerationService

#### Repositories
- IAnalisisDeHabitosRepository
- IReporteRepository
- IServicioPremiumRepository

### 4.2.6.2 Interface Layer

#### Controllers
- HabitAnalysisController: Gestión del análisis de hábitos.
- ReportController: Gestión de reportes.
- PremiumServiceController: Gestión de funcionalidades premium.

### 4.2.6.3 Application Layer

#### Command Handlers
- AnalyzeHabitsCommandHandler
- GenerateReportCommandHandler

#### Event Handlers
- HabitsAnalyzedEventHandler
- ReportGeneratedEventHandler

### 4.2.6.4 Infrastructure Layer

#### Implementaciones de Repositories
- AnalisisDeHabitosRepository
- ReporteRepository
- ServicioPremiumRepository

#### Servicios Externos
Integración con servicios de análisis, generación de reportes, etc.

### 4.2.6.5 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- HabitAnalysisService
- ReportGenerationService

  [![Image from Gyazo](https://i.gyazo.com/011ddfa5b0f679f2f4c1cd510ff2016b.png)](https://gyazo.com/011ddfa5b0f679f2f4c1cd510ff2016b)

### 4.2.6 Bounded Context Software Architecture Code Level Diagrams

#### 4.2.6.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/9c5713b9b17a8ed94b7c761a47c16ff5.png)](https://gyazo.com/9c5713b9b17a8ed94b7c761a47c16ff5)

#### 4.2.6.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/989bcd7b09ca352ea7359ac4464ab9e6.png)](https://gyazo.com/989bcd7b09ca352ea7359ac4464ab9e6)

## 7. Monitoring Bounded Context

### 4.2.7.1 Domain Layer

#### Entities

- **DatosDeUso**
  - Atributos: Id, UsuarioId, Fecha, Datos, etc.
  - Métodos: Recopilar(), Analizar(), etc.
- **Notificacion**
  - Atributos: Id, UsuarioId, Mensaje, Fecha, etc.
  - Métodos: Enviar(), Recibir(), etc.
- **EstadoDeSaludDeLaMascota**
  - Atributos: Id, MascotaId, Estado, etc.
  - Métodos: Actualizar(), Consultar(), etc.

#### Value Objects
Información de uso, notificaciones y estado de salud.

#### Aggregates
DatosDeUso, Notificacion, EstadoDeSaludDeLaMascota.

#### Domain Services
- UsageDataService
- NotificationService

#### Repositories
- IDatosDeUsoRepository
- INotificacionRepository
- IEstadoDeSaludDeLaMascotaRepository

### 4.2.7.2 Interface Layer

#### Controllers
- UsageDataController: Gestión de datos de uso.
- NotificationController: Gestión de notificaciones.
- HealthStatusController: Gestión del estado de salud de las mascotas.

### 4.2.7.3 Application Layer

#### Command Handlers
- CollectUsageDataCommandHandler
- SendNotificationCommandHandler

#### Event Handlers
- UsageDataCollectedEventHandler
- NotificationSentEventHandler

### 4.2.7.4 Infrastructure Layer

#### Implementaciones de Repositories
- DatosDeUsoRepository
- NotificacionRepository
- EstadoDeSaludDeLaMascotaRepository

#### Servicios Externos
Integración con sistemas de monitoreo, servicios de notificación, etc.

### 4.2.7.5 Bounded Context Software Architecture Component Level Diagrams

#### Componentes
- UsageDataService
- NotificationService

[![Image from Gyazo](https://i.gyazo.com/1a428fcedf93da2947f7ebba71ab7d35.png)](https://gyazo.com/1a428fcedf93da2947f7ebba71ab7d35)

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.6 Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/a81c9e190be71f5042b50abf8b29137e.png)](https://gyazo.com/a81c9e190be71f5042b50abf8b29137e)

#### 4.2.7.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/d0b5f10bb02f74169b6551266841e7ad.png)](https://gyazo.com/d0b5f10bb02f74169b6551266841e7ad)
