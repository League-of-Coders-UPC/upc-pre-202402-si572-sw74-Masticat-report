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
- Control del acceso a funcionalidades premium (cámaras).

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

- Activación de la cámara (si está disponible) para el monitoreo visual de la mascota.

**Entidades principales:**

- Cámara

**Eventos:**

- Visualización de la mascota

**Servicios:**

- Control de parámetros avanzados como cámaras.

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

![](https://i.gyazo.com/24b0e1c664550483d4a5c072a72ecc78.png)

Este diagrama representa una vista de alto nivel del Sistema Masticat y sus interacciones con los usuarios y sistemas externos. El sistema central gestiona los dispositivos y aplicaciones Masticat y está compuesto por dos tipos de usuarios: los domésticos, que son los usuarios finales, y los empleadores veterinarios, que son los profesionales que utilizan las interfaces del sistema. También se incluyen sistemas externos como Paypal, que maneja el procesamiento de pagos, y AuthZed, que proporciona servicios de autorización escalables.

#### 4.1.3.2. Software Architecture Context Level Diagrams.

![](https://i.gyazo.com/24b0e1c664550483d4a5c072a72ecc78.png)

Desde una perspectiva de nivel de contexto, este diagrama ilustra los límites del Sistema Masticat y sus interacciones inmediatas. El sistema es responsable de gestionar los dispositivos y aplicaciones Masticat, y tiene dos tipos de usuarios: el usuario doméstico, que interactúa con las interfaces, y el empleador veterinario, que tiene diferentes niveles de acceso. Las dependencias externas incluyen a Paypal, como pasarela de pago, y AuthZed, para servicios de autenticación y autorización.
Este diagrama de contexto define claramente el alcance del sistema, mostrando sus interfaces principales y dependencias externas sin entrar en complejidades internas, estableciendo un límite claro de lo que está en el alcance del Sistema Masticat y lo que es manejado por servicios externos.

#### 4.1.3.3. Software Architecture Container Level Diagram

![](https://i.gyazo.com/308ec388e1c55b5f730ecafeb65ae075.png)

El diagrama presenta la arquitectura de contenedores del Sistema Masticat, destacando sus componentes e interacciones. Incluye dos interfaces de usuario: una aplicación móvil y una web, que se conectan a través de un API Gateway central.
El núcleo del sistema consta de varios microservicios, como Configuración y Planificación, Perfil, Operación, Monitoreo, Gestión de Identidad y Acceso, Ejecución de Servicios, y Suscripciones y Pagos, cada uno con su propia base de datos, siguiendo el principio de segregación de datos. También se integra con componentes externos como la API Edge para la comunicación con dispositivos, AuthZed para autorización, y Paypal para gestión de pagos.
La arquitectura utiliza un API Gateway para centralizar la gestión de solicitudes, mejorando la seguridad y el monitoreo, y la separación de bases de datos mantiene un bajo acoplamiento entre los componentes. En resumen, el diagrama muestra una arquitectura moderna, diseñada para manejar las complejidades de un sistema distribuido como Masticat, ofreciendo flexibilidad para futuras expansiones.

#### 4.1.3.4. Software Architecture Deployment Diagrams

![]()

# Bounded Contexts

## 4.2. Profile Bounded Context

### 4.2.1. Domain Layer

#### Entities

- User
  - **Attributes:** Id, Name, Email, PhoneNumber, Address, DateOfBirth
  - **Methods:** Create(), Update(), Delete(), ChangeEmail(), UpdatePassword(), AddPet(), RemovePet(), UpdatePreferences(), GetProfile()
  - **Description:** Represents a user of the system with their personal information and related actions.

- Pet
  - **Attributes:** Id, Name, Species, Breed, DateOfBirth, Weight, Microchip, OwnerId
  - **Methods:** Register(), Update(), Delete(), UpdateWeight(), UpdateMicrochip(), TransferOwner(), GetMedicalHistory(), ScheduleVetAppointment()
  - **Description:** Represents a pet registered in the system with its characteristics and associated actions.

- Preferences
  - **Attributes:** Id, UserId, NotificationSettings, LanguagePreference, ThemePreference
  - **Methods:** Save(), Load(), Delete(), UpdateNotificationSettings(), ChangeLanguage(), ChangeTheme(), EnableFeature(), DisableFeature()
  - **Description:** Stores user preferences, including notification settings and customization.

#### Aggregates

User and Pet form an aggregate, as there is a strong relationship between them.

#### Domain Services

Services to manage complex relationships between User and Pet, such as pet transfer between users.

#### Repositories

IUserRepository, IPetRepository, IPreferencesRepository

### 4.2.2. Interface Layer

#### Controllers

- UserController: Manages CRUD operations for users and their profiles.
- PetController: Manages CRUD operations for pets and their medical records.
- PreferencesController: Manages user preferences and application customization.

### 4.2.3. Application Layer

#### Command Handlers

- CreateUserCommandHandler
- UpdatePetCommandHandler
- UpdatePreferencesCommandHandler

#### Event Handlers

- UserCreatedEventHandler
- PetUpdatedEventHandler
- PreferencesChangedEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- UserRepository: Implementation of IUserRepository.
- PetRepository: Implementation of IPetRepository.
- PreferencesRepository: Implementation of IPreferencesRepository.

#### External Services

Connections to databases, external APIs for profile management, authentication services, etc.

### 4.2.6. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/e53c5b8a1596de5939a346f8479de07d.png)](https://gyazo.com/e53c5b8a1596de5939a346f8479de07d)

**Description of Component Diagram:** El diagrama de componentes para el Contexto Delimitado de Perfil ilustra la estructura de alto nivel del sistema. Muestra los principales servicios (UserService, PetService, PreferencesService) interactuando con sus respectivos repositorios. Estos servicios se exponen a través de controladores API, que manejan las solicitudes entrantes. El diagrama también representa la capa de aplicación con manejadores de comandos y eventos, mostrando la arquitectura orientada a eventos del sistema.

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/e47d057badfcf148ab88567a9c3f7fbc.png)](https://gyazo.com/e47d057badfcf148ab88567a9c3f7fbc)

**Description of Class Diagram:** El diagrama de clases para el Contexto Delimitado de Perfil presenta las entidades principales del dominio y sus relaciones. Muestra la clase User como entidad central, con asociaciones a Pet (uno a muchos) y Preferences (uno a uno). La clase UserProfile representa una vista consolidada de la información del usuario. Cada clase se detalla con sus atributos y métodos, ilustrando claramente la estructura y el comportamiento del modelo de dominio.

#### 4.2.7.2. Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/f4e8678592d74afe674bd8dddbfffe24.png)](https://gyazo.com/f4e8678592d74afe674bd8dddbfffe24)

**Description of Database Diagram:** El diagrama de base de datos para el Contexto Delimitado de Perfil describe la estructura de datos que soporta el modelo de dominio. Incluye tablas para Users, Pets, Preferences y UserProfiles, con sus respectivos campos y relaciones claramente definidas. El diagrama muestra relaciones de clave foránea, indicando cómo se vinculan los datos entre tablas (por ejemplo, Pets haciendo referencia a Users mediante OwnerId).

## 2. IAM (Identity and Access Management) Bounded Context

### 4.2.1. Domain Layer

#### Entities

- Credentials
  - **Attributes:** Id, UserId, PasswordHash
  - **Methods:** Validate(), ChangePassword()
  - **Description:** Represents user authentication credentials.

- Role
  - **Attributes:** Id, Name, Description
  - **Methods:** Assign(), Remove()
  - **Description:** Represents a user role in the system.

- Permission
  - **Attributes:** Id, RoleId, Resource
  - **Methods:** Assign(), Revoke()
  - **Description:** Represents permissions associated with roles.

#### Aggregates

Credentials, Roles, and Permissions form an aggregate.

#### Domain Services

Services for managing complex relationships between Credentials, Roles, and Permissions.

#### Repositories

ICredentialsRepository, IRoleRepository, IPermissionRepository

### 4.2.2. Interface Layer

#### Controllers

- AuthController: Manages authentication operations.
- RoleController: Manages role and permission operations.

### 4.2.3. Application Layer

#### Command Handlers

- LoginCommandHandler
- AssignRoleCommandHandler

#### Event Handlers

- UserAuthenticatedEventHandler
- RoleAssignedEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- CredentialsRepository: Implementation of ICredentialsRepository.
- RoleRepository: Implementation of IRoleRepository.
- PermissionRepository: Implementation of IPermissionRepository.

### 4.2.7. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/5d3c7a51e45fbf05e65a0bad197b7b46.png)](https://gyazo.com/5d3c7a51e45fbf05e65a0bad197b7b46)

**Description of Component Diagram:** El Diagrama de Componentes de IAM representa la arquitectura para gestionar la autenticación y autorización de usuarios. Muestra AuthService y RoleService como componentes centrales, interactuando con sus respectivos repositorios. El diagrama incluye controladores API para manejar solicitudes relacionadas con autenticación y roles, así como manejadores de comandos y eventos en la capa de aplicación.


### 4.2.6. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/5faf9e374a83ed3d9da62a56017dede9.png)](https://gyazo.com/5faf9e374a83ed3d9da62a56017dede9)

**Description of Class Diagram:** El Diagrama de Clases de IAM ilustra las relaciones entre las entidades clave en el dominio de autenticación y autorización. Muestra la clase Credentials vinculada a User, y las clases Role y Permission formando la base del modelo de autorización. El diagrama define claramente los atributos y métodos de cada clase, proporcionando una visión completa del modelo de dominio de IAM.

#### 4.2.7.2. Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/43bc0dc7c31d65c15ecba691e463f8db.png)](https://gyazo.com/43bc0dc7c31d65c15ecba691e463f8db)

**Description of Database Diagram:** El Diagrama de Base de Datos de IAM presenta la estructura de datos para almacenar información de autenticación y autorización. Incluye tablas para Credentials, Roles y Permissions, con sus relaciones claramente definidas. El diagrama muestra cómo las credenciales de usuario están vinculadas a roles y cómo los roles están asociados con permisos específicos.

## 3. Subscriptions and Payments Bounded Context

### 4.2.1. Domain Layer

#### Entities

- SubscriptionPlan
  - **Attributes:** Id, Name, Price, Duration
  - **Methods:** Create(), Update(), Delete()
  - **Description:** Represents a subscription plan available to users.

- Payment
  - **Attributes:** Id, UserId, Amount, Date, Status
  - **Methods:** Process(), Refund(), GetStatus()
  - **Description:** Represents a payment made by a user.

- Invoice
  - **Attributes:** Id, PaymentId, Details, IssueDate
  - **Methods:** Generate(), Cancel(), Send()
  - **Description:** Represents an invoice for a payment.

#### Aggregates

SubscriptionPlan, Payment, and Invoice form an aggregate.

#### Domain Services

Services for managing complex operations like subscription renewals and payment processing.

#### Repositories

ISubscriptionPlanRepository, IPaymentRepository, IInvoiceRepository

### 4.2.2. Interface Layer

#### Controllers

- SubscriptionController: Manages subscription-related operations.
- PaymentController: Manages payment and invoicing operations.

### 4.2.3. Application Layer

#### Command Handlers

- CreateSubscriptionCommandHandler
- ProcessPaymentCommandHandler

#### Event Handlers

- SubscriptionCreatedEventHandler
- PaymentProcessedEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- SubscriptionPlanRepository: Implementation of ISubscriptionPlanRepository.
- PaymentRepository: Implementation of IPaymentRepository.
- InvoiceRepository: Implementation of IInvoiceRepository.

### 4.2.6. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/dc40968be14718517641f2223dbe66f9.png)](https://gyazo.com/dc40968be14718517641f2223dbe66f9)

**Description of Component Diagram:** El Diagrama de Componentes de Suscripciones y Pagos describe la arquitectura para gestionar las suscripciones de usuarios y el procesamiento de pagos. Representa SubscriptionService y PaymentService como componentes centrales, cada uno con su respectivo repositorio. El diagrama incluye controladores para manejar solicitudes de suscripción y pago, junto con manejadores de comandos y eventos para procesar estas operaciones.

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/50c2c7ca98a16537d903233a96fa4319.png)](https://gyazo.com/50c2c7ca98a16537d903233a96fa4319)

**Description of Class Diagram:** El Diagrama de Clases de Suscripciones y Pagos muestra las relaciones entre entidades clave como SubscriptionPlan, Payment e Invoice. Detalla los atributos y métodos de cada clase, proporcionando una imagen clara de cómo se modelan las suscripciones y pagos en el sistema.

#### 4.2.7.2. Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/3a444633e935ab1d783f23ffadce65a7.png)](https://gyazo.com/3a444633e935ab1d783f23ffadce65a7)


**Description of Database Diagram:** El Diagrama de Base de Datos de Suscripciones y Pagos ilustra la estructura de datos para almacenar información de suscripciones y pagos. Incluye tablas para SubscriptionPlans, Payments e Invoices, con sus relaciones y campos clave claramente definidos. El diagrama muestra cómo los pagos están vinculados a planes de suscripción específicos y cómo se generan las facturas para cada pago.

## 4. Configuration and Planning Bounded Context

### 4.2.1. Domain Layer

#### Entities

- DeviceConfiguration
  - **Attributes:** Id, DeviceId, Configuration
  - **Methods:** Configure(), GetConfiguration()
  - **Description:** Represents the configuration of a device.

- FeedingSchedule
  - **Attributes:** Id, PetId, Time, Amount
  - **Methods:** Schedule(), Update(), Cancel()
  - **Description:** Represents a feeding schedule for a pet.

- SensorConfiguration
  - **Attributes:** Id, SensorId, Configuration
  - **Methods:** Configure(), ReadConfiguration()
  - **Description:** Represents the configuration of a sensor.

#### Aggregates

DeviceConfiguration, FeedingSchedule, and SensorConfiguration form an aggregate.

#### Domain Services

Services for managing complex configurations and scheduling operations.

#### Repositories

IDeviceConfigurationRepository, IFeedingScheduleRepository, ISensorConfigurationRepository

### 4.2.2. Interface Layer

#### Controllers

- DeviceConfigurationController: Manages device configuration operations.
- FeedingScheduleController: Manages feeding schedule operations.
- SensorConfigurationController: Manages sensor configuration operations.

### 4.2.3. Application Layer

#### Command Handlers

- ConfigureDeviceCommandHandler
- ScheduleFeedingCommandHandler

#### Event Handlers

- DeviceConfiguredEventHandler
- FeedingScheduledEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- DeviceConfigurationRepository: Implementation of IDeviceConfigurationRepository.
- FeedingScheduleRepository: Implementation of IFeedingScheduleRepository.
- SensorConfigurationRepository: Implementation of ISensorConfigurationRepository.

### 4.2.6. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/c37ac755a1741164086038435ce01e35.png)](https://gyazo.com/c37ac755a1741164086038435ce01e35)

**Description of Component Diagram:** El Diagrama de Componentes de Configuración y Planificación muestra la arquitectura para gestionar las configuraciones de dispositivos y los horarios de alimentación. Incluye servicios para DeviceConfiguration, FeedingSchedule y SensorConfiguration, cada uno con su correspondiente repositorio. El diagrama también representa controladores y manejadores de comandos/eventos para gestionar estas configuraciones.

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/eb901c80559c13e6a80e050d6ce365f5.png)](https://gyazo.com/eb901c80559c13e6a80e050d6ce365f5)

**Description of Class Diagram:** El Diagrama de Clases de Configuración y Planificación ilustra las relaciones entre entidades como DeviceConfiguration, FeedingSchedule y SensorConfiguration. Detalla los atributos y métodos de cada clase, proporcionando una comprensión clara de cómo se modelan las configuraciones de dispositivos y alimentación en el sistema.

#### 4.2.7.2. Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/f9f5de9a982cc567237939f64ee6b8a3.png)](https://gyazo.com/f9f5de9a982cc567237939f64ee6b8a3)

**Description of Database Diagram:** El Diagrama de Base de Datos de Configuración y Planificación describe la estructura de datos para almacenar información de configuración y programación. Incluye tablas para DeviceConfigurations, FeedingSchedules y SensorConfigurations, con sus relaciones y campos clave claramente definidos. El diagrama muestra cómo estas configuraciones están vinculadas a dispositivos y mascotas específicos.

## 5. Operation Bounded Context

### Entities

- Dispensing
  - **Attributes:** Id, DeviceId, Amount, Time
  - **Methods:** Dispense(), GetHistory()
  - **Description:** Represents a food or water dispensing action.

- SensorReading
  - **Attributes:** Id, SensorId, Value, Timestamp
  - **Methods:** Record(), Analyze()
  - **Description:** Represents a reading from a sensor.

- DeviceStatus
  - **Attributes:** Id, DeviceId, Status, LastUpdateTime
  - **Methods:** UpdateStatus(), GetStatus()
  - **Description:** Represents the current status of a device.

### Aggregates

Dispensing, SensorReading, and DeviceStatus form an aggregate.

### Domain Services

Services for managing complex operations like data analysis and device monitoring.

### Repositories

IDispensingRepository, ISensorReadingRepository, IDeviceStatusRepository

### 4.2.2. Interface Layer

#### Controllers

- DispensingController: Manages food and water dispensing operations.
- SensorReadingController: Manages sensor reading operations.
- DeviceStatusController: Manages device status operations.

### 4.2.3. Application Layer

#### Command Handlers

- DispenseFoodCommandHandler
- RecordSensorReadingCommandHandler

#### Event Handlers

- FoodDispensedEventHandler
- SensorReadingRecordedEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- DispensingRepository: Implementation of IDispensingRepository.
- SensorReadingRepository: Implementation of ISensorReadingRepository.
- DeviceStatusRepository: Implementation of IDeviceStatusRepository.

### 4.2.6. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/116b1d28a611b74dfb9a78560f3204b2.png)](https://gyazo.com/116b1d28a611b74dfb9a78560f3204b2)

**Description of Component Diagram:** El Diagrama de Componentes de Operación ilustra la arquitectura para gestionar las operaciones centrales del sistema IoT de cuidado de mascotas. Muestra servicios para Dispensing, SensorReading y DeviceStatus, cada uno con su respectivo repositorio. El diagrama incluye controladores para manejar solicitudes operativas y manejadores de comandos/eventos para procesar estas operaciones.

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/92dc5fce2cbbb5b61523326c962c3051.png)](https://gyazo.com/92dc5fce2cbbb5b61523326c962c3051)

**Description of Class Diagram:** El Diagrama de Clases de Operación representa las relaciones entre entidades operativas clave como Dispensing, SensorReading y DeviceStatus. Detalla los atributos y métodos de cada clase, proporcionando una imagen clara de cómo el sistema modela y gestiona las actividades operativas centrales.

#### 4.2.7.2. Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/909ef859125b38eeccbff6912735dd4d.png)](https://gyazo.com/909ef859125b38eeccbff6912735dd4d)

**Description of Database Diagram:** El Diagrama de Base de Datos de Operación presenta la estructura de datos para almacenar datos operativos. Incluye tablas para Dispensing, SensorReadings y DeviceStatus, con sus relaciones y campos clave claramente definidos. El diagrama muestra cómo los datos operativos están vinculados a dispositivos específicos y cómo están estructurados para una recuperación y análisis eficientes.

## 6. Service Execution Bounded Context

### Entities

- Dispensing
  - **Attributes:** Id, DeviceId, Amount, Time
  - **Methods:** Dispense(), GetHistory()
  - **Description:** Represents a food or water dispensing action.

- SensorReading
  - **Attributes:** Id, SensorId, Value, Timestamp
  - **Methods:** Record(), Analyze()
  - **Description:** Represents a reading from a sensor.

- DeviceStatus
  - **Attributes:** Id, DeviceId, Status, LastUpdateTime
  - **Methods:** UpdateStatus(), GetStatus()
  - **Description:** Represents the current status of a device.

### Aggregates

Dispensing, SensorReading, and DeviceStatus form an aggregate.

### Domain Services

Services for managing complex operations like data analysis and device monitoring.

### Repositories

IDispensingRepository, ISensorReadingRepository, IDeviceStatusRepository

### 4.2.2. Interface Layer

#### Controllers

- DispensingController: Manages food and water dispensing operations.
- SensorReadingController: Manages sensor reading operations.
- DeviceStatusController: Manages device status operations.

### 4.2.3. Application Layer

#### Command Handlers

- DispenseFoodCommandHandler
- RecordSensorReadingCommandHandler

#### Event Handlers

- FoodDispensedEventHandler
- SensorReadingRecordedEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- DispensingRepository: Implementation of IDispensingRepository.
- SensorReadingRepository: Implementation of ISensorReadingRepository.
- DeviceStatusRepository: Implementation of IDeviceStatusRepository.

### 4.2.6. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/3437d9f62aa36e0e4e3c4001aac91a39.png)](https://gyazo.com/3437d9f62aa36e0e4e3c4001aac91a39)

**Description of Component Diagram:** El Diagrama de Componentes de Ejecución de Servicios describe la arquitectura para ejecutar varios servicios en el sistema IoT de cuidado de mascotas. Incluye componentes para gestionar diferentes tipos de servicios, su ejecución y monitoreo. El diagrama muestra cómo estos componentes interactúan con repositorios y cómo se exponen a través de controladores API.

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/85f1527391f2eed5ad6f27528e09bc6b.png)](https://gyazo.com/85f1527391f2eed5ad6f27528e09bc6b)

**Description of Class Diagram:** El Diagrama de Clases de Ejecución de Servicios ilustra el modelo de dominio para la ejecución de servicios. Muestra clases que representan diferentes tipos de servicios, registros de ejecución y entidades relacionadas. El diagrama detalla los atributos y métodos de cada clase, proporcionando información sobre cómo se modela y gestiona la ejecución de servicios.


#### 4.2.7.2. Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/a08a466b4181abcbcc4785cdbc46b372.png)](https://gyazo.com/a08a466b4181abcbcc4785cdbc46b372)

**Description of Database Diagram:** El Diagrama de Base de Datos de Ejecución de Servicios presenta la estructura de datos para almacenar datos de ejecución de servicios. Incluye tablas para diferentes tipos de servicios, registros de ejecución e información relacionada. El diagrama muestra cómo los datos de ejecución están vinculados a servicios y dispositivos específicos, y cómo están estructurados para seguimiento y análisis.

## 7. Monitoring Bounded Context

### Entities

- Dispensing
  - **Attributes:** Id, DeviceId, Amount, Time
  - **Methods:** Dispense(), GetHistory()
  - **Description:** Represents a food or water dispensing action.

- SensorReading
  - **Attributes:** Id, SensorId, Value, Timestamp
  - **Methods:** Record(), Analyze()
  - **Description:** Represents a reading from a sensor.

- DeviceStatus
  - **Attributes:** Id, DeviceId, Status, LastUpdateTime
  - **Methods:** UpdateStatus(), GetStatus()
  - **Description:** Represents the current status of a device.

### Aggregates

Dispensing, SensorReading, and DeviceStatus form an aggregate.

### Domain Services

Services for managing complex operations like data analysis and device monitoring.

### Repositories

IDispensingRepository, ISensorReadingRepository, IDeviceStatusRepository

### 4.2.2. Interface Layer

#### Controllers

- DispensingController: Manages food and water dispensing operations.
- SensorReadingController: Manages sensor reading operations.
- DeviceStatusController: Manages device status operations.

### 4.2.3. Application Layer

#### Command Handlers

- DispenseFoodCommandHandler
- RecordSensorReadingCommandHandler

#### Event Handlers

- FoodDispensedEventHandler
- SensorReadingRecordedEventHandler

### 4.2.4. Infrastructure Layer

#### Repository Implementations

- DispensingRepository: Implementation of IDispensingRepository.
- SensorReadingRepository: Implementation of ISensorReadingRepository.
- DeviceStatusRepository: Implementation of IDeviceStatusRepository.

### 4.2.6. Bounded Context Software Architecture Component Level Diagrams

[![Image from Gyazo](https://i.gyazo.com/76306d33966dbe7d1f17723b5e25f30b.png)](https://gyazo.com/76306d33966dbe7d1f17723b5e25f30b)

**Description of Component Diagram:** El Diagrama de Componentes de Monitoreo representa la arquitectura para monitorear el sistema IoT de cuidado de mascotas. Muestra componentes para recopilación de datos, análisis y alertas. El diagrama incluye servicios para procesar diferentes tipos de datos de monitoreo, sus interacciones con repositorios y cómo se exponen a través de controladores API.

### 4.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.1. Bounded Context Domain Layer Class Diagrams

[![Image from Gyazo](https://i.gyazo.com/2b942ad120772eaeb4ccfc12595c564b.png)](https://gyazo.com/2b942ad120772eaeb4ccfc12595c564b)

**Description of Class Diagram:** El Diagrama de Clases de Monitoreo ilustra el modelo de dominio para el monitoreo del sistema. Muestra clases que representan diferentes tipos de datos de monitoreo, alertas y resultados de análisis. El diagrama detalla los atributos y métodos de cada clase, proporcionando una imagen clara de cómo se modelan las actividades de monitoreo en el sistema.

#### 4.2.7.7 Bounded Context Database Design Diagram

[![Image from Gyazo](https://i.gyazo.com/c1fb6295df16ff9f935e88a14c241924.png)](https://gyazo.com/c1fb6295df16ff9f935e88a14c241924)

**Description of Database Diagram:** El Diagrama de Base de Datos de Monitoreo describe la estructura de datos para almacenar datos de monitoreo. Incluye tablas para diferentes tipos de registros de monitoreo, alertas y resultados de análisis. El diagrama muestra cómo los datos de monitoreo están vinculados a dispositivos y sensores específicos, y cómo están estructurados para consultas e informes eficientes.
