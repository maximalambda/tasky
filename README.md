Tasky
===

## Task 1. Front-end

**Task: Crear un formulario en React con nombre, email y teléfono; guardar en base de datos la información enviada.**

- Debe validar:
  - Que el usuario escriba su nombre con apellidos
  - Que el email sea válido
  - Que el teléfono sea a 10 dígitos
- Al enviar, debe guardar la información en base de datos

![](tasky/form.gif)

Puntos extra si la validación de nombre y apellidos se hace correctamente incluso si el usuario pone espacios o caracteres especiales, y si el teléfono es validado a 10 dígitos, independientemente de guiones y espacios que introduzca el usuario.

Puntos extra (×2) si el formulario (y sus campos y botón) se deshabilita para evitar que se envíe la información dos veces.

**Task: Completar la maqueta.**

Lograr que la primer sección (de fondo azul) se empalme ligeramente con la segunda sección:

![](tasky/layout.png)

Revisar [diseño final](tasky/landing.png) como referencia de cómo debe verse la maqueta. (Pista: este task no es solo de modificar el CSS, también el HTML.)

Puntos extra si la implementación considera un diseño responsive y los bordes de la imagen de fondo no son visibles en diferentes resoluciones, así como conexiones lentas que podrían tardar en cargar la imagen.

## Task 2. Back-end

**Task: Crear modelo Lead.**

Crea un nuevo modelo llamado `Lead` y una nueva migración que agregue al modelo 3 columnas string: nombre, email, teléfono.

**Task: Crear nuevo controlador.**

Crea un nuevo controlador para recibir la información del formulario y la guarde al modelo `Lead`.

Puntos extra si se realiza la misma validación que se hace en front-end, pero a través del controlador.

**Task: Nuevo endpoint.**

Crea un endpoint con ruta `/api/lead` y método POST para el controlador creado anteriormente, donde recibirás la información del formulario.

## Task 3. Tests

**Task: Completa las pruebas unitarias.**

Completa la prueba unitaria `test/Feature/LeadsTest` para comprobar que el endpoint recibe la información de Lead y la persiste en la base de datos.

**Task: Completa la prueba de integración.**

Completa la prueba de integración `test/Browser/LeadsTest` para comprobar que un usuario al escribir su información en el formulario y enviarlo el sistema recibe y persiste su información en la base de datos.

Puntos extra si la prueba se asegura que al enviar el formulario se muestre un mensaje de confirmación.

## Task 4. Revisión

#### Code review

Revisar las implementaciones realizadas con un ojo crítico. Anticípate a posibles observaciones que un reviewer haría. Señala las partes en las que un feature se podría romper o donde tiene deficiencias. Si usaste algo que no comprendiste a la totalidad, puedes dejarlo como comentario.

#### Limpiar commits

Asegúrate que los mensajes de los commits sean claros, precisos y concretos. Recuerda que debes utilizar commits atómicos, en los que los cambios sean agrupados naturalmente. Recuerda que puedes usar rebase interactivo para fusionar (squash), reordenar y renombrar commits.

Procura agregar un prefijo a tus commits para evitar redundancia y tener más claridad. Ejemplo:

> Leads: Se crean columnas y modelo

También reflexiona acerca de qué cambios son 100% necesarios para el proyecto y cuáles son archivos temporales, transitorios o de sistema (ejemplo: .DS_Store). Si encuentras alguno, asegúrate de quitarlo y de que no pueda volver.

#### Consideraciones de UX

Piensa en un usuario que no tiene una conexión ideal, pantallas más grandes o más pequeñas de las que tienes tú, considera que el usuario podría cometer errores y hay que darles una forma de corregirlo. También es importante evitar frustrar al usuario y ser suficientemente flexible al validar la información que ingresó en el formulario y la forma en la que se le comunica cuando hay errores.

#### Documentar quirks, limitaciones

Imagina que vas a entregar este proyecto a otra persona que va a darle seguimiento al mismo. ¿Qué limitaciones tiene la implementación actual, considera escenarios fuera del [happy path](https://en.wikipedia.org/wiki/Happy_path)?, ¿habrá escenarios en donde la aplicación devuelva un falso positivo o falso negativo?

Documenta todos estos casos de la forma en la que te gustaría que alguien más te hiciera entrega de un proyecto.

---

**Para correr pruebas unitarias:**

```
php artisan test
```

**Para correr pruebas de integración:**

```
php artisan dusk
```

---

### Setup

#### 1. Clonar repo

```
git clone git@github.com:osom-so/tasky.git
```

#### 2. Instalar dependencias

```
composer install
```
```
npm i
```
```
php artisan dusk:install
```

#### 3. Preparar Laravel

```
cp .env.example .env
```
```
php artisan key:generate
```

### Levantar servers

```
php artisan serve
```
```
npm run hot
```
