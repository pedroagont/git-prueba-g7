# Práctica de Git/GitHub - Master DEVF G7

Práctica para aprender a trabajar con repositorios de git y ramas.

Los pull requests son bienvenidos. Puedes clonar este repositorio, crear tu propia rama y agregar un archivo con tu nombre que incluya un saludo desde consola o cualquier cosa que tú desees, ¡sé creativo! :)

## Antes de comenzar

### Instalación y terminal de git

Descarga la versión de git para el sistema operativo de tu computadora desde el siguiente link: [https://git-scm.com/downloads](https://git-scm.com/downloads)

#### Usuarios Windows:

Inicia el instalador que descargaste y acepta las opciones por default para continuar. Una vez instalado, tendrás en tu computadora tres nuevos programas:
- **git bash**: Terminal basada en ```bash``` y sistemas UNIX (Mac y Linx).
- **git CMD**: Terminal basada en ```CMD```, la línea de comandos de Windows.
- **git GUI**: Graphical User Interface, es decir, interfaz gráfica para no interactuar desde la terminal.

Para proceder con esta práctica es necesario que abras la terminal de **git bash**.

#### Usuarios Mac:

Para ti que tienes Mac te sugiero que descargues el instalador binario y lo inicies aceptando las opciones por default para continuar. Si no te permite abrir el instalador por riesgos de seguridad, no te preocupes, git no es un virus. En ocasiones nuestra computadora nos protege de desarrolladores de software externos a Apple. Si es tu caso, es necesario que vayas a tus **Preferencias de Sistema** y en el panel de **Seguridad y Privacidad** aceptes la instalación de git con tu usuario y contraseña.

Una vez instalado sólo necesitas dirigirte a tus **Aplicaciones** y en la carpeta de **Utilidades** y abrir el programa **Terminal** para comenzar a utilizar git.

#### Usuarios Linux

Desde tus aplicaciones abre tu **Terminal** para proceder con la práctica. *Seguramente ya sabes hacer esto.*

### Configuración de git

Recuerda que es necesario tener configurado  git en nuestra computadora para que al momento de hacer un commit, ésta sepa quién lo hizo. Esto lo podemos lograr con el comando ```git config``` e indicando nuestro nombre y correo. Para evitar hacer esta configuración en cada repositorio con el que trabajemos en nuestra computadora, podemos agregar la bandera ```--global``` y de esa manera quedará configurado por default:

```bash
git config --global user.name "Pedro A. González"
git config --global user.email "pgonzalez@post.com"
```

### Permisos de colaborador

De igual forma recuerda haber aceptado los permisos para colaborar en este repositorio desde la siguiente liga: [https://github.com/pedroagont/git-prueba-g7/invitations](https://github.com/pedroagont/git-prueba-g7/invitations)

*Si enviaste tu usuario de GitHub durante la clase, ya deberías tener invitación. Si no es así, envíame un mensaje por Slack o un correo a pgonzalez@post.com para que te agregue como colaborador.*

*Si no tienes permisos pero quieres realizar esta práctica puedes crear un "Fork" de este proyecto y en el paso 1 clonar tu propio repositorio para proceder*

## Contribuir

1. Primero tenemos que tener una copia de este proyecto en nuestra computadora de manera local. Para esto, podemos utilizar el comando ```git clone``` y la ruta del repositorio que queremos clonar. Para el caso de GitHub, todos los repositorios tienen un botón verde que dice "Code" de donde podemos copiar la liga que necesitamos:

```bash
git clone https://github.com/pedroagont/git-prueba-g7.git
```

2. Una vez que el repositorio fue clonado en nuestra computadora, tenemos que cambiarnos a la carpeta del proyecto recién creada por git con ```cd``` y la ubicación a la que queremos acceder:

```bash
cd git-prueba-g7
```

3. En este momento, ya nos encontramos dentro del repositorio git y lo podemos apreciar dado que nuestra consola seguramente muestra entre paréntesis la palabra ```(master)```, indicando el nombre de la rama de git en la que estamos trabajando. De cualquier forma, para confirmar esto, podemos usar el comando ```git status```, el cual nos deberá indicar el directorio de trabajo de la rama en donde estamos:

```bash
git status
On branch master
Your branch is up to date with 'origin/master'.
nothing to commit, working tree clean
```

Otra forma de verificar que nos encontramos en un repositorio git es con el comando ```ls -a``` para mostrar todos los elementos que hay en la ruta donde estamos y debe haber una carpeta oculta con el nombre ```.git``` junto al resto de archivos y directorios:

```bash
ls -a
.               .git            index.html
..              README.md       sensei-pedro.js
```

Si ves esta carpeta significa que vamos bien. OJO: NO TE TIENES QUE METER A ESTA CARPETA, sólo verificamos que exista para confirmar que estamos en un repositorio git.

*En el comando ```ls -a```, la bandera ```-a``` significa "all" de "todos" en Inglés para mostrar todo lo que se encuentre en el directorio actual, incluyendo los archivos y directorios ocultos, aquellos que normalmente empiezan con un punto "." como la carpeta ```.git```.*

4. Ya que nos encontramos en el repositorio de git, podemos empezar a trabajar. Sin embargo, para no intervenir erróneamente el desarrollo de la rama principal, vamos a crear una nueva. Esta nueva rama incluirá una copia exacta del proyecto pero por separado, en donde podremos trabajar todos nuestros cambios sin riesgo de romper algo en la rama principal. Para crear una nueva rama podemos usar el comando ```git branch``` seguido del nombre de la nueva rama:

```bash
git branch mi-rama-ejemplo
```

5. Listo, tu rama ha sido creada, pero aún seguimos ubicados en la rama ```(master)```. Para continuar tenemos que decirle a git que cambie nuestro directorio de trabajo al de la nueva rama con el uso de ```git checkout``` y el nombre de la rama al que queremos cambiarnos:

```bash
git checkout mi-rama-ejemplo
```

Una vez ubicados en tu rama es posible que veas en tu terminal la palabra ```(mi-rama-ejemplo)```. En cualquier caso, puedes confirmarlo con el comando ```git status```:

```bash
git status
On branch mi-rama-ejemplo
nothing to commit, working tree clean
```

*(También es posible realizar los pasos 4 y 5 en un solo comando utilizando ```git checkout -b mi-rama-ejemplo```*

6. Ya que nos encontramos en nuestra nueva rama, podemos empezar a trabajar sin problema. Crea un nuevo archivo con tu nombre, por ejemplo **juana-perez.js** que contenga algo sencillo como lo siguiente:

```javascript
console.log('Hola soy Juana Pérez! 🥳');
```

7. Una vez que ya hicimos y salvamos los cambios en los archivos de nuestro *directorio de trabajo*, tenemos que decirle al repositorio de git que queremos que los agregue a nuestro *directorio de producción*. Podemos lograr esto con el comando ```git add``` y el nombre de el o los archivos modificados que queremos agregar:

```bash
git add juan-perez.js
```

*Si usamos ```git add .``` o ```git add *``` podemos agregar todos los archivos que se hayan modificado del directorio en donde nos encontramos*

8. ¡Ya casi lo logramos! Estos cambios ya fueron agregados al *directorio de producción* pero hace falta indicarle *qué* significan y *quién* los hizo. Para hacer esto usamos el comando ```git commit -m``` seguido de un mensaje entre comillas que indicará el motivo de nuestros cambios:

```bash
git commit -m "Agregué el archivo con el mensaje de Juana Pérez!"
```

*Cuando creamos un commit no sólo indicamos la razón de nuestros cambios, también firmamos con nuestros datos de configuración quién los hizo. Si no seguiste adecuadamente las indicaciones de la sección "Configuración de git" es posible que no te permita continuar. Agrega tus datos con ```git config``` para resolver el problema como se indica en la sección mencionada.*

9. Estos cambios ya están listos, sin embargo, por ahora sólo se encuentran en la rama que creamos en el repositorio de nuestra computadora de manera local. Para *subir/empujar* al repositorio remoto nuestros cambios utilizamos el comando ```git push origin``` y el nombre de la rama que queremos enviar:

```bash
git push origin mi-rama-ejemplo
```

Como estamos tratando de subir los cambios a un repositorio que, en este caso, se encuentra ubicado en GitHub, se abrirá una ventana donde se nos pedirá iniciar sesión en la plataforma y se validará que tengamos acceso como colaborador.

*Una vez que la rama ya existe en el repositorio remoto, la instrucción también funciona si sólo escribimos ```git push```. Este comando envía todos los cambios que encuentre en el directorio de producción, no sólo de la rama actual sino de todas las demás que hayamos modificado en nuestra computadora de manera local.*

10. Abre la [liga](https://github.com/pedroagont/git-prueba-g7) del repositorio en GitHub desde tu navegador y ubícate en tu rama. Una vez dentro, haz click en el botón de *Compare & Pull Request* para solicitar que se *jalen* los cambios de tu rama a la rama principal. Asegúrate que vaya desde ```mi-rama-ejemplo``` a la rama ```master``` y dale al botón verde para continuar:

```bash
(master) <- (mi-rama-ejemplo)
```

### ¡Listo! Si llegaste hasta este punto es porque lograste contribuir adecuadamente a un repositorio git a través de GitHub. Es aquí donde normalmente el líder del proyecto revisa los cambios realizados desde tu rama y decide si fusionarlos con la rama principal o solicitar alguna otra modificación.

#### Para más información puedes consultar cualquiera de los siguientes links
- [Guía sencilla de GIT en Español](https://rogerdudler.github.io/git-guide/index.es.html)
- [Juego para aprender GIT](https://learngitbranching.js.org)
- [Herramienta para visualizar GIT](http://git-school.github.io/visualizing-git/)

## Licencia
[MIT](https://choosealicense.com/licenses/mit/)
