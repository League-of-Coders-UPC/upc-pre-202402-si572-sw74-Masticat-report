# Capítulo IV: Strategic-Level Software Design

## 4.1. Strategic-Level Domain-Driven Design.

### 4.1.1. EventStorming.

Legend:

![](https://i.gyazo.com/271896d5e75954538067393193cf75d0.jpg)

Configuration & Daily Uses

![](https://i.gyazo.com/01e9d129d47f58fca0daae06989ec692.jpg)

Monitoring & Analysis

![](https://i.gyazo.com/cc10e198140a58173c73c8bb69a31c7a.jpg)

Maintentance & Alerts

![](https://i.gyazo.com/6aa35ade3948d808029dab2b6dc34e96.jpg)

Remote Control

![](https://i.gyazo.com/290408a7061ef6172013a017fa79687c.jpg)

Multiple Pet Management

![](https://i.gyazo.com/8d63ddc94062e5747f328006f6407d4f.jpg)

Premium Subscription & Features

![](https://i.gyazo.com/a2eacef16333839894076c40fa45ade5.jpg)

#### 4.1.1.1. Candidate Context Discovery.

**1\. Profile Context**

**Dominio principal:** Gestión de usuarios, mascotas y dispositivos.

**Responsabilidades:**

- Crear y gestionar perfiles de usuario (Dueños, Veterinarios, Cuidadores).
- Administración de mascotas (nombre, raza, microchip).
- Asignación de dispositivos Masticat a mascotas.
- Configuración de preferencias y personalización del sistema por usuario y mascota.

**Entidades principales:**

- Usuario
- Mascota
- Dispositivo

**Eventos:**

- Usuario Registrado
- Mascota Agregada
- Dispositivo Configurado para Mascota

**Servicios:**

- Vinculación de nuevos usuarios.
- Integración de dispositivos con mascotas.
- Almacenamiento de perfiles y configuración personal.

### **2\. IAM (Identity and Access Management) Context**

**Dominio secundario:** Autenticación y autorización.

**Responsabilidades:**

- Gestión de la identidad de los usuarios (login/logout).
- Autorización para acceder a los dispositivos y funcionalidades.
- Control de roles y permisos en base a perfiles (dueños, veterinarios, cuidadores).

**Entidades principales:**

- Credenciales de Usuario
- Roles

**Eventos:**

- Acceso Autorizado
- Permisos Actualizados

**Servicios:**

- Provisión de autenticación multi-factor para usuarios premium.
- Gestión de políticas de seguridad.

**Límites claros:**

- No se gestionan los datos de configuración o alimentación, solo se controla el acceso y autenticación.

### **3\. Subscriptions and Payments Context**

**Dominio principal:** Gestión de suscripciones y pagos.

**Responsabilidades:**

- Gestión de las suscripciones premium y tiers.
- Procesamiento de pagos (monitoreo de éxito/fallo en pagos).
- Control del ciclo de vida de las suscripciones (actualización, cancelación).

**Entidades principales:**

- Suscripción
- Método de Pago

**Eventos:**

- Suscripción Actualizada
- Pago Procesado

**Servicios:**

- Integración con pasarelas de pago.
- Control del acceso a funcionalidades premium (cámaras, control de temperatura, asistentes de voz).

### **4\. Configuration and Planning Context**

**Dominio principal:** Configuración de alimentación y planificación.

**Responsabilidades:**

- Programar el dispenso de comida.
- Establecer horarios y frecuencia de alimentación.
- Configurar la cantidad de comida y agua según parámetros del usuario.

**Entidades principales:**

- Horario de Alimentación
- Configuración del Dispensador

**Eventos:**

- Horario de Alimentación Establecido
- Configuración de Dispensador Actualizada

**Servicios:**

- Permitir ajustes remotos desde la app móvil.
- Personalización de los horarios de alimentación por mascota.

**Límites claros:**

- La ejecución real de las órdenes de alimentación está en el contexto de "Operation".

### **5\. Operation Context**

**Dominio principal:** Ejecución operativa del dispensador y gestión física del sistema.

**Responsabilidades:**

- Dispensar comida y agua de acuerdo con los horarios o solicitudes manuales.
- Verificar el nivel de comida y notificar cuando está bajo.
- Identificar cuando la mascota está cerca mediante sensores de proximidad.
- Enviar datos de uso y alimentación a la aplicación.

**Entidades principales:**

- Comida Dispensada
- Nivel de Comida
- Sensor de Proximidad

**Eventos:**

- Comida Dispensada
- Nivel de Comida Actualizado
- Proximidad Detectada

**Servicios:**

- Coordinación de sensores para detectar la cercanía de la mascota.
- Actualización de los niveles de comida en tiempo real.
- Ejecución de órdenes de alimentación programadas o manuales.

### **6\. Service Execution Context**

**Dominio principal:** Ejecución de comandos específicos relacionados con funcionalidades premium.

**Responsabilidades:**

- Control de temperatura del dispensador para mantener la comida fresca.
- Activación de la cámara (si está disponible) para el monitoreo visual de la mascota.
- Interacción con asistentes de voz para comandos remotos.

**Entidades principales:**

- Temperatura
- Asistente de Voz

**Eventos:**

- Temperatura Ajustada
- Comando de Voz Ejecutado

**Servicios:**

- Integración con plataformas como Alexa o Google Assistant.
- Control de parámetros avanzados como temperatura y cámaras.

### **7\. Monitoring Context**

**Dominio principal:** Recolección de datos y análisis.

**Responsabilidades:**

- Recolección de datos de sensores (peso de comida, cantidad de agua).
- Generación de reportes de uso y alimentación.
- Análisis de hábitos alimenticios de las mascotas.

**Entidades principales:**

- Registro de Alimentación
- Reporte de Hábitos

**Eventos:**

- Datos de Sensores Recopilados
- Análisis de Hábitos Completado

**Servicios:**

- Provisión de datos históricos y visualización para el usuario.
- Envío de notificaciones cuando se detectan hábitos fuera de lo normal.

#### 4.1.1.2. Domain Message Flows Modeling.

![](https://i.gyazo.com/5df3fd81b10ffae91e90589fb9f013c3.png)

#### 4.1.1.3. Bounded Context Canvases.

![](https://i.gyazo.com/5ae9f6549f020c6d89c68b597056abfe.png)

![](https://i.gyazo.com/17567cdfc9034fa3cc90b0ee806e2296.png)

![](https://i.gyazo.com/0f81f62c7c0486920bbf3bc42a4830d3.png)

![](https://i.gyazo.com/50be0d7e161a2c646e14e2443cbbc700.png)

![](https://i.gyazo.com/9ac22d918e18fa93a1817a35d1658c39.png)

![](https://i.gyazo.com/a67304a57a539771846ff52ca8a7e100.png)

![](https://i.gyazo.com/7868057c2f982cdbac7055d0d8496274.png)

### 4.1.2. Context Mapping.

![](https://i.gyazo.com/516e6344120871067e2b81c841e5947e.png)

### 4.1.3. Software Architecture.

#### 4.1.3.1. Software Architecture System Landscape Diagram.

![](https://i.gyazo.com/4c411467e0b1e0d1bf4e8ad4d30f0617.png)

#### 4.1.3.2. Software Architecture Context Level Diagrams.

![](https://i.gyazo.com/6e3c07fd5c6e790c725eb7c61dac3c3e.png)

#### 4.1.3.3. Software Architecture Container Level Diagram

![](https://i.gyazo.com/ec5ea675b6b3404e00a5da066c4c50f5.png)

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
