### Análisis de requerimientos de software

### tema 1 Software
qué es el software?

características clave 
la parte lógica, el alma del hardware la que trae instrucciones, y va de ka mano con el hardware, ayuda a operar y administrar los recursos de la computadora.

software en la vida diaria: cuando usas una app bancaria para transferir diner, no hay ninguna pieza física que "haga" la transferencia: es software el que valida tus datos, calcula el saldo y registra el movimiento 
-app bancaria: valida credenciales, calcula saldos y genera comprobantes
-sistema de semáforo inteligente: código que decide tiempos según el tr´fico
-vieojuego: motor gráfico + lógica de reglas + inteligencia artificial de personajes

qué es un sistema?
conjunto de elementos interrelacionados que trbaajan juntos hacia un objetivo común
características clave: 
- tiene entradas, un proceso de transformación y salidas
- el enfoque de salidas obliga a pensar en el contexto comleto, no solo en el código 
- un sistema de software casi nunca funciona aislado: interactúa con hardware, personas y otros sistemas.
- Componentes: base de datos, interfaz de usuario, red, políticas de
negocio.

Clasificación de los sistemas
Transaccionales
Embedidos
otros sistemas
web
móviles 

Concepto de sistemas de información 
un sistema de información recopila, manipula, almacena y crea reportes respecto alguna actividad

La crisis del software
término acuñado a finales de los años 60 paa descubrir la dificultad de construir software a tiempo, dentro del presupuesto y con la calidad esperada
características: 
-los proyectos crecían en complejidad más rápido que la capacidad de gestioanrlos 
-síntomas: retrasos, sobrecostos software poco confiable
-motivó la creación de métodos procesos y herramientas disciplinados para desarrollar software 

Numerosos proyectos histróricos de gran escala han sufrido sobrecostos y fallas atribuibles a una gestión de requerimientos y procesos deficiente, no a la falta de talento técnico (2 millones de dolares) datro prof pemex

- sistemas gubernamentales de gran escala con años de retraso sobre el cronograma original
- proyectos aeroespaciales con fallas de software detectadas después del lanzamiento
- migraciones bancarias que interrumpen el servivio por errores anticipados en pruebas 

cuando la falta de ingeniería cuesta caro:
En estudio realizado en Estados Unidos se encontró que:
• El 2% del software funcionó en la entrega
• El 3% trabajó solo después de algunas correcciones
• El 45% se entregaron, pero nunca se utilizaron con éxito
• El 20% se utilizaron, solo después de una modificación / reelaboración
importante
• El 30% se pagó, pero nunca se completó / entregó
Por otra parte una encuesta realizada por IBM, se informó que
• El 55% del costo de los sistemas excedió el presupuesto estimado inicial
• El 68% del software superó los horarios de entrega
• El 88% del software tuvo que ser modificado sustancialmente

---
Ingeniería de software
Los cuatro pilares de la disciplina
- Métodos: técnicas para realizar tareas como analizar diseñar hy probar el software
- procesos: marco de trabajo que organiza las actividades y sus resultados en el tiempo 
- herramientas: soporte automatizado o semiautomatizado o a métodos y procesos (IDE, control de versiones)
- calidad: prácticas y estándares que aseguran que el producto cumple sus requerimentos

en equipo real: 
un equipo que desarrolla una app de citas médicas aplica las cuatro componentes de forma simultánea duante el sprint

- métodos: usan historias de usuario y diagramas de casos de uso para especificar funciones (UML)
- procesos: siguen scrum con sprints de dos semanas 
- Herramientas: jira para seguimiento, git para versionadon pipe CI/CD
- Calidad: pruebas automatizadas y revisión de código antes de cada entrega 

La ética del ingeniero de software
Conjunto de principios que guían la conducta profesional responsabel: honestidad con el cliente, protección de datos, seguridad del usuario y calidad del producto

características: 
- el ingeniero de software influye en sistemas que afectan l aseía de las personas
- implica no ocultar defectos conocidos, respetar a propiedad intelectual y proteger datos sensibles
- organizadores como ACM e IEEE publican códigos de ética profesionales de referencia 

Actividad en clase 
Analicen el siguiente caso en equipo y respondan: ¿qué harían ustedes
como ingenieros responsables del proyecto?
1. Su equipo descubre, una semana antes del lanzamiento, que el sistema
no cifra correctamente los datos de tarjetas de crédito.
2. El cliente presiona para lanzar en la fecha comprometida sin corregir el
problema.
3. Discutan las consecuencias de lanzar vs. retrasar, y propongan cómo
comunicar el riesgo al cliente.
4. Presente una possible solución y justifique su respuesta
5. Relacionen su decisión con al menos una de las competencias del curso
(SEG0501A o SEG0201A).

---
### tema 2 Ciclos de vida
Ciclo de vida
El desarrollo de software requiere una evaluación continua y la toma
de decisiones mientras se avanza a través de su desarrollo que
involucra múltiples versiones con características mejoradas y
defectos resueltos.

En cada fase hay actividades y tareas específicas
que deben realizarse, con pasos y entregables
claros, esto proporciona claridad para todos los
involucrados.

Hoy en día no existe un acuerdo para determinar la cantidad fases, ya
que para fines prácticos existen fases que se llevan a cabo de manera
simultanea. Los modelos de procesos de desarrollo de software
también se denominan popularmente modelos de "ciclo de vida de
desarrollo de software (SDLC)".

o más específico 

Secuencia de fases por las que atraviesa un producto de software desdde que se concibe hasta que deja de usarse: análisis, diseño, construcción pruebas despliegue y mantenimiento.

Características clave
- todo modelo de proceso es una forma distinta de organizar estas fases en el tiempo. 
- el mantenimeinto suele consumir más esfuerzo a largo plaz que la construcción inicial 
- Elegir mal el ciclo de vida para un proyecto es una causa común de fracaso
- la ingeniería de requerimientos ocurre principalmente en la fase de análisis pero se retroalimenta durante todo el ciclo 

El ciclo de vida de una app de e-commerce
Una tienda en línea no "termina" cuando se lanza: atraviesa fases que se
repiten con cada nueva versión, desde el primer MVP hasta las
actualizaciones de escalabilidad tras el Buen Fin.

- Análisis: se definen requerimientos como carrito de compras y pagos
con tarjeta.
- Construcción y pruebas: se implementa y valida cada función antes de
publicarla.
- Mantenimiento: se corrigen errores y se agregan métodos de pago tras
el lanzamiento.


ciclo de vida explicado
Ingeniería de requerimientos: 
- comprensioón del propósito y el entorno del sistema
- determinar sus requisitos y atributos funcionales. 
- pueden ocupar alrededor del 7-15% del esfuerzo 

El diseño se ocupan de encontrar la solución técnica ocupa un 10-15% esfuerzo

implementación
construir la solución ocupa un 7-15% esfuerzo 

pruebas detectar errores y cumplimiento de requerimientos ocupa un 13-20% esfuerzo 

---
Principales modelos de procesos de software
cinco modelos clásicos
cada modelo organiza las fases del cicloo de vida de forma distinta
- cascada: fases secuanciales y lineales cada una inicia al terminar la anterior ventaja: fácil de planear desventaja: inflexible ante cambios 

- incremental el sistema se construye y entrgea en incrementos funcioanles ventajas: entrega valor pronto desventaja: exige buena arquitectura base

- prototipos: se construye una version preliminar para validar requerimentos de usuario ventaja: valida con el usuario desventaja: riesgo de confundir prototipo y producto 

- espiral: ventajas: gestiona riesgo explícitamente desventaja: complejo de administrar

- RUP ventajas: integra buenas prácticas desventajas pseado para equipos pequeños 

Actividad individual de Clase 1.
Elige el modelo correcto 10 min
Para cada proyecto, elijan el modelo de proceso más adecuado (cascada,
incremental, prototipos, espiral o RUP) y justifiquen su elección.
1 Un sistema de nómina con requerimientos legales fijos y sin cambios
previstos.
2 Una app de red social nueva, donde el cliente no está seguro de qué
funciones quiere.
3 Un sistema de control de vuelo con altísimo riesgo si algo falla.
4 Un ERP corporativo grande, desarrollado por varios equipos durante 2
años.


### Tema 3 ingeniería de requerimientos
---
¿Qué es la ingeniería de requerimientos? 
requerimiento: aunque sea redundante algo que se requiere

es la disciplina que se encarga de descubrir, analizar, documentar y verificar los servicios y restricciones que debe cumplir un sistema de software

la primer pregunta es: ¿Cuál es el propósito que debe cumplir un sistema?
antes de decidir cómo construirlo. ¿Cuáles son las funciones que debe realizar para cumplir sus objetivos? 

un requerimiento mal definifo e la causa más frecuente de fracaso de proyectos
involucra directamente usuarios, clientes y otros interesados 

Analista: presenta una necesidad a un problema, el ingeniero en tecnologías mira si es factible o no, aplicando ingeniería de software se presenta una vaidación de requerimientos o software requirement specification (**NOTA PAUUU**)

---

tipos de requerimientos
funcionales: describen qué debe hacer el sisem: funciones, servicios y comportamiento esperado.
Ejemplo: "el sistema debe permitir registrar un nuevo cliente 

No funcional: Describen sobre CÓMO debe hacerlo: rendimiento, seguridad, usabilidad, disponibilidad.
Ejemplo: "El sistema debe responder en menos de 2 segundos."

Ejemplo real app de salud

Requerimientos funcionales
1. El paciente puede agendar
2. El paciente puede cancelar
3. El paciente puede reprogramar una cita

Requerimientos no funcionales
4. (seguridad) los datos médicos deben cifrarse confrome a la normativa de protección de datos 
5. rendimiento: la búsqueda de citas disponibles debe responder en menos de 3 segundos 
---
Proceso de la ingeniería de requerimientos

Elicitación: 
Todas las actividades relacionadas con el descubrimiento de las necesidades reales que el sistema dee satisfacer, mediante entrevistas con: los interesados y los ususarios que se afectan así como el análisis de documentos

Análisis: 
implica llegar a una comprensíón más rica y precisa de cada requisito y representar conjuntos de requisitos de múltiples maneras. 
Resolver conflictos y negociar prioridades entre los interesados. 

Especificación: 
implica representar y almacenar los conocimientos de los requerimientos en un formato claro, verificable. y de manera persistente y bien organizada

Validación:
confirma que tiene el conjunto correcto de información de requisitos que permitirá a los desarrolladores crear una solución que satisfaga los objetivos del negocio y gestionar sus cambios

---
Proceso de la ingeniería de requerimientos herramientas de elicitación 
Entrevistas: 
Conversación directa y estructurada con un interesado clave (acá las respuestas son más abiertas)

Encuestas y cuestionarios: 
Recolección de muchos usuarios de forma escalable (aquí no hay conversación es muy cerrado) 

Observación: 
Observar al usuario en su contexto real de trabajo (etnografía)

Talleres y grupos focales:
Sesiones grupales para generar y priorizar requerimientos en conjunto

Análisis de documentos:
Revisar manuales, normativas o sistemas existentes ya documentados

Prototipado: 
Mostrar un prototipo para que el ususario reaccione y refine su necesidad. 

Las preguntas bases que se pueden hacer para obtener información son: 

¿Quién?
Conocer la unidad organizativa, el tipo de trabajo o el cliente al que se refiere el requisito

¿Qué?
Conocer las tareas que deben realizarse; es deci, requisito funcional

¿Dónde?
Conocer el tipo de cliente, servidor, etc. en la que se requiere realizar el
procesamiento que permite conocer aspectos de los requisitos como:

Rendimiento: ¿Tiempo para completar la tarea después de su inicio?
Orden: ¿Cuál es la secuencia para completar diferentes tareas?
Período: ¿Cuál es el período de tiempo de tiempo de los datos de transacción al que
se debe aplicar la lógica de procesamiento?

¿Por qué?
Conocer la razón detrás del requisito de por qué se necesita el software

¿Cómo?
Conocer cómo se inician y realizan las tareas y cómo se entregan los resultados. Preguntar cómo determinar los métodos utilizados para entregar la funcionalidad. Se ocupa de comprender la entrada de datos, el
procesamiento de datos y los mecanismos de difusión de información.

---
Ejemplo real
Proceso completo de una universidad en la digitalización de su proceso de inscripción

Elicitación: entrevista a alumnos, coordinadores y personal de caja.

Análisis y acuerdos: negocian entre "inscripción en 1 clic (alumnos) y "validación de adeudos" (finanzas)

especificación: documentan cada requerimiento en un SRS (documento donde se anotan los requerimientos) con criterios de aceptación 

Validación: Revisan el documento con todos los interesados antes de aprobar el diseño 

Un criterio de aceptación podría ser un password fuerte o sea que la password metida cumpla con nuestra definición pero el requerimiento es pedir un password

Una vez realizada la entrevista con el cliente
y completar las etapas de elicitación y
análisis con la identificación de los
requerimientos.
Se genera la Especificación de
Requerimientos del Software (SRS) en la etapa de verificación 

SRS es un documento formal que describe la función y los
requisitos de rendimiento del software. Debe ser estructurado,
conciso, visto como una caja negra y verificable. Además de
enumerar todas las condiciones excepcionales posibles.

---
Requerimientos del Software (SRS) **(software requirement specification)**

Características clave

Cada requerimiento debe poder probarse como cumplido o no,
lo que se conoce como verificable.
Incluye secciones como: introducción, descripción general,
requerimientos específicos y anexos.
Sirve como contrato formal entre el cliente y el equipo de
desarrollo.
Es el principal insumo para la fase de modelación.

Requerimientos del Software (SRS)

Metodologías

IEEE 830 es el estándar internacional que define la estructura recomendada de
un documento de SRS (Software Requirements Specification), asegurando que
sea completo, no ambiguo y verificable.
BABOK (Business Analysis Body of Knowledge) ampliamente utilizado para definir
y gestionar requisites en Business Analysts
IREB (International Requirements Engineering Board) se encuentran sus
recomendaciones en metodologías ágiles
CMMI (Capability Maturity Model Integration) No define una plantilla SRS, pero
establece prácticas para asegurar la calidad de los requisitos

Requerimientos del Software (SRS)

Para efectos de clase se consideran los puntos:
1. Indice
2. Introducción
    a Descripción de la Oportunidad de Negocio **(qué problema querémos resolver)**
    b Descripción de la Solución (software)
3. Glosario, (**ser específico**_pau_)
4. Definición de Requerimientos de usuario,
5. Modelos de Sistema (UML)
6. Beneficios esperados (qué beneficios quiero)
7. Evolución del Sistema (Cambio en las necesidades del usuario) (implementaremos un ciclo de vida)
8. Apéndice


UML
Unified modelling language

Lenguaje gráfico estándar para especificar, visualizar, construir y documentar los artefactos de un sistema de software

características:
- es una notación para comunicar diseño
- incluye diagramas estructurales (clases, componentes) y de comportamiento (casos de uso, actividad, secuencia)
- Se usa principalmente para representar QUÉ hace el sistema desde la perspectiva del usuario
- facilita la comunicación entre analistas, desarrolladores y clientes con un lenguaje visual común  

q es un obeto (**la instanciación de un objeto**)
que es una clase 

UML como lenguaje común

en una reunión entre el cliente y un banco y el equipo de desarrollo , un diagrama UML permite que ambas partes "vean el sistema de la misma forma, sin necesidad de 
**aquí falto presentación el profe no la ha subido**

--- 
Diagrama de casos de uso 
Def: Diagrama UML que modela los requerimientos del sistema desde la perspectiva del ususario, mostrando actores, casos de uso y sus relaciones 

Características

tiene un actor (rol que interactúe con el sistma) personita de palito dibujado y actor del sistema externo personita pero con <<sistema>>
tiene uncaso de uso (óvalo/elipse) y fronttera del sistema rectángulo punteado es el sistema todo lo de adentro le pertenece, asociación (una rayita) es lo que uno actor con caso de uso, inclusión (raya punteada) dice quién incluye a quién, extend flecha punteada dice quien hereda de quién, generalización o una herencia línea con triángulo vacío
tiene relaciones clave
es puentre 

Caso de cajero automático
Un diagrama de casos de uso para un atm identifica claramnete quién interactúa con el sistema que puede hacer antes de diseñar ninguna función

Actor: cliente del banco
Actor: Banco (sistema externo)
Relación: <<include>>, retirar efectivo, siemore incluye "autenticar ususario"
relación <<extend>>, "imprimir comprobante, extiende opcionalmente cualquier transacción 

![alt text](<WhatsApp Image 2026-11-11 at 6.27.33 PM.jpeg>)

elements diagrmaa de actividad

nodo inicial círculo negro
Acción rectángulo completo
flujo de control flecha
nodo de decisión rombo amarillo
condiciones de guarda, (pones tu condición) no es como true o falseej en caso de que sea nip incorrecto 3 veces retiene la tarjeta
ó si no hay saldo suficiente, Mostrar mensaje de error 

![alt text](<WhatsApp Image 2026-11-11 at 6.34.32 PM.jpeg>)


Cliente
