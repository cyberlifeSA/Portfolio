- --
- Tags: #cyberdefenders #maldoc101_lab #oledump #olevba
- --
En este documento hay macros que contienen múltiples flujos. Proporciona el número del más alto.

![[../../../../Fotos/Pasted image 20260706161356.png]]

El comando permite identificar que el archivo corresponde a un **Documento Compuesto V2 (Compound Document V2)**, un formato basado en **CFB (Compound File Binary)**. Además, proporciona información relevante, como el sistema operativo con el que fue creado el documento, la fecha y hora de la última modificación y la versión de la aplicación utilizada. Estos metadatos pueden ser útiles para determinar el origen del archivo y detectar posibles modificaciones.

A continuación, se utiliza la herramienta **oledump** para examinar los flujos de datos contenidos en el archivo CFB. Esta utilidad, desarrollada en Python, permite extraer e inspeccionar los flujos incrustados en documentos de Microsoft Office. Al ejecutar el comando `python oledump.py sample.bin`, se obtiene un listado con todos los flujos disponibles, indicando su índice, tamaño y tipo. Aquellos identificados con la letra **M** corresponden a macros VBA, las cuales requieren un análisis detallado, ya que frecuentemente son utilizadas para incorporar código malicioso.

**M (mayúscula):** Este indicador señala que el flujo contiene una macro VBA con atributos y código comprimido. Para examinar su comportamiento es necesario descomprimir dicho código, ya que es allí donde se encuentra la lógica de la macro. La presencia de este indicador suele ser un aspecto relevante durante el análisis, debido a que las macros comprimidas pueden ocultar código malicioso.

**m (minúscula):** Este indicador identifica un flujo que incluye únicamente los atributos de una macro, pero no contiene código VBA ejecutable. En estos casos, el flujo almacena información descriptiva o de configuración relacionada con la macro, sin incorporar instrucciones que puedan ejecutarse.

En este contexto, los **atributos** corresponden a metadatos asociados a una macro VBA. Estos pueden incluir información como el nombre de la macro, su descripción y otras propiedades utilizadas para su identificación o configuración. Aunque forman parte de la estructura del proyecto VBA, no contienen el código encargado de ejecutar acciones o realizar operaciones.

![[../../../../Fotos/Pasted image 20260706162208.png]]

**Respuesta:** 16

¿Qué evento se utiliza para iniciar la ejecución de los macros?

**`olevba`** es una herramienta de la suite **oletools** que se utiliza para **extraer y analizar macros VBA** contenidas en documentos de Microsoft Office. Es muy utilizada en análisis de malware porque muchas campañas maliciosas emplean documentos con macros para ejecutar código en el equipo de la víctima.

![[../../../../Fotos/Pasted image 20260706163901.png]]

![[../../../../Fotos/Pasted image 20260706163816.png]]

**Respuesta:** Document_open

¿Qué familia de malware intentaba eliminar este maldoc?

![[../../../../Fotos/Pasted image 20260706164820.png]]

![[../../../../Fotos/Pasted image 20260706172027.png]]

**Respuesta:** emotet

¿Qué flujo es responsable del almacenamiento de la cadena codificada en base64?

![[../../../../Fotos/Pasted image 20260706172239.png]]

![[../../../../Fotos/Pasted image 20260706172558.png]]

El flujo **Macros/roubhaol/i09/o** llama la atención debido a su tamaño relativamente grande, lo que puede indicar la presencia de información ofuscada o codificada que requiere un análisis más detallado.

![[../../../../Fotos/Pasted image 20260706174809.png]]

**Respuesta:** 34

Este documento contiene un formulario de usuario. Proporciona el nombre.

![[../../../../Fotos/Pasted image 20260706175520.png]]

**Respuesta:** roubhaol

Este documento contiene una cadena codificada en Base64 ofuscada; ¿Qué valor se usa para rellenar (o ofuscar) esta cadena?

![[../../../../Fotos/Pasted image 20260706174705.png]]

![[../../../../Fotos/Pasted image 20260706174637.png]]

![[../../../../Fotos/Pasted image 20260706180705.png]]

![[../../../../Fotos/Pasted image 20260706180955.png]]

**Respuesta:**  `2342772g3&*gs7712ffvs626fq`

¿Qué programa ejecuta la cadena codificada en Base64?

![[../../../../Fotos/Pasted image 20260706184700.png]]

![[../../../../Fotos/Pasted image 20260706184730.png]]

**Respuesta:** powershell

¿Qué clase WMI se utiliza para crear el proceso de lanzamiento del troyano?

![[../../../../Fotos/Pasted image 20260706185120.png]]

**Respuesta:** Win32_Process

Se contactó con varios dominios para descargar un troyano. Proporciona el primer FQDN según la pista proporcionada.

![[../../../../Fotos/Pasted image 20260706185533.png]]

**Respuesta:** haoqunkong.com