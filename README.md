\# Infografía Interactiva: Dinámica y Táctica del Balonmano

\!\[HTML5\](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)  
\!\[CSS3\](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge\&logo=css3\&logoColor=white)  
\!\[JavaScript\](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)  
\!\[Bootstrap\](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)  
\!\[PWA\](https://img.shields.io/badge/PWA-5A0FC8?style=for-the-badge\&logo=pwa\&logoColor=white)

Aplicación web progresiva (PWA) educativa de una sola página, diseñada para explicar los fundamentos tácticos, reglas y dinámicas del balonmano. Dirigida a un público adulto (30-50 años) con un enfoque de aprendizaje autónomo, profundo y no lineal.

\---

\#\# Arquitectura y Estructura

El proyecto está contenido en su totalidad en un \*\*único archivo \`index.html\`\*\*, cumpliendo con el requisito de distribución cero. La arquitectura interna separa lógicamente los datos, la presentación y el comportamiento:

1\. \*\*Capa de Datos (\`appData\`):\*\* Un objeto JSON simulado en JavaScript que centraliza todo el contenido textual, preguntas del test y configuración de los módulos. Esto permite mantenimiento y escalabilidad sin tocar la estructura del DOM.  
2\. \*\*Capa de Vista (Renderizado dinámico):\*\* Funciones \`render\[Nombre\]()\` que leen \`appData\` e inyectan el HTML resultante en los contenedores correspondientes.  
3\. \*\*Capa de Estilos (\`\<style\>\`):\*\* Variables CSS para la tokenización completa del sistema de diseño (Dark Mode y Alto Contraste), layout basado en CSS Grid y Flexbox.  
4\. \*\*Capa Lógica (\`\<script\>\`):\*\* Controladores de interacción, Canvas API para el fondo de partículas, lógica del quiz y ejecutores de PWA.

\#\# Tecnologías Utilizadas

\- \*\*HTML5 Semántico:\*\* Uso de \`\<main\>\`, \`\<section\>\`, \`\<nav\>\`, \`\<footer\>\`, atributos ARIA y roles para accesibilidad.  
\- \*\*CSS3 Avanzado:\*\*   
  \- Custom Properties (Variables CSS) para temas (Dark / High Contrast).  
  \- Grid y Flexbox para el sistema Bento UI y la responsividad.  
  \- Efectos \`backdrop-filter\` (Glassmorphism), gradientes y sombras.  
\- \*\*JavaScript Vanilla (ES6+):\*\*  
  \- Manipulación del DOM.  
  \- Canvas API (Fondo de constelación interconectada).  
  \- IntersectionObserver (Animaciones de revelado al scroll).  
  \- Blob API (Generación de Service Worker y Manifest en vuelo).  
\- \*\*Bootstrap 5.3.3:\*\* Sistema de grid responsivo para la barra de navegación y componentes de acordeón para las tarjetas de posiciones.  
\- \*\*Dependencias CDN:\*\* Google Fonts (Chakra Petch, Outfit) y Bootstrap Icons.

\#\# Módulos de Contenido

La aplicación se divide en módulos renderizados dinámicamente:

1\. \*\*Hero y Mapa Conceptual:\*\* Presentación principal con estadísticas rápidas y un mapa SVG interactivo que conecta los módulos mediante líneas animadas.  
2\. \*\*Hub / Bento Grid:\*\* Panel de acceso rápido a las secciones, utilizando tarjetas con jerarquía visual y efectos \*hover\*.  
3\. \*\*La Cancha Interactiva:\*\* Diagrama vectorial (SVG) a escala de las dimensiones oficiales (40x20m), con zonas interactivas (6m, 7m, 9m) que despliegan \*tooltips\* tácticos.  
4\. \*\*Posiciones de Juego:\*\* Tarjetas para las 7 posiciones, integrando acordeones de Bootstrap para desglosar el rol ofensivo y defensivo.  
5\. \*\*Técnicas de Lanzamiento:\*\* Análisis funcional de la Suspensión, el Apoyo y la Cadera (Cuándo, Ventaja, Lectura táctica).  
6\. \*\*El Portero:\*\* Sección destacada con estética diferenciada (acentos ámbar) subrayando su rol como jugador clave.  
7\. \*\*Dinámica Táctica:\*\* Explicación de Cruce, Bloqueo, Transición, Circulación y Fijación.  
8\. \*\*Autoevaluación:\*\* Quiz de opción múltiple con retroalimentación inmediata, barra de progreso y sistema de puntuación.

\#\# Sistema de Diseño y UI/UX

\- \*\*Estética Premium:\*\* Inspirada en dashboards de \*Sports Analytics\*. Fondo grafito/nava profundo (\`\#060b18\`, \`\#0a1128\`).  
\- \*\*Acentos Controlados:\*\* Cian (\`\#00e5ff\`) para interactividad principal, Ámbar (\`\#f59e0b\`) para el portero y alertas, Verde Petróleo y Naranja para categorías secundarias.  
\- \*\*Tipografía:\*\* \*Chakra Petch\* para títulos (impacto tecnológico) y \*Outfit\* para cuerpo de texto (legibilidad óptima).  
\- \*\*Microinteracciones:\*\* Glow sutil en tarjetas, transiciones suaves, y nodo de partículas animado en el fondo.  
\- \*\*Alto Contraste:\*\* Toggle implementado que inyecta la clase \`.high-contrast\` sobrescribiendo las variables CSS raíz.

\#\# Características PWA

La aplicación es instalable y funciona sin red gracias a la inyección de recursos mediante la \*\*Blob API\*\*:

\- \*\*Manifest:\*\* Generado como un objeto JSON, convertido a \`Blob\` y enlazado dinámicamente en el \`\<head\>\`. Incluye iconos SVG codificados en Data URI.  
\- \*\*Service Worker:\*\* Registrado desde un Blob de texto en JavaScript. Implementa una estrategia \*Cache-first\* básica para permitir la ejecución \*offline\*.

\#\# Accesibilidad (a11y)

\- Enlace "Saltar al contenido" para lectores de pantalla.  
\- Atributos \`aria-label\` en botones, secciones e interacciones no estándar.  
\- Respeto estricto de la media query \`prefers-reduced-motion: reduce\` (desactiva partículas y transiciones).  
\- Navegación completa por teclado (estados \`focus-visible\`, interacciones por \`Enter\`/\`Space\`).  
\- Contraste de color verificado para legibilidad en modo oscuro.

\#\# Cómo ejecutar el proyecto

Al ser un archivo único y autónomo, no requiere servidores Node.js ni pasos de compilación.

1\. Descarga el archivo \`index.html\`.  
2\. Ábrelo directamente en cualquier navegador moderno (Chrome, Edge, Firefox, Safari).  
3\. Para probar las funcionalidades PWA (Instalación y Service Worker), sirve el archivo a través de un servidor local básico, por ejemplo:  
   \- Usando la extensión \*\*Live Server\*\* de VS Code.  
   \- O mediante Python: \`python \-m http.server 8000\`  
4\. Accede a \`localhost:8000\` (o el puerto configurado) para ver el icono de instalación de la PWA en la barra del navegador.  
