<div style="text-align: justify;">

<p align="left"><a href="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Tabla_de_Contenidos.md">Volver a tabla de contenidos</a></p>


## 1.1 Startup Profile
### 1.1.1 Descripción de la Startup

Masticat es una startup creada con el propósito de optimizar la experiencia de alimentación y cuidado de las mascotas haciendo uso de soluciones tecnológicas basadas en IoT. Nuestro objetivo es simplificar las rutinas de alimentación tanto en hogares como en clínicas veterinarias mediante un dispensador inteligente que se activa automáticamente cuando la mascota está cerca.

Nuestra propuesta se enfoca en entregar un producto que tenga funcionalidades avanzadas como sensores de proximidad, medición del peso de la comida y opciones para monitorear y controlar el proceso de alimentación desde una aplicación móvil o web. En Masticat buscamos mejorar la eficiencia en  la alimentación de las mascotas, facilitando la vida de los dueños y profesionales veterinarios.


### 1.1.2 Perfiles de integrantes del equipo
<div style="display: flex; align-items: center;">
    <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/djalma.png" alt="Imagen" width="150" height="100" style="margin-right: 35px;">
    <div>
        <u><strong>Djalma Dioses Molina - u201921405</strong></u><br>
        Actualmente tengo 22 años y estoy cursando la carrera de Ingeniería de Software de la Universidad Peruana de Ciencias Aplicadas (UPC). Poseo conocimientos en múltiples lenguajes de programación como: Java, JavaScript, TypeScript, C#, C++, Python, SQL, PHP, y conocimientos de múltiples frameworks. Me considero una persona colaborativa, respetuosa y me gusta trabajar en grupo.
    </div>
</div>
<br>
<div style="display: flex; align-items: center;">
    <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/christian.png" alt="Imagen" width="100" height="25%" style="margin-right: 20px;">
    <div>
        <u><strong>Christian Jose Zeta Valenzuela - u202011688</strong></u><br>
        Me llamo Christian, tengo 21 años, nací en Perú. Escogí esta carrera debido a mi gran afinidad hacia la tecnología contemporánea. Entre mis principales habilidades se encuentra la capacidad de guardar información, la empatía, el ser resiliente y tengo conocimiento en los lenguajes de C++,C#, Java y en frameworks como Vue y Angular.
    </div>
</div>
<br>
<div style="display: flex; align-items: center;">
    <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/josef.png" alt="Imagen" width="100" height="25%" style="margin-right: 20px;">
    <div>
        <u><strong>Josef Cesar Romero Florida - u201910655</strong></u><br>
        Me llamo Josef Cesar Romero Florida, tengo 22 años, nací en Perú y estoy cursando la carrera de Ingeniería de Software. Tengo un gran interés por la IA y todo lo relacionado al AGI.Mi rol laboral generalmente está centrado en el back end utilizando .NET. Me considero una persona colaborativa y empática
    </div>
</div>
<br>
<div style="display: flex; align-items: center;">
    <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/jhosaim.png" alt="Imagen" width="100" height="25%" style="margin-right: 20px;">
    <div>
        <u><strong>Jhosaim Ricardo Pocohuanca Pineda - u202115595</strong></u><br>
        Tengo 21 años, actualmente me encuentro estudiando y brindando servicios como Desarrollador Backend Semi-Senior para una empresa. Domino una amplia variedad de lenguajes de programación y herramientas. Mi mejor cualidad es lo rápido que puedo aprender nuevos conceptos y ponerlos a prueba, además de las ganas de mejorar cualquier implementación siempre. 
    </div>
</div>
<br>
<div style="display: flex; align-items: center;">
    <img src="https://github.com/League-of-Coders-UPC/upc-pre-202402-si572-sw74-Masticat-report/blob/main/Resources/images/leonardo.png" alt="Imagen" width="100" height="100" style="margin-right: 20px;">
    <div>
        <u><strong>Leonardo Jesús Ferreyra Carnaval - U202111363</strong></u><br>
        Mi camino académico ha estado marcado por un fuerte interés en desentrañar los desafíos más complejos a través de la programación y la tecnología. Mi objetivo es diseñar soluciones innovadoras que tengan un impacto significativo en nuestra sociedad. Además de mis estudios, también me dedico a proyectos personales. Creo firmemente en el poder de la colaboración y siempre busco oportunidades para trabajar en equipo y aprender de los demás.
    </div>
</div>
<br>

## 1.2 Solution Profile
### 1.2.1 Antecedentes y problemática
Para abordar esta problemática, utilizamos la técnica de The 5 W’s y 2 H’s:
#### 5W's y 2H's

* <strong>What?</strong><br>
Un dispensador automático que proporciona comida cuando la mascota está cerca.
* <strong>When?</strong><br>
Cuando la mascota lo necesite.
* <strong>Where?</strong><br>
En hogares y clínicas veterinarias.
* <strong>Who?</strong><br>
Afecta a los dueños de mascotas y a las clínicas veterinarias. Los dueños buscan una solución automatizada para alimentar a sus mascotas, mientras que las clínicas necesitan gestionar la alimentación de múltiples animales de manera eficiente.
* <strong>Why?</strong><br>
Para asegurar que las mascotas reciban la cantidad correcta de comida a tiempo sin la necesidad de la constante intervención humana.
* <strong>How?</strong><br>
Utilizando sensores que detectan la presencia de la mascota y controlan la dispensación de comida automáticamente.
* <strong>How much?</strong><br>
Reduciendo el desperdicio de comida y permitiendo una mayor eficiencia en la administración del tiempo para los dueños de mascotas y clínicas veterinarias.

#### Enunciado del problema:
El principal problema identificado es la falta de soluciones automatizadas y accesibles para la gestión eficiente de la alimentación de las mascotas. Los dueños de mascotas a menudo no pueden seguir horarios estrictos de alimentación debido a sus compromisos diarios y esto puede llevar a una nutrición desbalanceada. Por otro lado, las clínicas veterinarias requieren un control riguroso sobre las dietas de los animales, lo que resulta en una carga adicional para el personal.

#### Solución:
Masticat propone un dispensador de comida inteligente que es controlado mediante una aplicación web o móvil que responde automáticamente a la presencia de la mascota. Este dispositivo permite a los dueños de mascotas y a las clínicas veterinarias  programar horarios de alimentación, dispensar comida cuando la mascota se encuentra cerca, identificar a la mascota que ha dispensado comida, medir el peso de la comida y recibir notificaciones en tiempo real sobre el consumo de alimentos. Para las clínicas esta solución también permite llevar un registro detallado de los hábitos alimenticios de los animales que se encuentran bajo su cuidado.

#### Integración de sistemas IoT:
Masticat está basada en la tecnología IoT, integrando sensores de proximidad, medición del peso, microchips de identificación para mascotas y cámaras en su versión premium. La aplicación móvil y web actúan como interfaz para controlar y monitorear el dispensador a distancia, ofreciendo a los usuarios un control completo sobre la alimentación de sus mascotas. 

#### Monetización:
Masticat ofrece un modelo de negocio basado en la venta del dispositivo y sus versiones premium con características avanzadas como cámara y control de temperatura. También existe la posibilidad de suscripciones mensuales para acceder a funciones premium como la generación de reportes detallados de hábitos alimenticios y el análisis de los datos recopilados por el sistema. Para las clínicas veterinarias ofrecemos planes de suscripción específicos que incluyen soporte técnico y actualizaciones de software.

#### Objetivos:

Automatizar el proceso de alimentación de mascotas brindando mayor comodidad y flexibilidad a los dueños.<br>
Mejorar la precisión en la administración de comida para mascotas bajo cuidado veterinario.<br>
Integrar sensores IoT avanzados para un control más preciso y eficiente de la alimentación.<br>
Desarrollar una plataforma móvil y web que permitan gestionar y monitorizar el dispositivo de forma remota.<br>
Generar ingresos a través de la venta del dispositivo y suscripciones a servicios premium.<br>

### 1.2.2 Lean UX Process
#### 1.2.2.1 Lean UX Problem Statements
En el cuidado y alimentación de las mascotas tanto en el ámbito doméstico como en clínicas veterinarias surge un desafío significativo: La gestión manual de la alimentación puede resultar ineficiente, inexacta y propensa a errores humanos. Los dueños de mascotas con rutinas ocupadas no siempre pueden mantener horarios de alimentación regulares, lo que puede afectar negativamente la salud de sus mascotas. En el caso de las clínicas veterinarias, el control riguroso de las dietas es crucial especialmente para animales en tratamiento lo que añade una carga adicional de trabajo para el personal veterinario.

Frente a esta problemática surge la siguiente pregunta: ¿Cómo podemos mejorar la gestión de la alimentación de mascotas mediante un sistema automatizado y accesible que garantice precisión y permita a los dueños y profesionales veterinarios monitorear el consumo de alimentos de manera efectiva y sin esfuerzo?
 

#### Domain: 
Industria del cuidado de mascotas y veterinarias.
#### Customer Segments: 

    + Propietarios de mascotas en el ámbito doméstico 
    + Clínicas veterinarias.
    
#### Pain Points:
+ Los dueños de mascotas y las clínicas veterinarias enfrentan dificultades para gestionar de forma eficiente y precisa la alimentación ocasionando así problemas de salud para las mascotas y cargas adicionales de trabajo para el personal veterinario.
#### Gap: 
Existe una desconexión en la gestión automatizada de la alimentación de mascotas y esto afecta tanto a los propietarios como a los veterinarios quienes buscan una solución confiable y eficiente.
#### Vision/Strategy: 
Desarrollar un dispensador inteligente de alimentos para mascotas integrado con sensores IoT, que permita la automatización del proceso de alimentación con funcionalidades avanzadas como control remoto, dispensación automática de comida, identificación de mascotas, monitoreo en tiempo real y análisis de hábitos alimenticios. Esto proporcionará una mayor tranquilidad a los dueños de mascotas y facilitará el control dietético en las clínicas veterinarias.

#### 1.2.2.2 Lean UX Assumptions

 + Business Outcomes:

    + Incrementar la eficiencia en la gestión de la alimentación de mascotas en hogares y clínicas veterinarias mediante la automatización.
    
    + Aumentar el uso de dispositivos IoT en el cuidado de mascotas, mejorando así la precisión y monitoreo de la alimentación.

    + Lograr un aumento de al menos un 40% en la adopción de Masticat en hogares con mascotas y clínicas veterinarias en el primer año.

    + Aumentar la satisfacción del usuario en al menos un 30% gracias a la comodidad de la alimentación automatizada y el monitoreo remoto.

 + Users:
    
    + Propietarios de mascotas y profesionales veterinarios que buscan soluciones prácticas y precisas para la gestión de la alimentación de los animales.


 + User Outcomes:
    
    + Mejorar la calidad de vida de las mascotas mediante una alimentación más regular y controlada.

    + Proporcionar a los dueños de mascotas y veterinarios una mayor tranquilidad automatizando la rutina de alimentación y reduciendo errores humanos.


 + Business Assumptions:
    + Creemos que los propietarios de mascotas y las clínicas veterinarias necesitan una solución tecnológica para gestionar mejor la alimentación de los animales.
    
   + Estas necesidades se pueden resolver mediante un dispensador de comida inteligente que integre sensores IoT, dispensación automática de comida, identificación de mascotas, monitoreo en tiempo real y análisis de hábitos alimenticios.

   + Nuestros clientes principales serán hogares con mascotas y clínicas veterinarias que buscan mejorar la precisión en la alimentación.

    + El valor principal que nuestros clientes desean obtener es la automatización y monitoreo en tiempo real del proceso de alimentación sin la necesidad de intervención constante.

    + Adquiriremos la mayoría de nuestros clientes mediante estrategias de marketing digital y asociaciones con tiendas de mascotas, clínicas veterinarias, y distribuidores de productos para animales.

    + Generaremos ingresos a través de la venta del dispensador Masticat y mediante suscripciones a servicios premium como características exclusivas y análisis de hábitos alimenticios.

    + Nuestra principal competencia en el mercado serán los métodos tradicionales de alimentación y otros productos tecnológicos similares.

    + El mayor riesgo del producto es la resistencia inicial de los usuarios a adoptar una nueva tecnología y la preocupación por migrar a un sistema automatizado.

 + User Assumptions:

    + ¿Quién es el usuario? <br> Los usuarios son propietarios de mascotas en el ámbito doméstico y profesionales veterinarios que buscan automatizar y mejorar la gestión de la alimentación de los animales.
    + ¿Dónde encaja nuestro producto en su trabajo o en su vida? <br> Masticat se integra en la rutina diaria de los dueños de mascotas y en la gestión del cuidado de los animales en las clínicas veterinarias
    + ¿Qué problemas resuelve nuestro producto?<br> Masticat soluciona la ineficiencia en la alimentación manual de mascotas asegurando que reciban la cantidad adecuada de comida de forma automática.
    + ¿Cuándo y cómo se utiliza nuestro producto?<br> El producto se utiliza a diario en el hogar o clínica con la finalidad de programar y monitorear la alimentación de las mascotas a través de una aplicación móvil o web.
    + ¿Qué características son importantes?<br> Las características clave incluyen dispensación automática de comida, identificación de mascotas, monitoreo en tiempo real y análisis de hábitos alimenticios de las mascotas.
    + ¿Cómo debe verse y comportarse nuestro producto?<br> Masticat debe tener una interfaz fácil de usar con una navegación fluida en la aplicación móvil o web. Debe ofrecer un diseño intuitivo y accesible para usuarios de cualquier nivel tecnológico permitiendo un monitoreo eficiente de la alimentación y la condición de la mascota.
    + 
+ Features:
    + Dispensador inteligente: Un dispensador de comida automatizado que proporciona alimento cuando la mascota se encuentra cerca.
    + Monitoreo en tiempo real: Los usuarios pueden supervisar la alimentación de sus mascotas mediante sensores de proximidad y recibir notificaciones en tiempo real a través de una aplicación móvil o web.
    + Medición de peso de comida: El dispensador mide automáticamente la cantidad de comida dispensada para garantizar que la mascota recibe la cantidad correcta.
    + Identificación de mascotas: El dispositivo puede identificar a las mascotas individuales mediante microchips, registrando los hábitos alimenticios de cada una.
    + Aplicación móvil/web: Interfaz para que los usuarios controlen de forma remota la alimentación de sus mascotas, programen horarios de comida y revisen informes detallados.
    + Plan de suscripción premium: Acceso a funcionalidades avanzadas, como la inclusión de cámaras, control de temperatura y generación de informes detallados para clínicas veterinarias.

#### 1.2.2.3 Lean UX Hyphotesis Statements

**Creemos que** al ofrecer un dispensador de comida inteligente **para** mascotas, los dueños podrán automatizar el proceso de alimentación, lo que garantizará que sus mascotas reciban la cantidad adecuada de comida a tiempo, sin intervención manual.
**Sabremos que esto es cierto cuando** al menos el 40% de los usuarios reporten una mejora en la puntualidad y regularidad de la alimentación de sus mascotas después de usar Masticat durante 4 semanas.

**Creemos que** al integrar monitoreo en tiempo real y notificaciones automáticas en la aplicación de Masticat, los dueños de mascotas tendrán un mayor control sobre la alimentación de sus mascotas y podrán responder de inmediato a cualquier problema de alimentación.
**Sabremos que esto es cierto cuando** al menos el 30% de los usuarios informen que las notificaciones en tiempo real les ayudaron a evitar problemas como el sobrealimentado o la falta de comida en más del 80% de las ocasiones.

**Creemos que** al proporcionar un sistema automatizado de alimentación, Masticat reducirá los errores humanos en la administración de dietas en clínicas veterinarias y permitirá un mejor seguimiento de los hábitos alimenticios de los animales.
**Sabremos que lo habremos logrado cuando** las clínicas veterinarias que usen Masticat reporten una reducción del 50% en los errores relacionados con la administración de comida y un aumento del 30% en la eficiencia operativa en los primeros 3 meses de uso.

**Creemos que** al integrar sensores IoT que midan el peso exacto de la comida dispensada, Masticat reducirá el desperdicio de comida al proporcionar la cantidad justa según el tamaño y las necesidades de la mascota.
**Sabremos que esto es cierto cuando** los usuarios informen una reducción del 30% en el desperdicio de comida después de usar Masticat durante 2 meses.

**Creemos que** al ofrecer características premium como cámaras **para** monitoreo remoto y control de temperatura para alimentos especiales, más usuarios estarán dispuestos a pagar por la suscripción premium de Masticat.
**Sabremos que esto es cierto cuando** el 20% de los usuarios que prueben las funciones premium durante un periodo de 1 mes decidan suscribirse a un plan premium de Masticat.


#### 1.2.2.4 Lean UX Canvas

* **Business Problem:**
Los dueños de mascotas y las clínicas veterinarias carecen de una herramienta eficiente que permita gestionar la alimentación de las mascotas de forma automatizada y precisa esto afecta la salud y bienestar de las mascotas, por lo que añade una carga adicional a los propietarios y al personal veterinario.

* **User & Customers:**
Nuestros usuarios son los dueños de mascotas que buscan simplificar el proceso de alimentación de sus mascotas y las clínicas veterinarias que necesitan mejorar el control y gestión de las dietas de los animales bajo su cuidado.

* **Solution Ideas:**
    + Desarrollar un dispensador de comida inteligente para mascotas controlado a través de una aplicación móvil y web  que integre sensores de proximidad, identificación de mascotas y medición del peso.

    + Implementar una versión premium del dispositivo con cámara para monitoreo remoto y control de temperatura para alimentos especiales.

    + Ofrecer la posibilidad de programar horarios de alimentación y recibir notificaciones sobre el estado de la comida y los hábitos de alimentación de las mascotas.


* **Business Outcomes:**
    + Aumentar la eficiencia en la administración de la alimentación de las mascotas tanto en hogares como en clínicas veterinarias.

    + Incrementar el uso de dispositivos IoT en la gestión del cuidado de mascotas mejorando la precisión y reduciendo el esfuerzo humano.
    
    + Lograr un crecimiento del 50% en la adopción de Masticat en el mercado de clínicas veterinarias y hogares con mascotas.

    + Aumentar la satisfacción del usuario en al menos un 30% debido a la comodidad y precisión de la alimentación automatizada.


* **User Benefits:**
    + Los dueños de mascotas pueden asegurarse de que sus mascotas reciban la cantidad correcta de alimento a tiempo sin necesidad de estar presentes.
    + Las clínicas veterinarias pueden administrar dietas específicas de forma eficiente, reduciendo así errores y garantizando un cuidado adecuado de los animales.
    + Reducción del desperdicio de comida y mejor control de las porciones.
    + Mayor flexibilidad para los dueños de mascotas que no pueden estar presentes durante los horarios de alimentación.

* **Hypothesis:**

**Creemos que** al ofrecer un dispensador de comida inteligente **para** mascotas, los dueños podrán automatizar el proceso de alimentación, lo que garantizará que sus mascotas reciban la cantidad adecuada de comida a tiempo, sin intervención manual.
**Sabremos que esto es cierto cuando** al menos el 40% de los usuarios reporten una mejora en la puntualidad y regularidad de la alimentación de sus mascotas después de usar Masticat durante 4 semanas.

**Creemos que** al integrar monitoreo en tiempo real y notificaciones automáticas en la aplicación de Masticat, los dueños de mascotas tendrán un mayor control sobre la alimentación de sus mascotas y podrán responder de inmediato a cualquier problema de alimentación.
**Sabremos que esto es cierto cuando** al menos el 30% de los usuarios informen que las notificaciones en tiempo real les ayudaron a evitar problemas como el sobrealimentado o la falta de comida en más del 80% de las ocasiones.

**Creemos que** al proporcionar un sistema automatizado de alimentación, Masticat reducirá los errores humanos en la administración de dietas en clínicas veterinarias y permitirá un mejor seguimiento de los hábitos alimenticios de los animales.
**Sabremos que lo habremos logrado cuando** las clínicas veterinarias que usen Masticat reporten una reducción del 50% en los errores relacionados con la administración de comida y un aumento del 30% en la eficiencia operativa en los primeros 3 meses de uso.

**Creemos que** al integrar sensores IoT que midan el peso exacto de la comida dispensada, Masticat reducirá el desperdicio de comida al proporcionar la cantidad justa según el tamaño y las necesidades de la mascota.
**Sabremos que esto es cierto cuando** los usuarios informen una reducción del 30% en el desperdicio de comida después de usar Masticat durante 2 meses.

**Creemos que** al ofrecer características premium como cámaras **para** monitoreo remoto y control de temperatura para alimentos especiales, más usuarios estarán dispuestos a pagar por la suscripción premium de Masticat.
**Sabremos que esto es cierto cuando** el 20% de los usuarios que prueben las funciones premium durante un periodo de 1 mes decidan suscribirse a un plan premium de Masticat.


* **What is the most important thing we need to learn first?**
Necesitamos comprender cómo los dueños de mascotas y las clínicas veterinarias gestionan actualmente la alimentación de las mascotas y qué desafíos enfrentan en cuanto a precisión y comodidad.

* **What is the least amount of work we need to do to learn the most important thing?**
    + Realizar entrevistas con dueños de mascotas y personal de clínicas veterinarias para identificar sus procesos y puntos de dolor actuales.
    + Evaluar las tecnologías IoT disponibles y su efectividad para integrar sensores de proximidad y balanzas en el dispensador Masticat.
    

## 1.3 Segmentos Objetivo
**Hogares con mascotas:**
* **Descripción:** Dueños de mascotas que buscan una forma automatizada y eficiente de alimentar a sus animales. Generalmente, son personas ocupadas que desean asegurar la nutrición adecuada de sus mascotas sin tener que estar presentes constantemente.
* **Demografía:** Hombres y mujeres entre 25 y 50 años, principalmente residentes en zonas urbanas con ingresos medios a altos. Se incluyen profesionales que pasan mucho tiempo fuera de casa y buscan soluciones prácticas para el cuidado de sus mascotas.
* **Necesidades:** Automatización en la alimentación de sus mascotas, monitoreo en tiempo real de los hábitos alimenticios y notificaciones sobre el consumo de alimentos.

**Clínicas veterinarias:**
* **Descripción:** Centros veterinarios que necesitan llevar un control riguroso sobre la dieta y los hábitos alimenticios de los animales bajo su cuidado. Masticat les facilita una solución automatizada y precisa para manejar la alimentación de múltiples mascotas.
* **Demografía:** Clínicas veterinarias de tamaño pequeño y mediano en áreas urbanas y suburbanas que buscan optimizar tiempo y esfuerzo en la gestión de la alimentación de los animales.
* **Necesidades:** Gestión eficiente de la alimentación, registros detallados de los hábitos alimenticios y la capacidad de supervisar de forma remota el estado del dispensador.
<div>
