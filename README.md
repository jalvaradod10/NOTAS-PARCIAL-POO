# NOTAS-PARCIAL-POO
__Notación UML rápida (cheat-sheet, 1 línea cada uno)__

Breve cheat-sheet de notación que debes usar en el parcial:

Asociación simple (bidireccional): A -- B

Asociación unidireccional: A ---> B (flecha en B si A conoce a B)

Agregación (rombo abierto): A o-- B → A “contiene” B, B puede existir independiente.

Composición (rombo relleno): A ◆-- B → B no existe sin A (ciclo de vida ligado).

Herencia / generalización: Sub △-- Super (triángulo en Super).

Multiplicidad: 1, 0..1, 0..*, 1..*.

__7. ESTRATEGIA PASO A PASO PARA RESOLVER UN ENUNCIADO EN EL PARCIAL__

Subrayar: sustantivos → candidatos a clases; verbos → métodos; adjetivos/datos → atributos.

Eliminar ruido: si el enunciado menciona cosas irrelevantes, NO las modeles.

Agrupar: identificar si un sustantivo es atributo o clase (ej.: “dirección” puede ser atributo String o clase Address si tiene subcampos).

Decidir relaciones: por cada par, escribe “¿puede existir A sin B?” → responde composición/agregación/asociación.

Especificar multiplicidades (ser conservador: 0..* o 1..* cuando no estés seguro de exclusividad).

Añadir métodos solicitados y los necesarios para consultarlas (searchers).

Justificación corta de decisiones clave (por qué composición aquí, por qué many-to-many allá). Esto el profe lo pide.
__11. ERRORES COMUNES EN EXÁMENES Y TRUCOS DEL PROFESOR__

Multiplicidades inconsistentes: si pones 1 en ambos lados de una relación many-to-many, te lo saltan. Explica por qué pones 0..* o 1..*.

Confundir agregación con composición: justificar con “puede existir fuera” o “no puede existir fuera”.

Sobremodelar: crear clases por cada palabra del enunciado sin evaluar si es necesario.

Olvidar métodos pedidos en el enunciado (buscadores, agregadores). Siempre relee el enunciado.

No justificar decisiones clave: el profe quiere ver el razonamiento en pocos renglones.

Duplicar datos innecesarios: si guardas editorial en Libro y además haces lista de libros en Editorial, eso está bien si mantienes coherencia; en UML examinarán consistencia, no implementación.
Universidad del Norte
Departamento de Ingeniería de Sistemas y Computación
Programación Orientada a Objetos
__EJERCICIO UML 1__
Megaferias
La organización Megaferias está organizando la primera gran feria del libro en
Barranquilla. Para esto, les ha solicitado diseñar un sistema de información para
poder administrar el evento y sus participantes.
El sistema está enfocado principalmente en la administración de los stands
editoriales. En los stands, las casas editoriales presentan sus novedades a los
visitantes. Un stand puede alojar 1 o más editoriales, pues por temas de costos a
veces varias compañías pequeñas se ponen de acuerdo para alquilar un espacio
conjunto. Y hay editoriales que, por su tamaño, pueden ocupar más de 1 stand.
Cada editorial, además de su información general (nombre, dirección, gerente,
etc.), debe incluir la lista de libros van a presentar en la feria. En esta edición, se
hace una diferenciación entre 3 tipos de productos asociados: libros impresos
(título, autores, ISBN, páginas, género, formato (pasta dura, pasta suave), valor),
libros digitales (título, autores, ISBN, género, hipervínculos (si, no), formato (Kindle,
pdf, otro), valor) y audiolibros (título, autores, ISBN, duración, género, narrador,
formato (mp3, mp4, wma, otro), valor).
Tenga en cuenta los siguientes aspectos en su diseño:
• Un mismo libro puede tener varios formatos dentro de cada categoría; por
ejemplo, Cien Años de Soledad puede venir en edición impresa pasta dura y
pasta blanda, tener dos versiones de libro digital diferentes y tres audiolibros,
narrados por personas diferentes. Sin embargo, cada uno debe tener su propio
ISBN.
• Cada editorial tiene un número de ejemplares disponibles del material impreso.
Los contenidos digitales y audiolibros no tienen esa restricción.
• Un autor puede tener libros en diferentes editoriales.
El sistema debe permitir las siguientes funcionalidades de manera sencilla:
• Dado un autor, búsqueda de todas sus obras en la feria.
• Dada una obra genérica, búsqueda de todos los formatos de la obra, en todas
las editoriales.
• Dado un formato, búsqueda de todas las obras en ese formato.
Se requiere que provea:
• El diagrama de clase UML de este sistema. Criterio de evaluación: Clases
necesarias, relaciones adecuadas, uso del estándar UML, estructura que reduce
redundancia de información y facilidad de acceso a la información.
• Implemente los métodos necesarios para identificar al autor que tiene obras en
la mayor cantidad de editoriales
Universidad del Norte
Departamento de Ingeniería de Sistemas y Computación
Programación Orientada a Objetos
__EJERCICIO UML 2__
Chepacorinas y Diabolines
La nueva empresa C&D S.A.S (Chepacorinas y Diabolines) es una empresa
fabricante y distribuidora de alimentos típicos de la costa. La empresa cuenta con
varias fábricas en varias poblaciones aledañas a la carretera 25. Cada fábrica
tiene el registro de los empleados (nombre, cédula, teléfono, cargo, salario,
personas a cargo, jefe), órdenes de producción (cliente, cantidad, tipo de
producto, fecha de solicitud, fecha de entrega, valor).
Además, la empresa lleva registro detallado de sus canales de distribución propios,
los cuales principalmente están basados en fuerza laboral en campo. En cada
ciudad se tiene un administrador de venta y se registra en el sistema toda la
información sobre los vendedores matriculados y lleva un control diario de las
ventas por vendedor: ubicación de referencia (ciudad/población, punto de
interés, latitud, longitud, rango de maniobra), producto asignado (tipo de
producto, cantidad, fecha de entrega), total de ventas, producto devuelto ((tipo
de producto, cantidad, fecha de entrega).
Para resolver este problema usted debe:
a. Realizar un diagrama de clase UML para representar el modelo de la solución.
(Criterios de evaluación: Clases necesarias, relaciones adecuadas, uso del
estándar, estructura que reduce redundancia de información y facilidad de
acceso a la información)
b. Implemente el/los método/s que permita/n obtener cuál es el producto que
más se vende en una ciudad/población específica. Asuma que métodos get y
set de los atributos ya existen, y que clases como Date ya existen en el sistema

__1. ¿Qué significa por ej: paciente: Paciente dentro de Cita?__

Esto es un atributo cuyo tipo no es un dato primitivo (int, string, bool...) sino otra clase.

paciente → es el nombre del atributo.

Paciente → es el tipo de ese atributo, que resulta ser otra clase del diagrama.

👉 En cristiano: estás diciendo “cada Cita está asociada a un objeto de la clase Paciente”.
Eso es mucho más potente que poner solo un nombrePaciente: String, porque con la referencia al Paciente tenés todos los datos del paciente (cédula, dirección, historial, etc.), no solo el nombre.

📌 Cómo identificar cuándo usarlo:

Si lo que necesitás es guardar o relacionar entidades completas, usás otro objeto: paciente: Paciente, medico: Medico, servicio: ServicioPrestado.

Si lo que querés es solo un dato suelto (edad, fecha, precio…), ponés el tipo primitivo: edad: int, fecha: Date, precio: double.
__2. ¿Cuándo poner privado, protegido o público? (+, -, #)__

Esta es la clásica confusión. Pensalo así:

"-" Privado (private): solo la misma clase puede ver/modificar ese atributo o método.
→ Se usa casi siempre en atributos (para no dejar que cualquiera los cambie directo).

"#" Protegido (protected): la clase y sus hijas pueden acceder.
→ Se usa cuando querés heredar lógica interna. Ejemplo: Empleado tiene #salarioBase: double, y las subclases (EmpleadoTemporal, EmpleadoPlanta) pueden usarlo.

"+" Público (public): cualquier otra clase puede usarlo.
→ Normal en métodos (ejemplo: getNombre(): String, calcularPrecio(): double).

⚖️ Regla práctica:

Atributos → casi siempre privados (-).

Métodos → casi siempre públicos (+) si son la “interfaz” que otros usan.

Métodos internos o utilitarios → privados (-).

Atributos/métodos pensados para herencia → protegidos (#).
__3. ¿Qué poner en los métodos? (parámetros, tipo de retorno, void)__

Formato UML:

nombreMetodo(parametros): TipoRetorno


nombreMetodo → lo que hace la acción.

parametros → qué necesita para ejecutarse. Ejemplo: (fecha: Date, servicio: ServicioPrestado).

TipoRetorno → qué devuelve. Si no devuelve nada, ponés void.

📌 Ejemplos:

+consultarCitasPorPaciente(p: Paciente): List<Cita>


👉 Devuelve una lista de citas, y necesita un paciente.

+calcularEdad(): int


👉 No necesita parámetros, devuelve un entero.

+guardar(): void


👉 Hace la acción, pero no devuelve nada.

⚖️ Reglas prácticas:

Si el método realiza una acción → void. (Ej: guardarPaciente(), eliminarCita()).

Si el método responde con un dato → retorná el tipo de ese dato. (Ej: calcularEdad(): int, obtenerTotalVentas(): double).

Parámetros se ponen solo si el método necesita un dato externo para funcionar. Ej: buscarLibroPorIsbn(isbn: String): Libro.
__📄 Enunciado estilo parcial – CulturaApp__

La Alcaldía de la ciudad ha decidido lanzar CulturaApp, una plataforma digital para la gestión integral de los eventos culturales que se realizan a lo largo del año en diferentes espacios de la ciudad. La idea principal es que todos los conciertos, charlas, talleres y exposiciones se organicen desde un mismo sistema, donde los ciudadanos puedan inscribirse, reservar o comprar entradas, y los administradores puedan llevar control de la programación y la asistencia.

Cada evento cuenta con una fecha y una franja horaria, una descripción y la categoría a la que pertenece (concierto, exposición, taller, etc.). Los eventos se llevan a cabo en espacios físicos de la ciudad como teatros, auditorios o salas de exposición, los cuales tienen una ubicación detallada y una capacidad máxima que no puede superarse. En dichos espacios también se gestionan los equipos técnicos disponibles, como sistemas de sonido, proyectores o luminarias.

Los artistas o expositores participan en uno o varios eventos, y pueden ser tanto solistas como colectivos. La relación entre artistas y eventos debe poder ser consultada en cualquier momento por los organizadores, de modo que sea sencillo conocer qué artistas están involucrados en la programación de cada espacio.

Los ciudadanos que desean asistir a los eventos se registran en la plataforma como usuarios, almacenando datos personales como su nombre, cédula y correo electrónico. Estos usuarios pueden reservar gratuitamente los eventos sin costo, o adquirir entradas cuando se trate de eventos pagos. En este último caso, las entradas poseen un tipo (general, preferencial o VIP), un precio y un identificador único. Un mismo usuario puede reservar o comprar para varios eventos distintos, y también se contempla la posibilidad de adquirir paquetes que incluyan un conjunto de eventos con descuento. En todos los casos, el sistema debe garantizar que no se superen los cupos máximos definidos por la capacidad de cada espacio.

La administración de la plataforma requiere consultar periódicamente la programación de un espacio específico, conocer qué usuarios han asistido a cuáles eventos, identificar cuáles son los eventos con mayor número de asistentes en un periodo de tiempo dado, y controlar la disponibilidad de entradas por tipo. En el futuro, se prevé incorporar eventos virtuales o híbridos, que no dependen necesariamente de un espacio físico, sino que pueden transmitirse en línea. Por lo tanto, el diseño del sistema debe contemplar esa posible extensión sin necesidad de rehacer todo el modelo.
Universidad del Norte
Departamento de Ingeniería de Sistemas y Computación
Programación Orientada a Objetos
__PARCIAL 1__
MaxEPS
La entidad promotora de salud MaxEPS acaba de ingresar al mercado de los
servicios médicos y gracias a ello desean desarrollar un sistema que les permita
gestionar la información de los pacientes (nombre, cédula, edad, etc.), médicos
(nombre, cédula, edad, salario, etc.) y hospitales (nombre, ubicación (ciudad,
latitud, longitud), servicios prestados (nombre, descripción, costo, etc.), etc.) con el
fin de brindar una mejor atención.
La empresa considera que a medida que se incrementa su capacidad de
operación podrán brindar un conjunto de servicios más amplios en sus hospitales,
estos servicios junto con su información relevante deberán ser guardados dentro
del sistema. Es importante mencionar que no todos los hospitales prestarán los
mismos servicios.
Adicionalmente, el sistema debe permitir que los pacientes agenden (en un
horario) una cita médica para un servicio específico en el hospital que ellos deseen
(siempre y cuando este último ofrezca el servicio solicitado). Para esto el sistema le
asignará un médico que ofrezca ese servicio y que será el encargado de
completar el registro de la cita (fecha y hora, motivo de la consulta, síntomas,
diagnostico, medicamentos, etc.) una vez esta se haya realizado.
Finalmente, el sistema debe permitir realizar las siguientes acciones de manera
sencilla:
• Dado un paciente, consultar todo su historial clínico (citas médicas que ha
realizado).
• Dado un médico, consultar los últimos tres hospitales diferentes en los que ha
atendido citas médicas.
• Dado un hospital, consultar el servicio que más se ha provisto en un rango de
fechas específico.
Para resolver este problema usted debe:
a. (3.5) Realizar un diagrama de clase UML para representar el modelo de la
solución. (Criterios de evaluación: Clases necesarias, relaciones adecuadas, uso
del estándar, estructura que reduce redundancia de información y facilidad de
acceso a la información).
b. (1.5) Implemente los métodos que permitan obtener el médico con la mayor
cantidad de pacientes diferentes atendidos en un servicio específico en una
ciudad específica.
Para tener en cuenta:
• La solución (análisis) debe ser original.
• Este parcial es para desarrollar en parejas, todo tipo de fraude será castigado
según reglamento.
• NO se recibirán soluciones después de la fecha/hora límite de entrega.
• Debe documentar todo su código (la documentación debe ser de autoría
propia), esto será evaluado.
• Para enviar su solución se espera un comprimido que tenga la forma
apellidoestudiante1_apellidoestudiante2.zip. Este comprimido debe contener la
imagen/pdf del diagrama UML y un archivo de extensión .py con los métodos
solicitados.