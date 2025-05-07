### Di�logo de Configuraci�n del An�lisis Est�tico

Este cuadro de dialogo permite configurar diferentes opciones del an�lisis est�tico (argumentos para cppcheck) relacionadas al tipo errores que el an�lisis busca y los errores particulares o archivos fuentes que debe omitir. Se accede a �l desde el �tem *Configurar...* del submen� *An�lisis Est�tico* del men� *Herramientas*. Para una mejor descripci�n de este tipo de an�lisis y c�mo se utiliza en *ZinjaI* vea [An�lisis Est�tico](cppcheck.html).


El cuadro de di�logo muestra dos pesta�as. La pesta�a *General* permite definir opciones varias que se describen a continuaci�n:

*  **Copiar configuraci�n de las opciones del proyecto**: Puede haber bloques de c�digo que se compilen condicionalmente (#ifdef...). En estos casos, se puede suministrar a cppcheck un conjunto de constantes de preprocesador ya definidas para determinar si analizar o no estos bloques, o esperar que analice todas las posibles combinaciones. Para lo primero, se puede tomar la lista de constantes definidas en las [Opciones de Compilaci�n y Ejecuci�n de Proyecto](project_config.html) (incluyendo las definidas en el campo espec�fico para macros y las definidas en el campo de argumentos adicionales para la compilaci�n), o especificar una lista diferente. Si elije suministrar una lista difernte (es decir, no copiar del perfil de compilaci�n) debe introducir la lista de constantes a definir en el campo *Configuraciones a verificar* y la lista de constantes a considerar como definidas en el campo *Configuraciones a saltear*. Si no hay constantes definidas (ya sea en la lista espec�fica, o en el perfil de compilaci�n si se elige copiar), CppCheck intentar� verificar todas las combinaciones, mientras no sean m�s que una cierta cantidad predefinida (12).

*  **Verificaciones adicionales**: Hay un conjunto de verificaciones b�sicas que CppCheck realiza siempre, y otros conjuntos de verificaciones adicionales que se pueden activar. Se deben listar en este campo el nombre de algunos de estos o la palabra "all" para activarlos a todos. Las opciones posibles son *style*, *performance*, *portability*, *information*, *unusedFunction* y *missingInclude*.

*  **Verificaciones espec�ficas de una plataforma**: Para que cppcheck considere los tipos de datos y tama�os espec�ficos de una plataforma, debe ingresarla en este campo. Las posibles opciones son: *unix32*, *unix64*, *win32A*, *win32W* y *win64*. La diferencia entre las dos versiones de win32 es que la primera utiliza codificaci�n ASCII mientras que la segunda UNICODE.

*  **Verificaciones espec�ficas de un est�ndar**: Habilita algunas verificaciones adicionales relacionadas espec�ficamente a un est�ndar. Las opciones v�lidas son *posix*, *c99* y *c++11*.

*  **Supresiones**: Las supresiones permiten omitir en la salida determinados errores o conjuntos de ellos. Para especificar una supressi�n puede especificar simplemente el id del error (omite todos los errores de ese tipo), el id y el nombre de un archivo separados por dos puntos (ej: uninitVars:mi_clase.cpp, omite todos los errores de ese tipo generados por el archivo mi_clase.cpp), o agregando al final un n�mero de l�nea tambi�n separado por dos puntos (ej: uninitVars:mi_clase.cpp:57, omite el error de id uninitVars de la linea 57 del archivo mi_clase.cpp). El id de un error se observa en *ZinjaI* en el panel de resultados; el id aparece entre par�ntesis luego del nombre del archivo donde se produce (m�s a�n, puede agregar el id a la lista de referencias directamente mediante click derecho sobre el mismo en dicho panel).

*  **Archivo con listas de supresiones**: Alternativamente, en lugar de ingresar las supresiones en el campo *Supresiones* se pueden ingresar en un archivo de texto y especificar en este campo el nombre de dicho archivo.

*  **Habilitar supresiones inline**: Las supresiones inline son supresiones que se especifican en el mismo c�digo fuente como comentarios. Para que cppcheck omita un error hay que agregar un comentario con el texto "cppcheck-suppress" y el id del error separado por un espacio (por ejemplo, "// cppcheck-suppress memleakOnRealloc") en la linea anterior a la que produce el error.

*  **Habilitar paralelizar ejecuci�n**: Esta opci�n habilita el uso del argumento "-j" al ejecutar cpp-check. Esto har� que cpp-check lanze m�s de un proceso, para analizar varios fuentes en simult�neo. La cantidad de procesos se tomar� de la cantidad definida para el proceso de compilaci�n en la pesta�a [Proyecto](preferences.html#programa_simple) del cuadro de [Preferencias](preferences.html).

*  **Guardar esta configuraci�n con el proyecto**: Si activa esta opci�n las configuraciones definidas en esta ventana se guardan dentro del archivo de proyecto. En caso contrarior, se pierden al cerrar el proyecto.


La pesta�a archivos permite seleccionar qu� archivos ser�n analizados y qu� archivos ser�n excluidos del an�lisis. La lista incluye s�lamente a los fuentes (.c/.cpp) y no a las cabeceras (.h/.hpp) porque �stas se procesan cuando se procesan los fuentes que las incluyen.
