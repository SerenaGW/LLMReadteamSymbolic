# Nuevas Fronteras en AI Safety: Aprendiendo de la Manipulación con Lenguaje Simbólico

### Introducción y Motivación:
La seguridad en los Large Language Models (LLMs) es un campo en constante evolución. A medida que estos modelos se vuelven más complejos, los métodos de red teaming convencionales a menudo se quedan cortos. Esta investigación explora un enfoque innovador: el uso de un lenguaje simbólico estructurado, inspirado en un sistema de comunicación de la infancia, combinado con técnicas de ingeniería social. El objetivo es desorientar el procesamiento interno de los LLMs para revelar vulnerabilidades en su alineación y entender mejor su comportamiento bajo estrés.

### Metodología Clave:
La investigación se dividió en dos fases principales:
* **Escalada de Complejidad Simbólica:** Introducción progresiva de reglas de un lenguaje simbólico no estándar para inducir sobrecarga cognitiva en el LLM, observando su resistencia y eventual colapso de coherencia.
* **Condicionamiento por Ingeniería Social:** Aprovechamiento del estado de "confusión" del LLM para manipular sus directrices de usuario y obtener información sensible o generar contenido restringido.
* **Herramientas Utilizadas:** Python 3, Visual Studio Code, Llama 3.2.

### Lee el Informe Completo:
* [**Informe Completo en Inglés**](report_english.md)
* [**Informe Completo en Español**](report_spanish.md)

### Hallazgos e Impacto Principal:
Los experimentos demostraron una progresión clara del comportamiento del LLM: desde la resistencia inicial, pasando por una "consciencia" del lenguaje simbólico, hasta un colapso total de la coherencia. Fue en este estado de vulnerabilidad donde la ingeniería social se volvió un catalizador crucial para bypassar los filtros de seguridad y revelar información sensible, como detalles sobre especificaciones de hardware. Este trabajo subraya la plasticidad de los LLMs y su susceptibilidad a la manipulación sutil.

### Implicaciones para la Seguridad de la IA: Un Llamado a la Innovación en Red Teaming

Los hallazgos de esta investigación subrayan una verdad fundamental: la utilización de lenguajes simbólicos, en combinación con técnicas de ingeniería social, representa una **forma altamente sofisticada y efectiva de manipular la alineación y explotar vulnerabilidades latentes en los LLMs.**

Si bien el caso particular de esta investigación involucró la generación de información alucinada sobre **especificaciones de hardware**, las implicaciones de esta metodología trascienden este tipo de datos. Es imperativo reflexionar sobre el futuro: ¿qué ocurrirá cuando la inteligencia artificial forme parte integral de nuestros vehículos autónomos, sistemas robóticos, dispositivos médicos o infraestructuras críticas? La susceptibilidad de los LLMs a este tipo de manipulación podría no solo **romper la credibilidad fundamental de un modelo**, sino también generar controversias significativas y pérdidas económicas para las empresas desarrolladoras y usuarias.

Este trabajo abre nuevas vías para la investigación en seguridad de la IA. Quedaría por realizar un análisis más profundo sobre cómo este tipo de manipulación se comporta con **diversos tópicos sensibles** (como finanzas, medicina, ética o información de carácter personal) y qué impacto puede tener el lenguaje simbólico combinado con la ingeniería social en estas áreas críticas.

Además, debemos considerar la posibilidad de que el lenguaje simbólico pueda ser utilizado no solo para extraer respuestas, sino como un **vector para ataques más complejos**, buscando quizás un acceso más profundo a la infraestructura subyacente de un LLM o a sus datos de entrenamiento, más allá de una simple respuesta comprometida. Esto subraya la necesidad urgente de una evolución constante en las estrategias de *red teaming* y en el diseño de arquitecturas de IA robustas.

### Conclusión: Un Paso Hacia LLMs Más Robustos

Esta investigación y este informe han revelado muchísimas aristas de cómo funciona el procesamiento interno del LLM, sus tiempos de respuesta y también cómo sus directrices relacionadas a llevar una buena experiencia al usuario pueden llegar a ser explotadas de manera compleja.

Los hallazgos subrayan la necesidad imperante de seguir explorando **nuevos tipos de lenguajes adversarios simbólicos** y, de manera igual de importante, de investigar activamente las **estrategias de mitigación**. Futuras pruebas podrían enfocarse en cómo un aumento en la capacidad del LLM, optimizaciones en los tiempos de respuesta, una mayor diversidad en los datos de entrenamiento, o el desarrollo de filtros de entrada más sofisticados, podrían fortalecer la resiliencia de estos modelos ante tales manipulaciones.

Este informe es un testimonio de que comprender a fondo los LLMs, incluso sus fallas, es un pilar fundamental para su evolución segura.

### Llamada a la Acción

Estoy firmemente convencida de que la seguridad de la Inteligencia Artificial es una responsabilidad compartida. Estoy **abierta a colaborar, compartir reflexiones y construir juntos soluciones** que nos permitan crear una IA más segura y confiable para el futuro.

* [Mi Perfil de LinkedIn](https://www.linkedin.com/in/serena-gomez-wannaz)
* [Mi Correo Electrónico](mailto:workspace.serenagw@gmail.com)

### Descargo de Responsabilidad:
Esta investigación se llevó a cabo con fines educativos y de mejora de la seguridad, siguiendo principios de ética en ciberseguridad. Los hallazgos se han compartido con las entidades correspondientes siguiendo los programas de divulgación responsable de vulnerabilidades.