# COMPILADORES

## [Definición de compilador](#definicion)
## [Estructura de un compilador](#estructura)
## [Análisis Léxico](#Analisislexico)
## [Análisis sintáctico](#analisissntactico)
## [Análisis semántico](#analisissemantico)
## [Generación de código intermedio](#GenerCodigoIntermedio)
## [Utilidad del análisis léxico](#utilidadAnalisisLexico)
## [ANÁLISIS SINTÁCTICO](#analisissintacticos2)
## [Análisis sintáctico lineal](#analisissintactivolineal)
## [ANÁLISIS SINTÁCTICO DESCENDENTE](#analisissintacticodecendente)
## [Analizadores sintácticos predictivos](#Analisissintacticopredictivo)
## [Analizadores sintácticos descendentes recursivos](#ASDR)
## [(ASDR)](#ASDR)
## [Construcción de la tabla de análisis](#tablaanalisis)

## [Tipos de Compiladores](#tiposCompiladores)

## [Clasificación de los compiladores](#compiladoresClasi)
###  [  - OnlineGDB C Compiler](#OnlineGDB)
###  [  - Tutorialspoint Compiler](#Tutorialspoint)
###  [  - Geekflare’s Online C Compiler](#Geekflare)
###  [  - Replit](#Replit)
###  [  - Rextester](#Rextester)
###  [  - myCompiler](#myCompiler)
###  [  - OneCompiler](#OneCompiler)
###  [  - CodeChef](#CodeChef)
###  [  - Code on Mobile](#Mobile)
###  [  - Techiedelight](#Techiedelight)
###  [  - Conclusión](#Conclusión)
### [¿Qué es un compilador?](#¿Quéesuncompilador?)

### [Compilador e intérprete: definición y diferencias](#compinterprete)
### [¿Qué es un intérprete?](#QueesunInterprete)
### [Compilador e intérprete: diferencias, en resumen](#diferenciasComInt)
### [Solución híbrida de intérprete y compilador: compilación en tiempo de ejecución](#SolucionHibridaComTra)

### [Ver Link Relacionados](#LinkRelacionados2)


#
### ¿En qué se diferencia de un Intérprete?(#diferencias)


#

## **Definición de compilador**<a name="definicion"></a>
#### Un compilador es un tipo especial de traductor en el que el lenguaje fuente es un
#### lenguaje de alto nivel y el lenguaje objeto es de bajo nivel (figura 1.1). 
 ![](img\fig1.1.png)
#

#### Un traductor es un programa que convierte el texto escrito en un lenguaje en texto
#### escrito en otro lenguaje (figura 1.2).
 ![](img\fig1.2.png)



 

#### Un ensamblador es un compilador donde el lenguaje fuente es un lenguaje
#### ensamblador y el lenguaje objeto es el código de la máquina.
#### La diferencia entre compilador e intérprete es que el compilador analiza todo el programa fuente, crea el programa objeto y luego permite su ejecución (sólo del programa objeto obtenido) y el intérprete lee sentencia por sentencia el programa fuente, la convierte en código objeto y la ejecuta. Por lo tanto, es fácil comprender que tras  compilar un programa, su ejecución es mucho más rápida que la ejecución de un programa interpretado.
#
#### Uno de los motivos de la existencia de programas interpretados es que hay algunos lenguajes de programación que permiten añadir sentencias durante la ejecución, cosa que no se podría hacer si fueran compilados. Algunos ejemplos son las versiones más antiguas de Basic y actualmente el lenguaje Phyton.
#
#### El compilador es asistido por otros programas para realizar su tarea, por ejemplo, se utiliza un preprocesador para añadir ficheros, ejecutar macros, eliminar comentarios, etcétera.
# 
#### El enlazador se encarga de añadir al programa objeto obtenido, las partes de las librerías necesarias.
#### El depurador permite al programador ver paso a paso lo que ocurre durante la ejecución del programa. 
#### Hay compiladores que no generan código máquina sino un programa en ensamblador, por lo que habrá que utilizar un programa ensamblador para generar el código máquina.
# 
## **Estructura de un compilador**<a name="estructura"></a>

#### Un compilador es un programa complejo que consta de una serie de pasos, generalmente entrelazados, y que como resultado convierte un programa en un lenguaje de alto nivel en otro de bajo nivel (generalmente código máquina o lenguaje ensamblador).
#
#### Los pasos o fases de la compilación están actualmente bien definidos y en cierta medida sistematizados, aunque no están faltos de dificultad. Esta aumenta conforme se incrementa la riqueza del lenguaje a compilar.
###### Las fases del proceso de compilación son las siguientes (figura 1.3):
 

![](img\fig1.3.png)



## **Análisis Léxico**<a name="Analisislexico"></a>
### Marco Teórico

#### El Análisis Léxico es la primera fase de un compilador y consiste en un programa que recibe como entrada el código fuente de otro programa (secuencia de caracteres) y produce una salida compuesta de tokens (componentes léxicos) o símbolos. Estos tokens sirven para una posterior etapa del proceso de traducción, siendo la entrada para el Análisis Sintáctico.

#### La especificación de un lenguaje de programación a menudo incluye un conjunto de reglas que definen el léxico. Estas reglas consisten comúnmente en expresiones regulares que indican el conjunto de posibles secuencias de caracteres que definen un token o lexema.

#### En algunos lenguajes de programación es necesario establecer patrones para caracteres especiales (como el espacio en blanco) que la gramática pueda reconocer sin que constituya un token en sí.
# 
## **Función del Analizador Léxico**

#### Su principal función consiste en leer los caracteres de entrada y elaborar como salida una secuencia de componentes léxicos que utiliza el analizador sintáctico para hacer el análisis. En la figura 1 se puede apreciar el esquema de una interacción que se aplica convirtiendo el analizador léxico en una subrutina o corrutina del analizador sintáctico. Recibida la orden "obtener el siguiente componente léxico" del analizador sintáctico, el analizador léxico lee los caracteres de entrada hasta que pueda identificar el siguiente componente léxico.
#
![](img\fig1.32.png)
 #


## **Análisis sintáctico**<a name="analisissntactico"></a>
#### El analizador léxico tiene como entrada el código fuente en forma de una sucesión de caracteres. El analizador sintáctico tiene como entrada los lexemas que le suministra el analizador léxico y su función es comprobar que están ordenados de forma correcta (dependiendo del lenguaje que queramos procesar). Los dos analizadores suelen trabajar unidos e incluso el léxico suele ser una subrutina del sintáctico. Al analizador sintáctico se le suele llamar párser. El párser genera de manera teórica un árbol sintáctico. Este árbol se puede ver como una estructura jerárquica que para su construcción utiliza reglas recursivas. La estructuración de este árbol hace posible diferenciar entre aplicar unos operadores antes de otros en la evaluación de expresiones. Es decir, si tenemos esta expresión en Java:



## **Análisis semántico**<a name="analisissemantico"></a>
#### Esta fase toma el árbol sintáctico teórico de la anterior fase y hace una serie de comprobaciones antes de obtener un árbol semántico teórico.
#### Esta fase es quizás la más compleja. Hay que revisar que los operadores trabajan sobre tipos compatibles, si los operadores obtienen como resultado elementos con tipos adecuados, si las llamadas a subprogramas tienen los parámetros adecuados tanto en número como en tipo, etc.
#### Esta fase debe preparar el terreno para atajar las fases de generación de código y debe lanzar los mensajes de error que encuentre. En resumen, su tarea es revisar el significado de lo que se va leyendo para ver si tiene sentido.
#### Esta fase, las anteriores y las siguientes se detallarán más adelante, en el desarrollo de los otros capítulos.

## **Generación de código intermedio**<a name="GenerCodigoIntermedio"></a>
#### El código intermedio (CI) es la representación en un lenguaje sencillo (incluso inventado por el creador del compilador) de la secuencia real de las operaciones que se harán como resultado de las fases anteriores.
#### Se trata de representar de una manera formalizada las operaciones a llevar a cabo en un lenguaje más cercano a la máquina final, aunque no a una máquina concreta sino a una máquina abstracta. Es decir, no consiste en generar código ensamblador para una máquina basada en un procesador M68000, por ejemplo, sino en generar código que podría luego implementarse en cualquier máquina. Este lenguaje intermedio debe de ser lo más sencillo posible y, a la vez, lo más parecido a la manera de funcionar de la máquina final 

## **Utilidad del análisis léxico**<a name="utilidadAnalisisLexico"></a>

#### Las técnicas que vamos a describir en este capítulo se utilizan tanto para laconstrucción de compiladores como para otras áreas no tan relacionadas con este campo de la informática. Por ejemplo, se utilizan para interpretar el código HTML de una página web, para interpretar un archivo de tipo .ini, etcétera.
#
#### El analizador léxico va leyendo del fichero de entrada los caracteres secuencialmente y los va agrupando, según las directivas programadas, en tokens con un significado conocido por el programador. Los tokens serán la entrada del analizador sintáctico.
#
#### Podríamos pensar que el papel del analizador léxico podría ser asumido por el analizador sintáctico, pero el diferenciar estas dos tareas hace posible aplicar técnicas específicas para cada una de ellas.
#
#### El analizador léxico hace las funciones, a la vez, de preprocesador ya que se encarga de eliminar los caracteres innecesarios para el proceso de compilación. Por ejemplo, elimina los espacios en blanco que hay entre palabra y palabra (siempre que no sean necesarios, como por ejemplo dentro de las cadenas de texto).
#
#### Una ventaja importante es que permite obtener estructuras similares aun cuando los caracteres de entrada no lo sean. Por ejemplo, debe ser equivalente “6+2/4” a “6 +2 / 4”. En ambos casos, el analizador léxico suministra al sintáctico los tokens 6, +, 2, / y 4.
#### Resumiendo, las funciones del analizador léxico son:
#### Agrupar caracteres según categorías establecidas por la especificación dellenguaje fuente.
#### Rechazar texto con caracteres ilegales o agrupados según un criterio no especificado.
#
## **Funcionamiento**
#
#### La relación entre el analizador léxico y el sintáctico es una relación de maestro esclavo. El sintáctico demanda al léxico que lea el siguiente lexema y el léxico lee los caracteres necesarios del fichero de entrada hasta que consigue completar un lexema, que será entregado a su maestro (el analizador sintáctico). Esta relación viene representada en la figura 2.1.
#
#### El funcionamiento del analizador léxico es:
- Construir tokens válidos a partir de la lectura carácter a carácter del fichero de entrada.
- Pasar tokens válidos al analizador sintáctico.
- Gestionar el manejo del fichero de entrada.
- Ignorar los espacios en blanco, comentarios y demás caracteres o tokens innecesarios para el proceso de análisis.
- Avisar de los errores encontrados en esta fase.
- Llevar la cuenta del número de línea para incluirlo en el aviso de error (esto es imprescindible para que el usuario pueda encontrar y corregir el error).
- Hacer las funciones de preprocesador. 
 

![](img\fig1.2.1.png)

#


## **ANÁLISIS SINTÁCTICO**<a name="analisissintacticos2"></a>

## Funciones del analizador sintáctico
#### La función principal del analizador sintáctico (AS o párser) es comprobar que los tokens que le suministra el analizador léxico (AL o léxer) van ordenados según la especificación de la gramática del lenguaje a compilar. Y si no es así, dar los mensajes de error adecuados, pero continuar funcionando sin detenerse, hasta que se llegue al final del fichero de entrada. Es esencial que el proceso de análisis no se detenga al primer error encontrado, ya que así podrá informar al usuario en un solo informe de todos los errores generados.
#
#### Aparte de esta función principal, el párser es la unidad que guía todo el proceso, o casi todo, de la compilación. Esto es así porque por un lado va solicitando al léxer los tokens y al mismo tiempo va dirigiendo el proceso de análisis semántico y generación de código intermedio. Por lo que muchas veces se le llama al proceso de análisis semántico y generación de código intermedio, traducción dirigida por la sintaxis
 
![](img\fig3.1.png)
# 
#### Generalmente, los analizadores sintácticos obtienen un árbol teórico que permite expresar el orden de los lexemas según van apareciendo. Ese árbol debe ser el modelo de donde salga el análisis semántico. Pero lo normal es que si utilizamos el método de la traducción dirigida por la sintaxis no lleguemos ni siquiera a plantearnos la generación del árbol ya que el párser realizará las acciones semánticas e incorporará los métodos para realizar la generación de código intermedio y avisará de errores y su recuperación.
#
#### Es decir, el analizador léxico hará las funciones de las dos siguientes etapas (analizador semántico y generación de código intermedio).

#### Pero si damos la oportunidad a la creación del árbol de análisis sintáctico, recorriéndolo es posible crear una representación intermedia del programa fuente, ya sea en forma de árbol sintáctico abstracto o en forma de programa en un lenguaje intermedio.
#
#### Para generar párser, podemos utilizar dos técnicas, o bien lo hacemos a mano (es difícil aunque eficiente en su funcionamiento) o mediante herramientas que lo generan automáticamente (es menos eficiente pero más fácil de implementar).
##
#### Para que un AS funcione, debemos especificar el lenguaje que debe poder leer.
#### Para especificar este lenguaje, debemos representarlo con unas reglas únicas y bien formadas de manera que el párser funcione de una manera bien definida. Es decir, el lenguaje debe ser formal (tener unas reglas bien definidas). A estas reglas se le llama gramática. Por lo tanto, el primer paso para poder implementar un AS es definir la gramática que debe ser capaz de analizar. 
#
## **Análisis sintáctico lineal** <a name="analisissintactivolineal"></a>
#### Hay varios algoritmos de análisis sintáctico (incluso para gramáticas ambiguas), pero su coste computacional es elevado (del orden de n3). Por lo que debemos modificar un poco nuestra gramática (si es necesario) para que podamos utilizar un algoritmo de menor coste computacional (de coste lineal). Si conseguimos eliminar la ambigüedad, podremos utilizar dos estrategias:
#### **Análisis descendente:** partimos de la raíz del árbol de análisis sintáctico y vamos aplicando reglas por la izquierda para obtener una derivación por la izquierda del símbolo inicial. Para saber la regla a aplicar, vamos leyendo tokens de la entrada. De esta manera, construimos el árbol de análisis sintáctico. Recorriendo el árbol en profundidad, de izquierda a derecha, tendremos en las hojas los tokens ordenados.
#### **Análisis ascendente:** partimos de la cadena de entrada y vamos construyendo el árbol a partir de las hojas para llegar a la raíz. Si recorremos el árbol generado como en el caso anterior, encontraríamos los tokens ordenados.
#

## **ANÁLISIS SINTÁCTICO DESCENDENTE**<a name="analisissintacticodecendente"></a>
## **Introducción**
#### El análisis sintáctico descendente (ASD) consiste en ir haciendo derivaciones a la izquierda, partiendo del axioma inicial, hasta obtener la secuencia de derivaciones que reconoce a la sentencia. En realidad, se trata de aplicar un método de búsqueda en un árbol. El método es de búsqueda en profundidad.
#
#### Tal y como se dijo en el capítulo anterior, se va construyendo un árbol sintáctico en el que la raíz es el axioma inicial y los nodos son todas las derivaciones posibles para poder procesar una determinada sentencia. Pero podemos construir un árbol universal que englobe todas las posibles sentencias del lenguaje (o más bien de la gramática).
#
#### El método de ASD intenta encontrar en el árbol universal la sentencia a reconocer en cada momento. Pero es posible que esta búsqueda en profundidad se haga interminable porque haya ramas infinitas. Para evitar este inconveniente, se debe establecer un criterio para terminar la búsqueda por esa rama y establecerla por otra.
#

## **Analizadores sintácticos predictivos**<a name="Analisissintacticopredictivo"></a>

#
#### Hemos visto que los analizadores sintácticos con retroceso son ineficientes. Pero hay maneras de aumentar la eficiencia. Una de ellas es siendo capaces  de saber qué regla aplicar del conjunto de reglas aplicables en cada caso. Es decir, si tenemos un token y una serie de reglas a aplicar, debemos poder elegir una de ellas mirando si el primer token coincide con el que tenemos seleccionado.
#
#### Por ejemplo, en el ejemplo del epígrafe anterior, debíamos probar con cada una de las reglas 5, 6 y 7 para el no terminal F, pero si pudiéramos saber que el token actual es num, directamente aplicaríamos la regla 6 ya que las otras no podrían ser válidas. Si tuviéramos una gramática en que en cada caso supiéramos con exactitud qué regla aplicar sabiendo sólo el primer token de la regla, podríamos utilizar un nuevo tipo de analizador sintáctico descendente, el analizador sintáctico descendente predictivo (ASDP).
#
#### A las gramáticas que cumplen estos requisitos, se les llama LL(1). Aunque su número es reducido, hay técnicas para convertir gramáticas que no sean LL(1) en LL(1). Los ASDP son mucho menos costosos computacionalmente hablando que los ASD, por lo que se utilizan a la hora de implementar compiladores.
#
#### Para implementar un ASDP, se utiliza el concepto de conjunto de predicción. Se trata de relacionar cada regla de la gramática con todos los posibles terminales a que se puede acceder aplicando dicha regla.
#

## **Analizadores sintácticos descendentes recursivos**
## **(ASDR)**<a name="ASDR"></a>
#
#### Son un tipo especial de ASDP y por tanto sólo pueden analizar gramáticas LL(1).
#### Se trata de implementar tantas funciones recursivas como no terminales de la gramática.
#### Para cada no terminal se crea una función recursiva.
#### En la sección 3.5 vimos cómo construir un analizador sintáctico con diagramas de sintaxis. A partir de estos diagramas de sintaxis, y conociendo el siguiente token a analizar, es posible implementar un analizador sintáctico. En concreto, se trata de un analizador sintáctico descendente recursivo.
#### Para poder implementar un ASDR, es necesario que el lenguaje de
implementación admita la recursión. 
#### El proceso a seguir es crear los diagramas de sintaxis conforme a la gramática y a partir de ellos, realizar la implementación en el lenguaje elegido. 
#
## ** Implementación de ASDP’s**
#
#### Hemos visto en la sección anterior, que si conocemos el siguiente token a analizar, podemos construir un analizador sintáctico predictivo mediante diagramas de sintaxis y un lenguaje que admita la recursión. Pero hay otra manera de construir este tipo de analizadores: se trata de implementarlos a partir de una tabla.
#
#### Vamos a aprender en este apartado cómo construir esta tabla y a partir de ella implementar el analizador. 

#### En vez de hacer llamadas recursivas, utilizaremos una pila de símbolos. Cuando tengamos el siguiente token, miraremos en la tabla, que se llama tabla de análisis, para saber qué producción toca invocar. Una vez construida la tabla, procederemos a implementar un algoritmo que se encargará de todo el proceso de análisis. 

## **Construcción de la tabla de análisis**<a name="tablaanalisis"></a>
#### La tabla consta de filas, una por cada no terminal de la gramática, y columnas, una por cada terminal de la gramática y el símbolo de fin de fichero ($). Para llenar las diferentes celdas, primero calcularemos los conjuntos de predicción de todas las reglas.
#
#### Para cada fila de la tabla buscaremos todas las reglas en las que el no terminal de la fila aparezca a la izquierda de la regla. Le llamaremos a este conjunto de reglas, reglas de fila. Tomamos cada regla del conjunto de reglas de fila y para cada uno de los elementos de su conjunto de predicción, ponemos la regla en la columna del terminal de su  conjunto de predicción (y en la fila de su conjunto de reglas de fila). En las celdas que se queden vacías pondremos una señal para indicar que hay un error sintáctico (por ejemplo, la palabra error).

#

## Tipos de Compiladores<a name="tiposCompiladores"></a>
#

#### El escritor del compilador, como cualquier programador, puede usar con provecho herramientas de software tales como depuradores, administradores de versiones, analizadores, etcétera. Además de estas herramientas de desarrollo de software, se han creado herramientas más especializadas para ayudar a implantar varias fases de un compilador. Poco después de escribirse el primer compilador, aparecieron sistemas para ayudar en el proceso de escritura de compiladores. A menudo se hace referencia a estos sistemas como compiladores de compiladores, generadores de compiladores o sistemas generadores de traductores. En gran parte, se orientan en torno a un modelo particular de lenguaje, y son más adecuados para generar compiladores de lenguajes similares al del modelo.
#
#### Por ejemplo, es tentador suponer que los analizadores léxicos para todos los lenguajes son en esencia iguales, excepto por las palabras clave y signos particulares que se reconocen. Muchos compiladores de compiladores de hecho producen rutinas fijas de análisis léxico para usar en el compilador generado. Estas rutinas sólo difieren en la lista de palabras clave que reconocen, y esta lista es todo lo que debe proporcionar el usuario. El planteamiento es válido, pero puede no ser funcional si se requiere que reconozca componentes léxicos no estándar, como identificadores que pueden incluir ciertos caracteres distintos de letras y dígitos.
#
#### Se han creado algunas herramientas generales para el diseño automático de componentes específicos de compilador. Estas herramientas utilizan lenguajes especializados para especificar e implantar el componente, y pueden utilizar algoritmos bastante complejos. Las herramientas más efectivas son las que ocultan los detalles del algoritmo de generación y producen componentes que se pueden integrar con facilidad al resto del compilador. La siguiente es una lista de algunas herramientas útiles para la construcción de compiladores:
#
#### I. Generadores de analizadores sintácticos. Estos generadores producen analizadores sintácticos, normalmente a partir de una entrada fundamentada en una gramática independiente del contexto. En los primeros compiladores, el análisis sintáctico consumía no sólo gran parte del tiempo de ejecución del compilador, sino gran parte del esfuerzo intelectual de escribirlo. Esta fase se considera ahora una de las más fáciles de aplicar. Muchos de los “pequeños lenguajes” utilizados en la composición de este libro, como, PIC (Kernighan ([1982]) y EQN, se aplicaron en unos días por medio del generador de analizadores sintácticos ya vistos. Muchos de los generadores de analizadores sintácticos utilizan poderosos algoritmos de análisis sintáctico, y son demasiado complejos para realizarlos manualmente.
#
#### 2. Generadores de analizadores léxicos. Estas herramientas generan automáticamente analizadores léxicos. La organización básica del analizador léxico resultante es en realidad un autómata finito.
#
#### 3. Dispositivos de traducción dirigida por la sintaxis. Estos producen grupos de rutinas que recorren el árbol de análisis sintáctico, como el de la figura 1.4, generando código intermedio. La idea básica es que se asocian una o más “traducciones” con cada nodo del árbol de análisis sintáctico, y cada traducción se define partiendo de traducciones en sus nodos vecinos en el árbol.
#
#### 4. Generadores automáticos de código. Tales herramientas toman un conjunto de reglas que definen la traducción de cada operación del lenguaje intermedio al lenguaje de máquina para la máquina objeto. Las reglas deben incluir suficiente detalle para poder manejar los distintos métodos de acceso posibles a los datos: por ejemplo, las variables pueden estar en registros, en una posición fija (estática) de memoria o pueden tener asignada una posición en una pila. La técnica fundamental es la de “concordancia de plantillas”. Las proposiciones de código intermedio se reemplazan por “plantillas” que representan secuencias de instrucciones de máquina, de modo que las suposiciones sobre el almacenamiento de las variables concuerden de plantilla a plantilla. Como suele haber muchas opciones en relación con la ubicación de las variables (por ejemplo, en uno o varios registros o en memoria), hay muchas formas posibles de ‘cubrir’ el código intermedio con un conjunto dado de plantillas, y es necesario seleccionar una buena cobertura sin una explosión combinatoria en el tiempo de ejecución del compilador.
#
#### 5. Dispositivos para análisis de flujo de datos. Mucha de la información necesaria para hacer una buena optimación de código implica hacer un ‘análisis de flujo de datos”, que consiste en b recolección de información sobre la forma en que se transmiten los valores de una parte de un programa a cada una de las otras partes. Las distintas tareas de esa naturaleza se pueden efectuar esencialmente con la misma rutina, en la que el usuario proporciona los detalles relativos a la relación que hay entre las proposiciones en código intermedio y la información que se está recolectando.
#

## Clasificación de los compiladores<a name="compiladoresClasi"></a>

# 

#### a) Compilador cruzado. Genera un código ejecutable en un ordenador distinto de aquel en que se realiza la compilación.

 

#### b) Compilador de montaje y ejecución. Se fragmenta el programa fuente en módulos que se compilan por separado, y una vez compilados se unen mediante un enlazador para formar un módulo ejecutable.

 

#### c) Compilador en una pasada. Examina el código fuente una sola vez, generando el código objeto.

 

#### d) Compilador de pasadas múltiples Requiere varias lecturas del programa fuente para producir y optimizar el código objeto.

 

#### e) Compilador de optimización. Lee el código fuente, lo analiza, optimiza y descubre errores potenciales sin ejecutar el programa.

 

#### f) Compilador incremental. Compila el programa fuente, en caso de detectar errores al volver a compilar el programa corregido, solo compila las modificaciones que se han hecho respecto al primero.

 

#### g) Ensamblador. El lenguaje fuente es el lenguaje ensamblador.

 

#### h) Autocompilador. Es el compilador que está escrito en el mismo lenguaje a compilar, básicamente nos sirve para hacer ampliaciones al lenguaje, mejorar el código generado, etc.

 

#### i) Metacompilador. “Compilador de compiladores”. Obtiene como entrada la definición de un lenguaje y como salida el compilador para dicho lenguaje.

#

# compiladores de C en línea para ejecutar código en el navegador

## OnlineGDB C Compiler<a name="OnlineGDB"></a>
#
![](https://geekflare.com/wp-content/uploads/2021/08/onlinegdb.png)
#
#### Compilador OnlineGDB es una plataforma que admite múltiples lenguajes de programación, incluido C / C ++.

#### El portal web ofrece una interfaz de usuario limpia y es fácil de usar. No es necesario crear una cuenta para escribir el código y ejecutarlo.

#### El compilador en línea le permite embellecer el código, compartirlo a través de un enlace y guardarlo (se necesita una cuenta).

#### Puede modificar el tema (tema oscuro compatible) y habilitar la función de autocompletar para escribir el código. Además, también puede agregar indicadores de compilador adicionales para ayudarlo a depurar.

#### Si ya tiene el código con usted, cárguelo en el portal en el formato correcto y ejecútelo para obtener el resultado.
#
## Tutorialspoint Compiler<a name="Tutorialspoint"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/tutorialspoint.png)
# 
#### Punto de tutoriales es uno de los compiladores / herramientas en línea más populares relacionados con los lenguajes de programación. El compilador en línea C / C ++ es solo una de las ofertas.

#### Necesita crear una cuenta para compartir el código que ejecuta a través del compilador.

#### No admite compartir el código a través de enlaces (sin iniciar sesión), pero ofrece una interfaz mucho más limpia que muchos otros compiladores en línea.

#### A diferencia de otros, tiene la capacidad de bifurcar un código con un solo clic. Hay varias otras opciones disponibles para que las explore.
# 

## Geekflare’s Online C Compiler<a name="Geekflare"></a>

#### En Geekflare también hemos creado un compilador en línea para el beneficio de aquellos que quieran aprender a codificar. Nuestro compilador de C en línea no requiere registro ni instalación y compila y ejecuta instantáneamente sus programas.

![](https://geekflare.com/wp-content/uploads/2021/09/online-C-cimplier-1200x619.jpg)
#
#### El compilador de Geekflare también le permite ejecutar programas en otros lenguajes como Java, Python, Javascript, C ++ y más. ¡Simplemente haga clic en la lista desplegable en la esquina superior derecha para cambiar su lenguaje de programación!

#
## Replit<a name="Replit"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/replit-c-compiler.png)

#### Repita es un compilador en línea completo que admite varios lenguajes de programación, características premium opcionales y una oferta de equipo separada.

#### Si bien puede usarlo de forma gratuita para aprender y explorar, esto se puede usar profesionalmente si opta por el plan premium.

#### A diferencia de otras opciones, deberá registrarse en el servicio para obtener la experiencia completa. Sin una cuenta, ofrece funciones limitadas.

#### Además de todas las funciones básicas, puede consultar el historial de versiones de su código, configurar una base de datos y colaborar / interactuar mediante comentarios.

#### También encontrará varios proyectos disponibles como escaparate de la comunidad, que puede explorar y bifurcar para sus proyectos.

#
## Rextester<a name="Rextester"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/rextester.png)
#
#### Rextester es un compilador simple de C / C ++ que no ofrece muchas funciones pero le permite ejecutar y depurar el código.

#### Apoya la colaboración, pero solo se limita a los patrocinadores que apoyan el proyecto. Tiene la opción de cambiar entre el tema oscuro / claro y un diseño vertical / horizontal.
#
## myCompiler<a name="myCompiler"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/mycompiler.png)
#
#### mi Complier es otro compilador C / C ++ en línea sencillo para ejecutar programas.

#### Tiene opciones limitadas y puede guardar su trabajo registrándose en el portal.
#

## OneCompiler<a name="OneCompiler"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/onecompiler-c.png)

#

#### uncompilador es una plataforma fantástica que le permite ejecutar código compatible con una amplia gama de lenguajes de programación.

#### Cuenta con una interfaz de usuario limpia para brindarle una buena experiencia al ejecutar programas. Te permite cambiar entre un tema oscuro y un tema claro.

#### Además de eso, encontrará varios tutoriales, publicaciones y desafíos de codificación que te ayudan a aprender mientras lo usas.

#### También tiene una sección de ayuda de sintaxis útil justo debajo del editor para abordar rápidamente algunos conceptos comunes que le ayudarán a aprender. Puede optar por registrarse, pero no necesita una cuenta para utilizar el compilador.
#

## CodeChef<a name="CodeChef"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/codechef-compiler.png)
#
#### CodeChef es un IDE en línea popular que se utiliza a menudo para organizar concursos y desafíos de codificación.

#### Es posible que no tenga la opción de colaborar o guardar su código. Pero es una buena opción si desea ejecutar algún código o aceptar desafíos / concursos.

#### Ofrece muchos atajos de teclado para aprovechar algunos ajustes que puede realizar al escribir código en su editor.

#### Esta es una buena opción para aprender porque puede practicar ejercicios basados ​​en la dificultad / experiencia, lo que debería mantener las cosas interesantes para usted.

#
## Code on Mobile<a name="Mobile"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/mobile-c-compiler.jpg)
#
#### Compilador en línea: código en dispositivos móviles le permite ejecutar código sobre la marcha a través de dispositivos móviles.

#### Vale la pena señalar que esto solo está disponible para teléfonos inteligentes Android. También obtienes una función de guardado automático con él.
#

## Techiedelight<a name="Techiedelight"></a>
![](https://geekflare.com/wp-content/uploads/2021/08/techiedelight.png)
#
#### Techiedelight es otro compilador C / C ++ en línea útil que le permite cargar / descargar su código.

#### También puede optar por compartir el código con otra persona para colaborar sin crear una cuenta.

#### También le permite incrustar el código fuente en cualquier otro sitio web para compartirlo con el público.
#

## Conclusión<a name="Conclusión"></a>
#### La facilidad de uso y la flexibilidad de un compilador en línea permiten que un principiante practique y aprender programación C / C ++.

#### Y las características específicas en línea, como tener una copia de seguridad de su código y colaborar con un enlace, son algunas de las cosas que incluso los profesionales apreciarán.

#### La elección de un compilador de C en línea para ejecutar su código tiene sus ventajas. Elija uno y comience con su aventura de codificación.

#### A continuación, es posible que también desee ver algunos de los mejores compiladores de Python en línea o alguna Herramientas de finalización de código impulsadas por IA si tienes curiosidad

#

# Practica para entregar el Martes 1 de Noviembre 2022**

#


# ¿En qué se diferencia de un Intérprete?<a name="diferencias"></a>

#### Para responder a esta pregunta primero debemos conocer que es y para qué sirve un Intérprete.
#
#### Un intérprete lee un programa fuente ejecutable, escrito en un lenguaje de programación de alto nivel, así como datos para este programa, y ​​ejecuta el programa contra los datos para producir algunos resultados. Un ejemplo es el intérprete de shell de Unix, que ejecuta comandos del sistema operativo de forma interactiva.
#
#### Hay que tener en cuenta que tanto los intérpretes como los compiladores (como cualquier otro programa) están escritos en un lenguaje de programación de alto nivel (que puede ser diferente del idioma que aceptan) y se traducen en código máquina.
#
#### Por ejemplo, un intérprete de Java puede escribirse completamente en C o incluso en Java. El programa fuente del intérprete es independiente de la máquina ya que no genera código de máquina.
#
#### Un intérprete generalmente es más lento que un compilador porque procesa e interpreta cada enunciado de un programa tantas veces como el número de evaluaciones de esta afirmación. Por ejemplo, cuando se interpreta un bucle for, las afirmaciones dentro del cuerpo for-loop se analizarán y evaluarán en cada paso del bucle. Algunos lenguajes, como Java y Lisp, vienen con un intérprete y un compilador. Los programas fuente de Java (clases Java con extensión .java) son traducidos por el compilador javac en archivos de códigos de bytes (con extensión .class).
#
#### El intérprete de Java, llamado Java Virtual Machine (JVM), en realidad puede interpretar códigos de bytes directamente o puede compilarlos internamente en código máquina y luego ejecutar ese código.
#
#### Los compiladores son procesos complejos debido a que tienen varias fases por las que un programa fuente debe de pasar antes de convertirse en un programa ejecutable, los pasos son los siguiente
#


# Compilador e intérprete: definición y diferencias<a name="compinterprete"></a>

#### A la hora de elegir un lenguaje de programación, se debe prestar especial atención a dos cosas: por una parte, el lenguaje debe contar con todos los componentes básicos necesarios para el proyecto de software que se quiera desarrollar. Por la otra, tiene que permitir programar e implementar este proyecto de la manera más sencilla posible. La buena legibilidad y simplicidad del código fuente son fundamentales para garantizar lo segundo, porque estas características no solo facilitan el aprendizaje del lenguaje de programación, sino también, obviamente, su posterior utilización en el día a día.
# 
#### En primer lugar, para que el ordenador o el procesador puedan comprender las instrucciones que contiene un programa desarrollado previamente, el código fuente escrito en los lenguajes de programación actuales debe convertirse a un formato legible por máquina. De este procedimiento, dependiendo del lenguaje de programación, se encarga un compilador o un intérprete. ¿Qué son exactamente estos dos programas? Y ¿en qué se diferencian?

## ¿Qué es un intérprete?<a name="QueesunInterprete"></a>
#
#### Un intérprete es un programa informático que procesa el código fuente de un proyecto de software durante su tiempo de ejecución, es decir, mientras el software se está ejecutando, y actúa como una interfaz entre ese proyecto y el procesador. Un intérprete siempre procesa el código línea por línea, de modo que lee, analiza y prepara cada secuencia de forma consecutiva para el procesador. Este principio también se aplica a las secuencias recurrentes, que se ejecutan de nuevo cada vez que vuelven a aparecer en el código. Para procesar el código fuente del software, el intérprete recurre a sus propias bibliotecas internas: en cuanto una línea de código fuente se ha traducido a los correspondientes comandos legibles por máquina, esta se envía directamente al procesador.

#

#### El proceso de conversión no finaliza hasta que se ha interpretado todo el código. Solo se interrumpe prematuramente si se produce un fallo durante el procesamiento, lo que simplifica mucho la resolución de los errores, ya que la línea de código problemática se detecta inmediatamente después de ocurrir el fallo.

#####  Nota
    BASIC, Perl, Python, Ruby y PHP son algunos de los lenguajes de programación más famosos que dependen de un intérprete para ser traducidos de código fuente a código máquina. Por ello, también suelen llamarse lenguajes interpretados.


## ¿Qué es un compilador?<a name="¿Quéesuncompilador?">

#### Un compilador es un programa informático que traduce todo el código fuente de un proyecto de software a código máquina antes de ejecutarlo. Solo entonces el procesador ejecuta el software, obteniendo todas las instrucciones en código máquina antes de comenzar. De esta manera, el procesador cuenta con todos los componentes necesarios para ejecutar el software, procesar las entradas y generar los resultados. No obstante, en muchos casos, durante el proceso de compilación tiene lugar un paso intermedio fundamental: antes de generar la traducción final en código máquina, la mayoría de los compiladores suelen convertir el código fuente en un código intermedio (también llamado código objeto) que, a menudo, es compatible con diversas plataformas y que, además, también puede ser utilizado por un intérprete.
#
#### Al producir el código, el compilador determina qué instrucciones van a enviarse al procesador y en qué orden. Si las instrucciones no son interdependientes, incluso es posible que puedan procesarse en paralelo.
#
#####  Nota
    Entre los lenguajes compilados puros se incluyen, entre otros, los veteranos C, C++ y Pascal.


## Compilador e intérprete: diferencias, en resumen<a name="diferenciasComInt"></a>
#
#### Tanto los compiladores como los intérpretes cumplen la función de convertir el código de software que se ha escrito a un formato ejecutable y legible por máquina. Sin esta traducción, los procesadores informáticos no podrían ejecutar el software en lenguajes como C, C++, PHP, Python o Ruby, lo que convierte estos programas en unos componentes imprescindibles para utilizar ordenadores, portátiles o smartphones. En los apartados anteriores, hemos visto que compiladores e intérpretes presentan algunas diferencias básicas, algo que debe tenerse especialmente en cuenta a la hora de elegir un lenguaje de programación adecuado para desarrollar un nuevo software. En la siguiente tabla, se resumen los aspectos clave que caracterizan intérpretes y compiladores:
# 
| 	            |Intérprete	 |Compilador |
|---------------|------------|-----------|
| Momento en que se traduce el código fuente |Durante el tiempo de ejecución del software|Antes de ejecutar el software|
|Procedimiento de traducción|Línea por línea|Siempre todo el código|
|Presentación de errores de código|Después de cada línea|	En conjunto, después de toda la compilación|
|Velocidad de traducción|Alta|Baja|
|Eficiencia de traducción|	Baja|	Alta|
|Coste de desarrollo|Bajo|Alto|
|Lenguajes típicos|	PHP, Perl, Python, Ruby, BASIC|C, C++, Pascal|
#
#### Si observamos las diferencias entre compilador e intérprete, vemos claramente los puntos fuertes y débiles de cada solución para traducir el código fuente: con el intérprete, los programas se pueden ejecutar de inmediato y, por lo tanto, se inician mucho más rápido. Además, el desarrollo es mucho más fácil que con un compilador, porque el proceso de depuración (es decir, la corrección de errores) se lleva a cabo igual que la traducción, línea por línea. En el caso del compilador, primero debe traducirse todo el código antes de poder resolver los errores o iniciar la aplicación. Sin embargo, una vez que se ejecuta el programa, los servicios del compilador ya no son necesarios, mientras que el intérprete continúa utilizando los recursos informáticos.
#
|                     |Ventaja   |Inconveniente|
|---------------------|----------|-------------|
|Intérprete|Proceso de desarrollo sencillo (sobre todo en términos de depuración)|Proceso de traducción poco eficiente y velocidad de ejecución lenta|
|Compilador|Proporciona al procesador el código máquina completo y listo para ejecutar|Cualquier modificación del código (resolución de errores, desarrollo del software, etc.) requiere volverlo a traducir|

#
## Solución híbrida de intérprete y compilador: compilación en tiempo de ejecución<a name="SolucionHibridaComTra"></a>
#
#### Para compensar los puntos débiles de ambas soluciones, también existe el llamado modelo de compilación en tiempo de ejecución (en inglés, just-in-time-compiler, o “compilador justo a tiempo”). Este tipo de compilador, que a veces también se conoce por el término inglés compreter (acrónimo de compiler e interpreter), rompe con el modelo habitual de compilación y traduce el código del programa durante el tiempo de ejecución, al igual que el intérprete. De esta forma, la alta velocidad de ejecución típica de los compiladores se complementa con la simplificación del proceso de desarrollo.
#

## Ver Link Relacionados<a name="LinkRelacionados2"></a>
[AOT vs JIT compilation in Java](https://youtu.be/sJVenujWGjs)
#
[Lenguajes compilados o lenguajes interpretados ¿Cuál es la diferencia?](https://youtu.be/ojqusTBq4A0)
#

