<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# PrivateGPT: GPT local

## ¿Por qué?

- El uso de LLMs como ChatGPT, Claude y otros a través de la web trae consigo debates sobre la privacidad de los datos.
- Además, hacer uso de plugins de terceros que se apoyan en esas herramientas aumenta los actores que tienen acceso potencial a esos datos.

## ¿Qué?

- Se busca tener la capacidad de utilizar toda la potencia de un LLM sin necesidad de una conexión a internet, de modo privado, garantizando que los datos permanecen en el entorno de ejecución en ningún momento.

## ¿Para qué?

Sobretodo, por un tema de privacidad.

## ¿Cómo?

- [PrivateGPT](https://github.com/imartinez/privateGPT/tree/main)
- [LocalGPT](https://github.com/PromtEngineer/localGPT)
- [GPT4All](https://gpt4all.io/index.html) --> ***+sencillo!***

### PrivateGPT

- Lo he instalado sobre KUbuntu, se puede instalar sobre otros sistemas operativos, como Windows, Mac OS u otra distro de GNU/Linux. 
- El proceso de instalación en la página del proyecto, tiene pequeñas variaciones en función del sistema operativo, pero *grosso modo* consiste en: 

| | |
|-|-|
|Clonar el repo|
|[Descargar un motor de modelo de lenguage](https://gpt4all.io/index.html)|He usado el [recomendado](https://gpt4all.io/models/ggml-gpt4all-j-v1.3-groovy.bin).
|Instalar un conjunto de librerías (incluidas en el archivo **requirements.txt**)|```sudo pip3 install -r requirements.txt --break-system-packages```
|Retocar el archivo de configuración (**.env** a partir de example.env)|
|Colocar los archivos a trabajar en la carpeta **source_documents**|![](/documentos/imagenes/privateGPT_files.png)
|Alimentar al LLM mediante el comando **ingest.py**|![](/documentos/imagenes/privateGPT_ingest.py.png)
Ejecutar el modelo, utilizando **privateGPT.py**|![](/documentos/imagenes/privateGPT_query001.png)

#### Impresiones

|PROs|No PROs|
|-|-|
GPT en local|Aun es lento al procesar las consultas
Privacidad|Los documentos han de estar relacionados
Control de documentos|