# Práctica de Git/Github - Master DEVF G7

Ejercicio para aprender a trabajar con repositorios de git y ramas.

Los pull requests son bienvenidos. Puedes clonar este repositorio, crear tu propia rama y agregar un archivo con tu nombre y un saludo desde consola o cualquier cosa que tú quieras. :)


## Contribuir

1. Primero tenemos que tener una copia de este repositorio en nuestra computadora de manera local. Para esto, podemos utilizar el comando ```git clone```:

```bash
git clone https://github.com/pedroagont/git-prueba-g7.git
```

2. Una vez que el repositorio fue clonado en nuestra computadora, tenemos que cambiarnos a la carpeta del proyecto recién creada por git con ```cd```:

```bash
cd git-prueba-g7
```

3. Para verificar que ya nos encontramos en el repositorio git podemos usar el comando ```ls -a``` para mostrar todos los elementos que se encuentran en ese directorio y debe haber una carpeta con el nombre ```.git``` junto al resto de archivos que hay:

```bash
ls -a
.               .git            index.html
..              README.md       sensei-pedro.js
```

*La bandera "-a" significa "all" para mostrar todo lo que se encuentre en el directorio actual, incluyendo los archivos ocultos.*

4. Ya que nos encontramos en el repositorio de git, podemos empezar a trabajar. Sin embargo, para evitar el peligro de intervenir el desarrollo actual, vamos a crear una nueva rama que incluirá una copia exacta del proyecto pero separada de la rama principal. Para crear una nueva rama podemos usar el comando ```git branch```:

```bash
git branch mi-rama-ejemplo
```

5. Ahora cámbiate a tu nueva rama con ```git checkout```:

```bash
git checkout mi-rama-ejemplo
```

*(También es posible realizar los dos pasos anteriores en un solo comando utilizando ```git checkout -b mi-rama-ejemplo```)*

6. Ya que nos encontramos en nuestra nueva rama, podemos empezar a trabajar sin problema. Crea un nuevo archivo con tu nombre, por ejemplo **juana-perez.js** que contenga algo sencillo como lo siguiente:

```javascript
console.log('Hola soy Juana Pérez! 🥳');
```

7. Una vez que ya hicimos los cambios en los archivos de nuestro *directorio de trabajo*, tenemos que decirle al repositorio de git que queremos que los agregue a nuestro *directorio de producción*. Podemos lograr esto con el comando ```git add``` y el nombre del o los archivos modificados que queremos que agregue:

```bash
git add juan-perez.js
```

*Si usamos ```git add .``` o ```git add *``` podemos agregar todos los archivos que se hayan modificado del directorio en donde nos encontramos*

8. ¡Ya casi lo logramos! Estos cambios ya fueron agregados al *directorio de producción* pero hace falta indicarle *qué* significan. Para hacer esto usamos el comando ```git commit -m``` seguido de un mensaje entre comillas que indicará el motivo de nuestros cambios:

```bash
git commit -m "Agregué el archivo con el mensaje de Juana Pérez!"
```

9. Estos cambios ya están listos, sin embargo, por ahora sólo se encuentran en el repositorio de nuestra computadora de manera local. Para *subir* al repositorio remoto nuestros cambios utilizamos el comando ```git push origin``` y el nombre de la rama que queremos enviar:

```bash
git push origin mi-rama-ejemplo
```

*El comando también funciona si sólo escribimos ```git push```. Esto envía todos los cambios que encuentre en el directorio de producción, no sólo de la rama actual sino de todas.*

10. Abre la [liga](https://github.com/pedroagont/git-prueba-g7) del repositorio en GitHub y crea un nuevo *Pull Request* desde ```mi-nueva-rama``` a la rama ```master``` para que se *jalen* los cambios.

```bash
(master) <- (mi-nueva-rama)
```

### ¡Listo! Si llegaste hasta este punto es porque lograste contribuir adecuadamente a un repositorio GIT a través de GitHub

#### Para más información puedes consultar cualquiera de los siguientes links
- [Guía sencilla de GIT en Español](https://rogerdudler.github.io/git-guide/index.es.html)
- [Juego para aprender GIT](https://learngitbranching.js.org)
- [Herramienta para visualizar GIT](http://git-school.github.io/visualizing-git/)

## Licencia
[MIT](https://choosealicense.com/licenses/mit/)
