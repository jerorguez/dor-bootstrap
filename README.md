# Bootstrap

<div style="display: flex; justify-content: center;">
    <img src="https://www.eniun.com/wp-content/uploads/Bootstrap-descargar-instalar.png" alt="Logo Bootstrap" />
</div>

##
<div style="text-align: right;">
    <p><i>Siomara N. Alonso Hernández</i></p>
    <p><i>Jerobel Rodríguez Niño</i></p>
</div>
<hr>

[TOC]


## Desarrollo teórico

1. Definición de Bootstrap: ¿qué es?:

    ***Bootstrap*** es comúnmente definido como un *framework* de desarrollo front-end que sigue una metodología de adaptabilidad a distintos dispositivos.
    Fue desarrollado por *Twitter* en 2010, y se le llamó inicialmente ***Twitter Blueprint***, pero un año después pasó a ser de código abierto y a ser conocido con el nombre con el que lo conocemos hoy día.
    Este *framework* combina elementos css con js con el fin de estilizar prácticamente cualquier elemento del HTML, y, como se comentó al principio, su idea principal es que el diseño sea siempre responsive.


2. Instalación de Bootstrap.
    
    Para usar *Bootstrap* únicamente hace falta enlazar sus archivos css y js a la cabecera de nuestra web, y esto se puede hacer de dos formas:
    * Descargando directamente los archivos .css y .js.
    ```html
    <link rel="stylesheet" href="./assets/css/bootstrap.min.css">
    ```
    * Enlazando con una CDN (Content Delivery Network).
    ```html
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    ```
    La primera es una buena opción cuando se trabaja en local y se quieren evitar problemas de conección, pero una desventaja es que añade peso innecesario a la carpeta del proyecto.
    La segunda es exactamente lo contrario, mientras que no añade peso al proyecto, te ves limitado a los posibles problemas de conectividad.


3. Componentes básicos para utilizar de Bootstrap (buttons, list group, etc.): explicación de los 3 que consideres más básicos en el diseño o que más utilizas.
    
    * **Dropdowns:** por lo general, cualquier menú de navegación tiene dropdowns, ya que es más ordenado mantener las distintas secciones agrupadas en una categoría.
    * **Stepper:** son útiles para ver el proceso de registro o de compra; si planeamos crear una web con opción a registro de usuarios (para comprar o un simple blog) o queremos hacer encuestas, es más visual ver el paso por el que se va en el proceso.
    * **Tooltips:** los tooltips son una forma cómoda de ofrecer información a un usuario, si en algún momento es necesario explicar algo y esa explicación sea mínima, un tooltip es una opción bastante cómoda de ofrecer esa info.


4. Formularios:

Bootstrap facilita la creación de formularios, así como la validación de estos. Un ejemplo de formulario podría ser:

```htmlembedded
<form>
  <!-- 2 column grid layout with text inputs for the first and last names -->
  <div class="row mb-4">
    <div class="col">
      <div class="form-outline">
        <input type="text" id="form3Example1" class="form-control" />
        <label class="form-label" for="form3Example1">First name</label>
      </div>
    </div>
    <div class="col">
      <div class="form-outline">
        <input type="text" id="form3Example2" class="form-control" />
        <label class="form-label" for="form3Example2">Last name</label>
      </div>
    </div>
  </div>

  <!-- Email input -->
  <div class="form-outline mb-4">
    <input type="email" id="form3Example3" class="form-control" />
    <label class="form-label" for="form3Example3">Email address</label>
  </div>

  <!-- Password input -->
  <div class="form-outline mb-4">
    <input type="password" id="form3Example4" class="form-control" />
    <label class="form-label" for="form3Example4">Password</label>
  </div>

  <!-- Checkbox -->
  <div class="form-check d-flex justify-content-center mb-4">
    <input class="form-check-input me-2" type="checkbox" value="" id="form2Example33" checked />
    <label class="form-check-label" for="form2Example33">
      Subscribe to our newsletter
    </label>
  </div>

  <!-- Submit button -->
  <button type="submit" class="btn btn-primary btn-block mb-4">Sign up</button>

  <!-- Register buttons -->
  <div class="text-center">
    <p>or sign up with:</p>
    <button type="button" class="btn btn-primary btn-floating mx-1">
      <i class="fab fa-facebook-f"></i>
    </button>

    <button type="button" class="btn btn-primary btn-floating mx-1">
      <i class="fab fa-google"></i>
    </button>

    <button type="button" class="btn btn-primary btn-floating mx-1">
      <i class="fab fa-twitter"></i>
    </button>

    <button type="button" class="btn btn-primary btn-floating mx-1">
      <i class="fab fa-github"></i>
    </button>
  </div>
</form>
```

El resultado sería:
![](https://i.imgur.com/BrBL1th.png)



Además, si queremos validar un formulario debemos tener en cuenta las siguientes clases:

- **needs-validation**: se añade en la misma etiqueta del `form`.
    - Cada input requerido debe venir con el atributo `required` para que la validación pueda hacer su trabajo, si no está, no se validará ese campo.
    - Además de lo anterior, junto a la clase `needs-validation` se añade un atributo `novalidate` que, junto con esta, solo son removidos si el formulario está correctamente validado (que no hay inputs vacíos, etc.).
- **valid-feedback**: esta clase se usa a modo de contenedor que muestra el mensaje si el input no es correcto.

Ejemplo de formulario puesto para validar:
```htmlembedded
<form class="row g-3 needs-validation" novalidate>
  <div class="col-md-4">
    <label for="validationCustom01" class="form-label">First name</label>
    <input type="text" class="form-control" id="validationCustom01" value="Mark" required>
    <div class="valid-feedback">
      Looks good!
    </div>
  </div>
  <div class="col-md-4">
    <label for="validationCustom02" class="form-label">Last name</label>
    <input type="text" class="form-control" id="validationCustom02" value="Otto" required>
    <div class="valid-feedback">
      Looks good!
    </div>
  </div>
  <div class="col-md-4">
    <label for="validationCustomUsername" class="form-label">Username</label>
    <div class="input-group has-validation">
      <span class="input-group-text" id="inputGroupPrepend">@</span>
      <input type="text" class="form-control" id="validationCustomUsername" aria-describedby="inputGroupPrepend" required>
      <div class="invalid-feedback">
        Please choose a username.
      </div>
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustom03" class="form-label">City</label>
    <input type="text" class="form-control" id="validationCustom03" required>
    <div class="invalid-feedback">
      Please provide a valid city.
    </div>
  </div>
  <div class="col-md-3">
    <label for="validationCustom04" class="form-label">State</label>
    <select class="form-select" id="validationCustom04" required>
      <option selected disabled value="">Choose...</option>
      <option>...</option>
    </select>
    <div class="invalid-feedback">
      Please select a valid state.
    </div>
  </div>
  <div class="col-md-3">
    <label for="validationCustom05" class="form-label">Zip</label>
    <input type="text" class="form-control" id="validationCustom05" required>
    <div class="invalid-feedback">
      Please provide a valid zip.
    </div>
  </div>
  <div class="col-12">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="" id="invalidCheck" required>
      <label class="form-check-label" for="invalidCheck">
        Agree to terms and conditions
      </label>
      <div class="invalid-feedback">
        You must agree before submitting.
      </div>
    </div>
  </div>
  <div class="col-12">
    <button class="btn btn-primary" type="submit">Submit form</button>
  </div>
</form>
```

Antes de validarlos, el formulario se vería así:
![](https://i.imgur.com/9oYpezF.png)


Después de validar los campos:
![](https://i.imgur.com/rSEBPKP.png)


5. Layouts: breakpoints, contenedores y grid.

Bootstrap es un framework que crea webs full-responsive gracias a sus contenedores y breakpoinst. Cada componente usado se estirará o contraerá dependiendo del contenedor elegido.

- Contenedores disponibles: como puede comprobarse en la siguiente imagen, dependiendo de cómo queramos desarrollar nuestra web tendremos a nuestra disposición diferentes contenedores; si queremos que nos coja el 100% de la pantalla en dispositivos de más de 1400px usaremos .container-fluid, mientras que si nos interesa que sea orientado a dispositivos más pequeños, como tablets, usaremos .container-xl, etc.
![](https://i.imgur.com/ksQY9lp.png)

- Los breakpoints son los siguientes: como hemos visto con los contenedores, los breakpoints en los que se basan son estos:
![](https://i.imgur.com/4jj5ZiD.png)

- Los Grids: Bootstrap usa unidades de medida estáticas como px únicamente para los breakpoints o los grid, mientras que para el resto de componentes usa unidades escalables como rem o em. Grid se basa en la división de 12 columnas, es decir, que, como máximo, se podrá tener en el ancho un máximo de 12 columnas; podemos modificar esto añadiéndole al prefijo `col-` un número, como 6, la idea es que la cantidad de columnas con número incluido no sume más de 12, ya que estas acabarán en la siguiente fila si fuese así, por lo que yo podría tener dos `col-6` y `col-6` y cada una pillaría un 50% de las columnas.
![](https://i.imgur.com/cVilheY.png)
Tenemos aquí un ejemplo:
![](https://i.imgur.com/4sQ7sfI.png)


6. Ampliación:
    * Componente, control, técnica etc, a elección personal que consideres importante que se deba conocer de Bootstrap y no se haya visto.
    
En Bootstrap yo diría que una de los componentes más importantes pueden ser los modales; resultan muy útiles para mostrar información (como harían los alerts() en JavaScript) pero también para los logins o registros.

Un ejemplo de modal sería uno verticalmente centrado, como este:
![](https://i.imgur.com/z1NzMpI.png)
![](https://i.imgur.com/qP8UC5Z.png)

El código:
```htmlembedded
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModalCenter">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModalCenter" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLongTitle">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```
**Nota importante**: *hay que tener en cuenta que muchos atributos data vienen con un sufijo extra `bs` que está implementado en la versión 5 de Bootstrap, por lo que es probable que copiando y pegando directamente el código no funcione, habría que modificar el código como lo tengo arriba.*

El funcionamiento es simple, colocamos el modal en donde queramos de nuestra web, lo ideal sería ponerlo justo después del comienzo de la etiqueta body y antes del primer div; debemos tener en cuenta que el id del modal `exampleModalCenter` debe venir indicado de la siguiente forma en el botón: `data-bs-target="#exampleModalCenter"`; la clase `fade` junto a la clase `show` (que se añade con js al pulsar el botón) le da el efecto de aparición sutil y con su propia transición.
El modal viene dividido en `modal-header`, `modal-body` y `modal-footer`; si quisiéramos cambiar su apariencia, lo idea sería modificar esas clases directamente en nuestro css.
Para cerrar el modal habría que tener en cuenta el atributo `data-bs-dismiss="modal"`.


## Recursos

- [Web de referencia usada | Bootstrap Made](https://bootstrapmade.com/demo/HeroBiz/)
- [Bootstrap: guía para principiantes de qué es, por qué y cómo usarlo | Rock Content](https://rockcontent.com/es/blog/bootstrap/)


## Bibliografía



###### tags: `dor` `bootstrap`

