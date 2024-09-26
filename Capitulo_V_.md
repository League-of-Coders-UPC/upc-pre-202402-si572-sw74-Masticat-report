# Capítulo V: Solution UI/UX Design

## 5.1. Style Guidelines

### 5.1.1. General Style Guidelines

**Overview:**
Nuestra misión es cautivar la atención del usuario desde el primer momento, creando un diseño que establezca una conexión inmediata y reconocible con Masticat.

**Brand Name:**
Hemos elegido llamar a nuestra solución "Masticat" debido a su enfoque en ayudar a los usuarios y su tecnología avanzada.

**Typography:**
Hemos seleccionado cuidadosamente las fuentes "Poppins" y "Satisfy" para transmitir una imagen moderna y legible.

[![Image from Gyazo](https://i.gyazo.com/9383947659daaf8a4cb3360caf3b78f7.png)](https://gyazo.com/9383947659daaf8a4cb3360caf3b78f7)

[![Image from Gyazo](https://i.gyazo.com/f34cb1bd09ae16c0f4311cc9f41b8298.png)](https://gyazo.com/f34cb1bd09ae16c0f4311cc9f41b8298)

**Colors:**
Los colores principales son el azul y el amarillo. El azul se ha seleccionado por su asociación con la energía, la creatividad y la emoción. Este color refleja nuestra pasión por brindar un servicio excepcional y experiencias emocionantes a nuestros usuarios. El amarillo se utiliza como color principal para el fondo, proporcionando un contraste elegante y una apariencia limpia.

[![Image from Gyazo](https://i.gyazo.com/ee409c3794cbbf58090eaf40d9d33f84.png)](https://gyazo.com/ee409c3794cbbf58090eaf40d9d33f84)

**Spacing:** 
Hemos establecido niveles de espacio que van desde 8px hasta 96px para garantizar un diseño equilibrado y una experiencia visual agradable.

[![Image from Gyazo](https://i.gyazo.com/e62bd6f082dc683ce6e1851f666a40a8.png)](https://gyazo.com/e62bd6f082dc683ce6e1851f666a40a8)

**Button:**

[![Image from Gyazo](https://i.gyazo.com/70befa2af7f43265dba610b32491b660.png)](https://gyazo.com/70befa2af7f43265dba610b32491b660)

### Web Style Guidelines

Masticat se desarrollará tanto para plataforma web, por lo tanto, implementaremos un diseño adaptable (Web Responsive Design) que tiene como finalidad mostrar la información de manera óptima en cualquier tipo de dispositivo, garantizando que el contenido se mantenga intacto para mejorar la experiencia del usuario.

[![Image from Gyazo](https://i.gyazo.com/11fa23497a630c9bfec653d1b50e3b49.png)](https://gyazo.com/11fa23497a630c9bfec653d1b50e3b49)

### 5.1.2. Web, Mobile and IoT Style Guidelines

#### Web Style Guidelines
La plataforma web de Masticat implementa un diseño responsivo para asegurar una visualización óptima en todos los tipos de dispositivos. Los principios clave incluyen:
- Grillas fluidas que se adaptan a los tamaños de pantalla
- Imágenes y medios flexibles
- Media queries de CSS para ajustar los diseños
- Enfoque mobile-first

#### Mobile Style Guidelines
Para la aplicación móvil:
- Navegación inferior para acciones primarias
- Gestos de deslizamiento para acciones comunes
- Grandes áreas táctiles (mínimo 44x44 píxeles)
- Jerarquía visual clara con diseño basado en tarjetas

#### IoT Style Guidelines
Para interfaces de dispositivos IoT:
- Diseño minimalista con enfoque en información esencial
- Alto contraste para legibilidad en varias condiciones de iluminación
- Iconos grandes y fácilmente reconocibles
- Retroalimentación háptica para interacciones del usuario

## 5.2. Information Architecture

En esta sección, presentaremos las decisiones y el sustento que guían la organización del contenido en las experiencias web y móvil de Masticat, incluyendo el Landing Page y las Aplicaciones. Nuestro objetivo es facilitar que los dueños de mascotas y profesionales veterinarios se adapten fácilmente a la funcionalidad de nuestro dispensador inteligente y encuentren todo lo que necesiten sin esfuerzo.

### 5.2.1. Organization Systems

Para Masticat, aplicaremos los siguientes sistemas de organización:

**Organización Visual del Contenido (Visual Hierarchy):**
Utilizaremos una jerarquía visual en la página de inicio para destacar las características clave del dispensador Masticat.

- Ejemplo: En la parte superior, mostraremos una imagen del dispositivo con sus principales funciones (sensores de proximidad, medición de peso), seguida por los beneficios para mascotas y dueños.

**Organización Secuencial (Step-by-Step to Accomplish):**
Implementaremos este sistema para guiar a los usuarios a través del proceso de configuración del dispensador Masticat.

- Ejemplo: Un asistente de configuración que lleve al usuario paso a paso por la instalación, conexión a la app y programación de horarios de alimentación.

**Organización Matricial:**
Usaremos esta organización para presentar comparativas de diferentes modelos de Masticat para usuarios premium y para usuarios de acceso gratis.

- Ejemplo: Una tabla que muestre las características y capacidades de los modelos.

### 5.2.2. Labeling Systems

En el contexto de Masticat, los sistemas de etiquetado juegan un papel fundamental en la organización y accesibilidad de la información en nuestra plataforma. Estos nombres se encuentran en enlaces, menús y pie de página, así como en encabezados que indican la jerarquía de la información. Son esenciales para permitir a los dueños de mascotas y profesionales veterinarios navegar fácilmente por nuestro sitio web y encontrar la información que necesitan sobre nuestros dispensadores inteligentes.

Las etiquetas que utilizamos deben tener en cuenta las implicaciones de SEO, lo que significa que deben cumplir con los siguientes objetivos:

- **Nivel de Experiencia de Usuario (UX):** Las etiquetas proporcionarán información y contexto claros para que los usuarios comprendan la función de los elementos etiquetados, facilitando la comprensión de las características y beneficios de Masticat.
- **Nivel SEO:** Utilizaremos el etiquetado interno para enlazar las páginas de Masticat de manera que tengan sentido entre sí, mejorando así la optimización de motores de búsqueda y reforzando la relevancia de nuestro contenido sobre alimentación de mascotas y tecnología IoT.

**Palabras Clave y Etiquetado Adecuado:** 
Cada página de Masticat contendrá palabras clave relevantes y un etiquetado apropiado para distribuir los términos de manera efectiva y evitar la competencia interna entre páginas.

**Impacto de las Etiquetas en Menús y Bloques Estáticos:** 
Reconocemos que las palabras clave contenidas en los menús y en los bloques estáticos tienen un mayor impacto en la navegación y visibilidad de Masticat.

#### Tipos de Etiquetas

- **Etiquetas Contextuales:** Estas etiquetas describen los enlaces en Masticat y son cruciales para conectar diferentes partes de la plataforma. Elegiremos cuidadosamente las palabras para estas etiquetas para evitar ambigüedades y garantizar que los usuarios comprendan el contenido al hacer clic en ellas.

[![Image from Gyazo](https://i.gyazo.com/938fe8bddbf8c71e0fd63096cffc0c84.png)](https://gyazo.com/938fe8bddbf8c71e0fd63096cffc0c84)
  
- **Etiquetas de Encabezado:** Las etiquetas de encabezado serán utilizadas para indicar la temática y jerarquía de contenido en Masticat. Por ejemplo, en la página de productos, utilizaremos encabezados como "Dispensadores para Hogar" y "Soluciones para Clínicas Veterinarias". Los encabezados ayudan a diferenciar las secciones del contenido y su importancia relativa.

[![Image from Gyazo](https://i.gyazo.com/e1eb4bc08106b3385e2c1b63340c1c47.png)](https://gyazo.com/e1eb4bc08106b3385e2c1b63340c1c47)

- **Etiquetas con Parámetro ALT:** En Masticat, las etiquetas con parámetro ALT se emplearán para proporcionar descripciones alternativas a las imágenes en nuestra plataforma. Por ejemplo, una imagen de nuestro dispensador tendrá una etiqueta ALT como "Dispensador inteligente Masticat con sensor de proximidad y medidor de peso". Estas descripciones son esenciales para la accesibilidad web, permitiendo a usuarios con tecnologías de asistencia comprender el contenido de las imágenes.

[![Image from Gyazo](https://i.gyazo.com/49ae51a786d2750d32f251654fc31b9e.png)](https://gyazo.com/49ae51a786d2750d32f251654fc31b9e)

### 5.2.3. SEO Tags and Meta Tags

En Masticat, comprendemos la importancia de optimizar nuestras páginas tanto en la Landing Page como en la Web Application para mejorar la visibilidad en los motores de búsqueda y brindar una experiencia de usuario de alta calidad. A continuación, se detallan los principales SEO Tags y Meta Tags que utilizaremos, junto con los valores asignados:

- **Title (Título):** 
  El título de una página es clave para captar la atención de los usuarios y mejorar la indexación en los motores de búsqueda. Ejemplo: "Masticat - Alimentación Inteligente para Mascotas".

[![Image from Gyazo](https://i.gyazo.com/0bd167e567219198a7cbf7fb42bc9dff.png)](https://gyazo.com/0bd167e567219198a7cbf7fb42bc9dff)
  
- **Meta Tags de Descripción (Meta Description):** 
  Las descripciones serán breves y atractivas, destacando los beneficios de Masticat. Ejemplo: "Descubre cómo Masticat mejora la alimentación de tu mascota con un dispensador inteligente y monitoreo desde cualquier lugar".
  
- **Meta Tags de Palabras Clave (Keywords):** 
  Aunque el enfoque en las palabras clave ha evolucionado en el SEO, consideraremos palabras clave relevantes para cada página y las incluiremos en los meta tags de keywords cuando sea apropiado.
  
- **Meta Tag de Autor (Author):** 
  Utilizaremos el meta tag de autor para identificar al creador o autor del contenido, lo que puede ayudar a establecer credibilidad y autoridad en la industria.

Este enfoque alineará la estrategia SEO de Masticat con su visión de ofrecer soluciones tecnológicas avanzadas para la alimentación y el cuidado de mascotas.

### 5.2.4. Searching Systems

En Masticat, hemos desarrollado un sistema de búsqueda avanzado que facilita a los usuarios encontrar rápidamente la información sobre el estado de alimentación de sus mascotas y configurar el dispositivo según sus necesidades. A continuación, detallamos cómo hemos diseñado nuestro sistema de búsqueda para que los usuarios puedan manejar la información sin sentirse abrumados:

**Opciones de Búsqueda:**

Ofrecemos a nuestros usuarios diversas opciones de búsqueda para personalizar su experiencia en la plataforma. Estas incluyen:

- **Estado de alimentación:** Permite a los usuarios ver la cantidad de alimento que queda, la frecuencia de dispensado y los hábitos alimenticios de su mascota.
- **Configuraciones del dispositivo:** Los usuarios pueden buscar y ajustar las configuraciones del dispensador, como la programación de comidas y la cantidad de alimento dispensado.
- **Historial de uso:** Facilita la consulta de datos pasados sobre el consumo de alimentos y agua de la mascota.
- **Alertas y notificaciones:** Los usuarios pueden encontrar notificaciones sobre alertas importantes como niveles bajos de comida o mal funcionamiento del dispositivo.

Esto permite a los usuarios filtrar la información que más les interesa y acceder de manera rápida a los datos necesarios para el cuidado de sus mascotas.

[![Image from Gyazo](https://i.gyazo.com/f178e382475841ed12a391ee65275490.png)](https://gyazo.com/f178e382475841ed12a391ee65275490)

### 5.2.5. Navigation Systems

En Masticat, hemos diseñado un sistema de navegación intuitivo y sencillo que guía a los usuarios a través de nuestra Landing Page y la aplicación móvil/web, permitiéndoles interactuar de manera eficiente con el dispensador inteligente y las demás funcionalidades del producto. A continuación, explicamos cómo los usuarios podrán navegar por nuestro sistema:

**Barra de Navegación:**
Hemos implementado una barra de navegación en la parte superior de la plataforma con cinco opciones principales:

- **Inicio:** Lleva a los usuarios a la página de inicio, donde pueden ver el estado actual de su dispensador y acceder a información general sobre la salud y alimentación de su mascota.
- **Perfil de Mascotas:** Permite a los usuarios gestionar los perfiles de sus mascotas, agregando o actualizando información como nombre, peso y hábitos alimenticios.
- **Programación de Alimentación:** En esta sección, los usuarios pueden programar y personalizar los horarios de alimentación de su mascota, así como ajustar las cantidades de comida dispensada.
- **Historial y Reportes:** Los usuarios pueden acceder a un historial detallado de los datos de alimentación, consumo de agua y otros parámetros importantes, junto con reportes automáticos generados por la aplicación.
- **Configuraciones del Dispositivo:** Aquí, los usuarios pueden ajustar la configuración del dispensador, incluyendo la calibración de sensores y activar/desactivar el dispensador automático.

Nuestro sistema de navegación en Masticat está diseñado para garantizar que los usuarios puedan alcanzar sus metas fácilmente, ya sea monitorear la alimentación de su mascota, ajustar las configuraciones del dispensador, o consultar reportes detallados, brindándoles una experiencia eficiente y satisfactoria.

[![Image from Gyazo](https://i.gyazo.com/f178e382475841ed12a391ee65275490.png)](https://gyazo.com/f178e382475841ed12a391ee65275490)

## 5.3. Landing Page UI Design

### 5.3.1. Landing Page Wireframe
Hemos creado una representación inicial en forma de bosquejo de baja fidelidad para la página de inicio de Masticat:

[![Image from Gyazo](https://i.gyazo.com/33db07c65e8dd351a5583165f3a26991.png)](https://gyazo.com/33db07c65e8dd351a5583165f3a26991)

### 5.3.2. Landing Page Mock-up
El Landing Page se desarrolló utilizando un prototipo de fidelidad intermedia en forma de Mock Up. A continuación, te presentamos una vista previa de nuestra propuesta:

[![Image from Gyazo](https://i.gyazo.com/f6fd623d5ae366a14e32d70c3765f15a.png)](https://gyazo.com/f6fd623d5ae366a14e32d70c3765f15a)

