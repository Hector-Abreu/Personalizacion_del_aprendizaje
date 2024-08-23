# Personalización del aprendizaje
## Video demostración
Enlace del [video](https://youtu.be/4gAV_l6qSyo) para ver el ejemplo de uso.

## Rand (RASA)
Puede descargar el contenido del proyecto a través del siguiente [enlace](https://drive.google.com/file/d/1v6T9ynrRiffLZ3BMolsSk80TOXN_0YsN/view?usp=sharing).

### Requisitos previos
Para el poder utilizar el asistente, es necesario tener [Python 3.10.6](https://www.python.org/downloads/release/python-3106/) instalado.

Confirmar que ***pip*** está instalado para manejar paquetes de Python.
> [!NOTE]  
> Si no tiene acceso a las API KEYs de OpenAI, no podrá realizar peticiones con la custom action desarrollada para conectarse con OpenAI.

Si tiene acceso a una API KEY de OpenAI, con el siguiente comando podrá asignarla para su uso:
```sh
setx OPENAI_API_KEY "Your_KEY"
```
## Configuración del Entorno e instalación
Después de descargar y descomprimir la carpeta de nuestro asistente, seguiremos los siguientes pasos:

1. Situarnos en la carpeta **RAND**
2. Crear nuestro entorno virtual con el comando:
```python
py -3.10 -m venv venv
```
3. Activar nuestro entorno virtual con el comando:
```
.\venv\Scripts\activate
```
4. Instalar ***RASA***
```python
pip install rasa
```
5. Nos situamos en la carpeta ***RASA*** e instalamos *pipreqs* para crear un archivo que lista todas las bibliotecas instaladas en el entorno virtual.
```python
pip install pipreqs
```
6. Instalar los módulos utilizados.
 ```python
pip install -r .\requirements.txt
```
***NOTA:*** Puede ser que no instale todos los módulos o bibliotecas necesarios, como por ejemplo el SpeechRecognition, el cual se instalará aparte.
 ```python
pip install SpeechRecognition
```

## Puesta en marcha
> [!IMPORTANT]
> Esto debemos hacerlo en 2 terminales diferentes.

Para activar el venv, debemos situarnos en la carpeta *RAND* a través de un terminal y escribir los comandos:
```
.\venv\Scripts\activate
```
Para desactivarlos, bastará con escribir:
```
deactivate
```

Una vez activado el ***venv***, en ambos terminales nos situamos en la carpeta ***RASA*** y ejecutamos:
En el primer terminal, para las acciones de nuestro bot:
```
rasa run actions
```

En el segundo terminal, para poder iniciar el servidor ***RASA*** y cargar el modelo, habilitar la API HTTP y los controles de Acceso de Origen Cruzado (CORS):
```
rasa run -m models --enable-api --cors "*"
```

> [!CAUTION]
> Si surgen errores al intentar ejecutar los scripts, deberemos dar permiso a través de una consola de powershell.

El siguiente comando muestra el ***ExecutionPolicy*** actual, que nos dará como resultado ***Restricted*** en caso de error.
```powershell
Get-ExecutionPolicy
```

Ahora se mostrarán los comandos para permitir la ejecución de scripts en Windows con ***RemoteSigned*** y para volver a dejarlo como ***Restricted***.
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
Set-ExecutionPolicy Restricted -Scope CurrentUser
```

## Activar el servidor python 
En un tercer terminal se tendrá que iniciar un servidor web Python con el comando:
```python
py -m http.server 8000
```
Una vez tengamos los 3 terminales operativos, lo único que faltaría sería abrir el navegador web y escribir:
```
localhost:8000
```
En el cual se cargaría nuestro asistente y podríamos comenzar su uso.

> Héctor Abreu Acosta
>
> Trabajo de fin de Grado para la Universidad de La Laguna
> 
> Grado en Ingeniería Informática
> 
> Curso 2023-2024 
