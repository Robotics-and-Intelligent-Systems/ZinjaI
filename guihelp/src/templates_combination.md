### Combinaci�n de Plantillas

Esta funcionalidad permite fusionar o reemplazar los [perfiles](projects.html#config) de configuraci�n de un proyecto con los otro o de una plantilla. Est� pensada para actualizar proyectos creados a partir de plantillas cuando se actualizan las plantillas, y para generar combinaciones que utilicen configuraciones de m�s de una plantilla a la vez.

Para actualizar un proyecto, o combinarlo con otra plantilla, debe abrir el proyecto en cuesti�n y acceder a esta opci�n mediante el bot�n *Combinar/Actualizar Plantilla* de la pesta�a [M�s](project_general_config.html#mas) del cuadro de [Configuraci�n de Proyecto](project_general_config.html).

En primer lugar, *ZinjaI* le mostrar� la lista de plantillas de proyecto disponibles para que seleccione una. Tambi�n dispondr� de una opci�n adicional al final de la lista que le permitir� abrir un archivo *.zpr* de otro proyecto, para combinar as� los perfiles de dos proyectos existentes  en lugar de un proyecto y una plantilla. Una vez seleccionada la plantilla, o el segundo proyecto, aparecer� el cuadro de di�logo "Combinar Plantillas".

![](templates_combination.png)

En este cuadro, a la izquierda se presentan 3 columnas: perfiles del proyecto actual, acci�n a realizar, y perfiles del segundo proyecto. All� puede determinar para cada peril del proyecto actual, si desea combinarlo o reemplazarlo con un perfil del otro, o no modificarlo. La acci�n "combinar" suma los campos de ambos perfiles. Por ejemplo, en la lista de directorios adicionales para cabeceras, quedar�n concatenadas las listas de ambos proyectos. La opci�n reemplazar reemplaza el valor del perfil del proyecto actual con el del segundo proyecto (esto implica que se perder� el valor actual).

Por �ltimo, a la derecha del cuadro de di�logo se listan los campos de los perfiles y de la configuraci�n general que pueden combinarse, junto a casillas de verificaci�n para que puede filtrar (desactivando) los que desee que no se actualicen.
