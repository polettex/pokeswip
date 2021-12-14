Estilos y lógica que se utilizarán en el desarrollo de la app:
- CSS - Horizontal Scroll Menu
- Google font
- Flex
- onclic pokeball
- `galleryRandom()` randomizar imágenes en la galería

**Para cada ejercicio es necesario utilizar un documento html correctamente ligado a una hoja js.**

**Ejercicio 1.** Utilizar `window.onload = function() { //code...}` para mostrar un alert con el mensaje "hello world".

> Enlace de referencia:
>  - https://developer.mozilla.org/es/docs/Web/API/GlobalEventHandlers/onload

**Ejercicio 2.** Crear una función `saludo` tal que, dependiendo de la hora actual, realize los siguientes cambios en el documento html:

  - obtenga un elemento h1 con id "saludo" y muestre dentro de él la frase ¡Buenos días! o ¡Buenas noches! y
  - cambie el color de fondo del documento html (obtener el elemento body) a rgb(238, 107, 47) (de día) y #3E3730 (de noche).

Definiremos día y noche si se cumple la siguiente condición de hora:
```js
if(hora < 7 || hora > 17){ // podéis cambiar el número de hora (7, 17, etc) en el condicional del if para realizar pruebas
    //noche
}else{
    //día
}
```
Para comprobar el funcionamiento de la función creada se ha de llamar a esta utilizando:
```js
window.onload = function() {
    saludo();
}
```
> Enlaces de referencias:
>   - https://www.w3schools.com/js/js_dates.asp
>   - https://www.w3schools.com/js/js_date_methods.asp
>   - https://www.w3schools.com/jsref/prop_style_backgroundcolor.asp

**Ejercicio 3.** Crear una función `getListRandom` que admita tres variables `(n, min, max)` y **retorne** una lista (array) de números aleatorios no repetidos. La función llamará a la función `getRndInteger(min, max)` para obtener números aleatorios entre el mínimo y el máximo indicados (incluidos ambos) y utilizará estos números para crear la lista que ha de devolver.
```JS
// This JavaScript function always returns a random number between min and max (both included):
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```

Para comprobar el funcionamiento de la función creada se ha de llamar a esta utilizando:
```js
window.onload = function() {
    console.log(getListRandom(10, 1, 10));
}
// ejemplo de console.log devuelto:
[10, 1, 7, 8, 9, 3, 6, 5, 4, 2]
// ejemplo de console.log devuelto:
[5, 1, 9, 7, 4, 10, 2, 8, 6, 3]
// ejemplo de console.log devuelto:
[2, 10, 9, 6, 4, 1, 3, 8, 5, 7]
```
> Enlace de referencia:
>   - https://www.w3schools.com/js/js_random.asp

**Ejercicio 4.** Crear una función `buttonOpacity` que realize los siguientes cambios en el documento html:

  - obtenga una imagen del documento y cambie su opacidad (propiedad css `opacity`) a `0.5` o `1`.

La función ha de implementar un condicional que permita comprobar si la opacidad es igual a `0.5`, si lo es cambiará la opacidad a `1`, en cualquier otro caso la cambiará a `0.5`.

Para comprobar el funcionamiento de la función creada se ha de utilizar el evento `onclic` en una imagen del documento html (p. ej. la imagen de la pokeball).

> Enlace de referencia:
>   - https://www.w3schools.com/jsref/prop_style_opacity.asp

**Ejercicio 5.** Asociar el evento `onclic` a la imagen de la pokeball relacionada al front-end hecho en clase:

![pokeproject](https://github.com/dannylarrea/enunciados/blob/main/resources/pokeprojectJS.png)

de manera que al clicar la imagen se llame a la función `listRandom`:

```js
function listRandom() {
    buttonOpacity();
    galleryRandom();
}
```
  - la función `buttonOpacity` realizará la lógica del ejercicio 4. No retornará nada, únicamente realizará cambios en el documento html
  - la función `galleryRandom` definirá variables `min`, `max`, `images` y `listRnd`, donde:
    - si la imagen más pequeña que se utiliza es **IMG_1.PNG** => `min` valdrá 1
    - si la imagen más grande que se utiliza es **IMG_10.PNG** => `max` valdrá 10
    - la variable `images` será una lista que contendrá todas las imágenes asociadas a la galería excepto la pokeball (podéis utilizar los métodos `getElementsByClassName("example")`, `getElementsByTagName("img")`, etc. para recuperar las imágenes del documento html)
    - la variable `listRnd` será una lista (array) de números aleatorios no repetidos: `let listRnd = getListRandom(n, min, max)` (ejercicio 3).
  y, por cada elemento imagen recuperado, se asignará una nueva ruta (`src`) con el método `setAttribute`:
    ```js
    //Pseudocódigo de ejemplo
    function galleryRandom() {
        /* Definir variables 
        min, max, images, listRnd
        */


        for (...) {
            images[i].setAttribute("src", "./img/IMG_" + listRnd[i] + ".PNG");
        }
    }
    ```
> Enlaces de referencia:
>   - https://www.w3schools.com/jsref/met_document_getelementsbyclassname.asp
>   - https://www.w3schools.com/jsref/met_document_getelementsbytagname.asp
>   - https://www.w3schools.com/jsref/met_element_setattribute.asp
