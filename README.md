# A continucion encontraras la documentacion sobre la el proceso para realizar el Desafio #2 el cual nos presenta el siguiente escenario.

Escenario:
Nuestra organización nos encomendó la tarea de realizar una prueba de concepto para crear un CI/CD de nodejs, necesitan entender cómo se debe realizar el proceso de build para una  API hecha en nodejs.
Por este motivo, nos entregaron una aplicación de ejemplo hecha en esta tecnología, este proyecto cuenta con una prueba integrada hecha en la herramienta Jest propia de este  framework de desarrollo. El referente de desarrollo, nos encargó realizar la configuración de un webhook que permita  hacer un build automático cada vez que se produzca un push o un pull request, esto puede  ayudar para automatizar la ejecución del job para este CI/CD.

##### INSTALACION Y CONFIGURACION DE NGROK  ######
Se utilizará la tool NGROK de modo gratuito los cual nos permitirá exponer nuestro entorno local a la web es decir nuestro servicio de Jenkins.
Los descargaremos del sitio oficial https://ngrok.com para la distro de Linux que estemos utilizando. Siguiendo los siguientes pasos:
En nuestra terminal de Linux escribimos el comando sudo wget mas la dirección web  para descargar nuestra versión a instalar:

sudo wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz

Una vez descargada  descomprimos el fichero descargado con el siguiente comando.

sudo tar –zxvf ngrok-v3-stable-linux-amd64.tgz

para comenzar a utilizar la herramienta de NGROK debemos autenticarnos con un token de la siguiente manera:

ngrok config add-authtoken 2f3W8g00lk7BaadfTrgLI34Supu_22gCDysWM7XKLanyFGSyo
(el token nos lo proporciona una vez que estemos logueados en el sitio web)

Para verificar que la herramienta este corriendo en nuestra consola escribirmos el siguiente comando ./ngrok http 8080  lo cual nos dará los datos de esta forma:

Session Status                online                                                                                                
Account                       Josue Reyes (Plan: Free)                                                                              
Version                       3.8.0                                                                                                 
Region                        South America (sa)                                                                                    
Latency                       46ms                                                                                                  
# Web Interface                 http://127.0.0.1:4040                                                                                 
# Forwarding                    https://a1d3-186-22-245-136.ngrok-free.app -> http://localhost:8080   

Siguiente paso Realizamos un Fork del repositorio  Main este con el proposito de trabajar de manera separada sin afectar el repositorio Principal.

### CONFIGURACION DEL GITHUB WEBHOOK ##

Una vez realizado el Fork del repositorio deseado realizamos los siguientes pasos:
En la parte superior vamos a Settings o Configuraciones
En el menu de la izquierda de nuestra pantalla nos dirifmos a Webhook le damos clic
buscamos el boton  Add Webhook y en la ventana  agregar: el Forwarding proporcionado por el servicio de NGROK https://a1d3-186-22-245-136.ngrok-free.app/github-webhook/ ademas  seleccionar las opcions Pull request y Pusshes este seleccionadas. Una vez realizado estos pasos nuestro servicio debe estar activo.

###  CONFIGURACION DE UN JOB EN JENKINS

Crear un nuevo Job Pipeline  en configuracion  de Build Triggers  seleccionar  GitHub hook trigger for GITScm polling para que realice automaticamente la actualizcion  cuando realicemos un COMMIT a nuestro jenkinsfile. 

La siguiente configuración es: 

Pipeline Definition

Pipeline script from SCM
SCM

Git

Repositories

Repository URL: https://github.com/josuereydev/nodejs-helloworld-api.git
Credentials

Aplicamos y Guardamos los cambios y nuestro Pipeline se construirá de manera automatica cuando realicemos cambios en el codigo desde algun editor.



 