#Estándar para la codificación PHP en Desarrollo Web



En el siguiente documento se pretende tener un estándar para la codificación del contenido tanto del backend como el frontend.



* [Formato de archivo](#1-formato-de-archivo)

* [Etiqueta de cierre de PHP](#2-etiqueta-de-cierre-de-php)

* [Nombre de archivo](#3-nombre-de-archivo)

* [Nombre de clases y métodos](#4-nombre-de-clases-y-metodos)

* [Nombre de variables](#5-nombre-de-variables)

* [Comentando](#6-comentando)

* [Constantes](#7-constantes)

* [TRUE, FALSE y NULL](#8-true-false-y-null)

* [Operadores lógicos](#9-operadores-logicos)

* [Comparación de valores de retorno y tipificación](#10-comparacion-de-valores-de-retorno-y-tipificacion)

* [Código de depuración](#11-codigo-de-depuracion)

* [Espacio en blanco](#12-espacio-en-blanco)

* [Saltos de línea](#13-saltos-de-linea)

* [Espaciado de corchete y paréntesis](#14-espaciado-de-corchete-y-parentesis)

* [Métodos privados y variables](#15-metodos-y-variables-privados)

* [Etiquetas cortas abiertas](#16-etiquetas-cortas-abiertas)

* [Una declaración por línea](#17-una-declaracion-por-linea)

* [Instrumentos de cadena](#18-instrumentos-de-cadena)

* [Consultas SQL](#19-consultas-sql)



1. Formato de archivo

---------------------



Los archivos deben guardarse con codificación Unicode (UTF-8).

Se deben utilizar terminaciones de línea Unix (LF).



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



2. Etiqueta de cierre de PHP

----------------------------



Se debe colocar la etiqueta de cierre de PHP en un documento PHP `?>`.

Es opcional para el analizador de PHP. Sin embargo, si se utiliza, cualquier espacio en blanco que siga a la etiqueta de cierre, ya sea introducido por el desarrollador, el usuario o una aplicación FTP, puede provocar salidas no deseadas o errores de PHP.



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##3. Nombre de archivo



Los archivos de clase deben ser nombrados de manera similar a Ucfirst, mientras que cualquier otro nombre de archivo (configuraciones, vistas, scripts genéricos, etc.) debe estar en minúsculas.



###Ejemplo:



```

Somelibrary.php

Some_library.php



Applicationconfig.php

application_config.php

```



Además, los nombres de archivo de clase deben coincidir con el nombre de la propia clase. Por ejemplo, si tiene una clase llamada Myclass, su nombre de archivo debe ser **`Myclass.php`**



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##4. Nombre de clases y métodos



Los nombres de las clases siempre deben comenzar con una letra mayúscula (Ucfirst). Las palabras múltiples deben ser separadas con un guión bajo (underscore), y no CamelCased.



###Ejemplo:



```javascript

class Superclass

class Super_class{

	public function_construct(){



	}

}

```



Los métodos de clase deben ser enteramente en minúsculas y nombrados para indicar claramente su función, preferiblemente incluyendo un verbo. Trate de evitar los nombres excesivamente largos y detallados. Las palabras compuestas deben separarse con un guión bajo (underscore).



###Ejemplo:



```javascript

function get_file_properties() //descriptivo, separador de guion bajo y todas las letras minúsculas

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##5. Nombre de variables



Las directrices para el nombre de variables son muy similares a las utilizadas para los métodos de clase. Las variables deben contener sólo letras minúsculas, usar guión bajo (underscore) como separador y ser razonables al nombrarlas para indicar su propósito y contenido. Las variables muy cortas sólo se deben usar como iteradores en los bucles **`for()`**



###Ejemplo:



```javascript

for($j = 0; $j < 10; $j ++) 

$str

$buffer

$group_id

$last_city

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##6. Comentando



En general, el código debe ser comentado prolíficamente. El mismo debe estar en español. No hay un formato requerido para los comentarios, pero se recomienda lo siguiente.

Bloque de comentarios precedentes a clase, método y declaraciones de propiedad para que puedan ser recogidos por IDE:



```java

/ ** 

* Super Class 

* 

* @package Nombre del paquete 

* @subpackage Subpaquete 

* @category Categoría 

* @author Nombre del autor 

* @link http://example.com 

* / 

class Super_class  {



/ ** 

* Codifica cadena para usar en XML 

* 

* @param string $str Cadena de entrada 

* @return string 

* / 

function  xml_encode($str)



/ ** 

* Datos para manipulación de clase 

* 

* @var array 

* / 

public $data = array();

```



Utilice comentarios de una línea dentro del código, dejando una línea en blanco entre los bloques de comentarios grandes y el código.



```js

// rompe la cadena por newlines 

$parts = explode("\n", $str);



// Un comentario más largo que necesita dar más detalles sobre lo que

// ocurre y por qué puede usar varios comentarios de una sola línea. Trate de

// mantener el ancho razonable, alrededor de 70 caracteres es el más fácil de leer. No dude en vincularse a recursos externos permanentes

// que pueden proporcionar mayor detalle:



$parts = $this->foo($parts);

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##7. Constantes



Las constantes siguen las mismas pautas que las variables, excepto que las constantes siempre deben estar totalmente en mayúsculas, es decir SLASH, LD, RD, PATH_CACHE, etc.



###Ejemplo:



```

MY_CONSTANT 

NEWLINE 

SUPER_CLASS_VERSION 

$str = str_replace(LD.'Foo'.RD, "bar", $str);

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##8. TRUE, FALSE y NULL



Las palabras **true**, **false** y **null**, se colocarán en minúsculas.



###Ejemplo:



```

if($foo == true) 

$bar = false; 

function foo($bar = null)

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##9. Operadores logicos



Se debe usar **`&&`** preferiblemente sobre **`AND`** y usar **`||`** de preferencia sobre **`OR`**, y dejar un espacio antes y después de usarlo.



###Ejemplo:



```

if($foo || $bar)

if($foo && $bar)

if( ! $foo)

if( ! is_array($foo))

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##10. Comparación de valores de retorno y tipificación



Para devolver y comparar las variables, se debe colocar **`===`** y **`!==`** según sea necesario.



###Ejemplos:



```

if(strpos($str, 'foo') === FALSE)



function build_string($str = "") 

{ 

        if($str === "") 

        {



        } 

}

```



La tipografía tiene un efecto ligeramente diferente que puede ser deseable. Cuando se emite una variable como una cadena, por ejemplo, las variables NULL y booleana FALSE se convierten en cadenas vacías, "0" (y otros números) se convierten en cadenas de dígitos y el booleano TRUE se convierte en "1":



```

$str = (string) $str;  // emite $str como una cadena

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##11. Código de depuración



No deje el código de depuración en sus envíos, incluso cuando se comenta. Cosas como **`var_dump ()`**, **`print_r ()`**, **`die () / exit ()`** no deben incluirse en su código a menos que sirva a un propósito específico que no sea la depuración.



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##12. Espacio en blanco



Utilice tabulaciones para espacios en blanco en su código.



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##13. Saltos de línea



Los archivos se deben guardar con los saltos de línea de Unix (line feed abreviado LF).



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##14. Espaciado de Corchete y Paréntesis



En general, los paréntesis y los corchetes no deben utilizar espacios adicionales. La excepción es que un espacio siempre debe seguir las estructuras de control de PHP que aceptan argumentos con paréntesis (**`declare`**, **`do-while`**, **`elseif`**, **`for`**, **`foreach`**, **`if`**, **`switch`**, **`while`**), para ayudar a distinguirlos de las funciones y aumentar la legibilidad.



###Ejemplos:



```

$arr[$foo] = 'foo';  // no hay espacios alrededor de claves de matriz

function foo($bar)  // no hay espacios alrededor de paréntesis en declaraciones de función 

{



}

foreach ($query->result() as $row)  // espacio simple después de estructuras de control de PHP, pero no en paréntesis interior

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##15. Métodos y variables privados



Métodos y las variables que sólo se acceden internamente, como la utilidad y las funciones de ayuda que sus métodos públicos utilizan para la abstracción de código, debe ser prefijado con un guión bajo (underscore).



```

public function convert_text() 

private function  _convert_text()

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##16. Etiquetas cortas abiertas



Siempre utilice las etiquetas de apertura completas de PHP, en caso de que un servidor no tenga short_open_tag habilitado.



###Ejemplo:



```

<?php echo $foo; ?>

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##17. Una declaración por línea



Nunca combine declaraciones en una línea.



###Ejemplo:



```

$foo = 'this'; 

$bar = 'that'; 

$bat = str_replace($foo, $bar, $bag);

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##18. Instrumentos de cadena



Utilice siempre cadenas de comillas simples a menos que necesite las variables analizadas, y en los casos en los que necesite las variables analizadas, utilice llaves para evitar el análisis de tokens codiciosos. También puede utilizar cadenas de comillas dobles si la cadena contiene comillas simples, por lo que no tiene que utilizar caracteres de escape.



###Ejemplo:



```

'Mi cadena' 

"Mi cadena {$foo}" 

"SELECCIONE foo de la barra WHERE baz = 'bag'"

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)



##19. Consultas SQL



Las palabras clave SQL siempre están en mayúsculas: SELECT, INSERT, UPDATE, WHERE, AS, JOIN, ON, IN, etc.



Divida las consultas largas en varias líneas para obtener legibilidad, preferiblemente para cada cláusula.



###Ejemplo:



```

$query = $this->db->query("SELECT foo, bar, baz, foofoo, foobar AS raboof, foobaz FROM exp_pre_email_addresses WHERE foo != 'oof' AND baz != 'zab' ORDER BY foobaz LIMIT 5, 100");

```



[Volver](#estandar-para-la-codificacion-php-en-desarrollo-web)

