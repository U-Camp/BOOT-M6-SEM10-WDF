![Banner](./imagenes/banner.png)

# WDF M6 S10: Arreglos y POO

>#### Hola, ya te encuentras en la semana 6 de tu U Camp, ¿cómo pasa el tiempo, cierto?, espero te encuentres muy bien y estés aprendiendo mucho; en esta semana estudiarás lo correspondiente a Arreglos y Métodos de Arreglo en JavaScript.
>#### Continuemos...

# ÍNDICE

- [Arreglos](https://github.com/U-Camp/BOOT-M6-SEM10-WDF/blob/main/README.md#arreglos)
  - [Métodos de Arreglo](https://github.com/BOOT-M6-SEM10-WDF/blob/main/README.md#m%C3%A9todos-de-arreglo)
- [POO](https://github.com/U-Camp/BOOT-M6-SEM10-WDF/blob/main/README.md#programaci%C3%B3n-orientada-a-objetos-poo-principios-b%C3%A1sicos)


# Arreglos

Dentro del lenguaje JavaScript, el tipo de dato `Array` es una estructura de datos que permite almacenar una serie de elementos (que pueden ser cualquier tipo de dato, incluyendo otros objetos o estructuras de datos).

El uso de esta estructura, otorga la posibilidad de poder usar funciones de orden superior,  las cuales son parte de la programación funcional, directamente en JavaScript, algunas de las cuales se usan para realizar iteraciones, para realizar ordenamientos, mapear elementos o reducirlos a su mínima expresión, de tal manera que los métodos funcionales que ofrece y más usados son los siguientes:

### Métodos de Arreglo

- **Iteraciones:** Para realizar iteraciones sobre un arreglo se usa el método `forEach`, el cual recibe una función como parámetro que se va a ejecutar por cada elemento dentro del arreglo.

- **Ordenamiento:** Para ordenar un arreglo se usa el método `sort` el cual recibe una función de comparación como parámetro, la cual debe comparar dos elementos y decidir el orden entre ambos.

- **Filtrado:** En ocasiones es necesario filtrar un arreglo, de tal manera que se obtenga un arreglo de elementos que cumplan con cierta condición, precisamente esta función la realiza el método `filter`, el cual recibe una función que se ejecutará por cada elemento dentro del arreglo y validará si el elemento actual cumple una condición específica.

-   **Mapas:** Un mapa sirve para transformar un arreglo en otro arreglo totalmente diferente con base en los elementos actuales, por lo que se usa el método `map` para realizar esta acción, el cual recibe una función que se ejecutará por cada elemento y debe regresar el elemento transformado.
  
- **Reducers:** Un reducer sirve para reducir un arreglo de manera que se transforma un arreglo en otra estructura de datos distinta (un objeto, un tipo de dato específico o alguna otra cosa). Se usa el método `reduce` para lograr esto, el cual recibe una función que se ejecutará por cada elemento del arreglo y que debe regresar el elemento reducido, de tal manera que esta reducción se pasa como parámetro a la siguiente iteración. Se puede ver este proceso de reducción como si fuera un método recursivo recorriendo un arreglo.


```javascript
     // Inicializamos un arreglo
     const frutas = ['Manzana', 'Plátano', 'Naranja', 'Fresa', 'Zarzamora'];

     // Recorremos el arreglo
     frutas.forEach((elemento, indice, array) => {
       // Imprime el elemento actual y su índice
       console.log(elemento, indice);
     });

     // Ordenamos alfabéticamente el arreglo
     frutas.sort((fruta1, fruta2) => {
       // fruta1 va primero que fruta2
       if (fruta1 < fruta2) {
         return -1;
       }
       // fruta2 va primero que fruta1
       if (fruta1 > fruta2) {
         return 1;
       }

       // Los elementos ya están ordenados
       return 0;
     });
     console.log('Frutas Ordenadas: ', frutas);

     // Filtramos el arreglo
     const berries = frutas.filter((elemento) => {
       if (elemento === 'Fresa' || elemento === 'Zarzamora') {
         return true;
       }

       return false;
     });
     console.log('Berries: ', berries);

     // Mapeamos el arreglo
     const frutasMapeadas = frutas.map((elemento, indice) => {
       return {
         nombreFruta: elemento,
         posicion: indice,
       };
     });
     console.log('Mapeo: ', frutasMapeadas);

     // Reducimos el arreglo
     const valorInicial = '';
     const licuado = frutas.reduce((valorReducido, elemento) => {
       return `${valorReducido} - ${elemento}`;
     }, valorInicial);
     console.log('Reducción: ', licuado);
```     
>#### Hola, te dejo por aquí una infografía que ilustra un poco lo comentado sobre arreglos y métodos [Presiona aquí para consultar y descargar](https://github.com/U-Camp/BOOT-M6-SEM10-WDF/blob/main/infografias/M1_S6_Infografia%2001.pdf)


# Programación Orientada a Objetos (POO): Principios básicos
La Programación Orientada a Objetos da características que otorgan a los objetos propiedades que guardan datos así como de métodos que realizan acciones y procesan esos datos, pero para poder hacer uso de las mismas, es necesario definir esas propiedades y comportamientos en un concepto llamado Clase, básicamente una clase es una plantilla de código que sirve para instanciar objetos, esto es crear objetos en memoria, la cual debe seguir los principios básicos de la Programación Orientada a Objetos, los cuales son los siguientes:

- **Encapsulamiento**: Este principio indica que hay que mantener el estado de un objeto privado, esto quiere decir que sólo el objeto pueda modificar características internas, pongamos de ejemplo la historia de un gato y su usuario; el usuario puede alimentar al gato, pero no puede decidir qué tan hambriento se siente; así mismo, en la POO un objeto no puede comunicarse o alcanzar métodos o propiedades privados de otro objeto.

- **Abstracción**: Al aplicar el encapsulamiento, sólo unos cuantos métodos quedan accesibles externamente, lo que genera una interfaz de comunicación, esto quiere decir que un objeto no tiene porqué saber cómo está construido otro objeto o cómo funciona por dentro, sólo tiene que saber cómo comunicarse con él; tal cual como se interactúa con los objetos reales, muchas veces no se sabe cómo están construidos o cómo funcionan, el objeto con el que se interactúa expone una interfaz con la que se pueden realizar acciones en él. Si un usuario acaricia un gato y el gato como reacción empieza a ronronear, el usuario no tiene porqué saber cómo es que el gato ronronea, sólo interactúa a través del pelo y la piel del gato.

- **Herencia**: Muchas veces los objetos son bastantes similares, pueden compartir una lógica común, pero no siempre es exactamente lo mismo; la herencia permite el re-uso del código al crear una clase hija con base en una clase padre, heredando las propiedades y métodos de la clase padre, haciendo posible que se escriban en la hija nuevas propiedades y métodos específicos de la clase hija. Por ejemplo, el gato es un animal y comparte algunas propiedades y acciones de otros animales, como el alimentarse, las cuales se heredan de su clase "animal", pero tiene otros atributos y comportamientos específicos de los gatos, como el maullar.

- **Poliformismo**: En el ejemplo anterior, la acción de maullar también podría tomarse como una herencia de la clase "felino", ya que la mayoría de los felinos realizan exclamaciones con la boca, pero los gatos específicamente maúllan, ese pequeño cambio en como un objeto realiza una acción determinada es el polimorfismo y normalmente se logra sobrescribiendo o sobrecargando (overriding) los métodos de la clase padre.

```javascript

// La clase define las propiedades y comportamiento del objeto
class Persona {
  nombre = '';
  correo = '';

  // El constructor instancia la clase
  // es lo que hace que el objeto que se está creando
  // tenga una identidad y un estado

  constructor(nombre, correo) {
  // La palabra reservada `this` hace referencia al ámbito `scope` del objeto
  // en este caso hace referencia a sus propiedades internas.
  this.nombre = nombre;
  this.correo = correo;
}

// Los métodos definen el comportamiento que tendrá el objeto
  hablar(mensaje) {
    console.log(`Persona ${this.nombre} dice: ${mensaje}`);
  } 
  
  decirCorreo() {
  this.hablar(`Mi correo es: ${this.correo}`);
  }
}

// La clase `Instructor` hereda las propiedades y métodos de la clase `Persona`
// También se puede decir que `Instructor` es un tipo de `Persona`
class Instructor extends Persona {
// Se pueden crear nuevas propiedades para esta clase hija
materia = null;
// Así como crear nuevos métodos para esta clase hija
asignarMateria(materia) {
  this.materia = materia;
}

explicar(tema) {
// Validamos si tiene materia asignada
  if (!this.materia) {
    console.log(`${this.nombre} no tiene materia asignada.`);
  } else {
    console.log(`Hoy, en clase de ${this.materia}, veremos el tema: ${tema}`);
  }
}

// O se pueden sobrescribir métodos
hablar(mensaje) {
  console.log(`${this.nombre} dice: ${mensaje}`); }
}

// Creamos o instanciamos un nuevo objeto de tipo `Persona`
// Al instanciarlo se le asigna una identidad.
const fulano = new Persona('Fulano', 'fulanito@de.tal');

// Se pueden realizar acciones por medio de su interfaz (abstracción)
// Imprime `Mi correo es: fulanito@de.tal`
fulano.decirCorreo();

// Imprime `Persona Fulano dice: Hola, qué tal!`
fulano.hablar('Hola, que tal!');

// Así mismo se puede crear un nuevo objeto de tipo `Instructor`
// El cual recibe una nueva identidad.
const instructorZutano = new Instructor('Instructor Zutano', 'instructor.zutano@de.tal');

// Al ser el objeto de tipo `Instructor` se tiene acceso a los nuevos métodos definidos en su clase
// Ya que aún no asignamos una materia
// imprime: `Instructor Zutano no tiene materia asignada`
instructorZutano.explicar('Programación orientada a objetos');

// Los métodos de las clases son los únicos que modifican las propiedades internas
// Por lo que las propiedades están encapsuladas
instructorZutano.asignarMateria('Desarrollo de Software');

// Ya que el Instructor tiene materia asignada
// imprime: `Hoy, en la clase de Desarrollo de Software, veremos el tema Programación orientada a objetos` 22
instructorZutano.explicar('Programación orientada a objetos');

// Se puede acceder a los métodos de la clase padre `Persona`
// Imprime `Mi correo es: instructor.zutano@de.tal`
instructorZutano.decirCorreo();

// O se pueden usar los métodos sobrescritos de la clase hija (polimorfismo)
// Imprime: `Zutano Instructor dice: Hola desde Instructor`
instructorZutano.hablar('Hola desde Instructor');

```
>#### Te dejo por aquí una infografía por si deseas consultarla y descargarla, es sobre Programación Orientada a Objetos, [presiona aquí.](https://github.com/U-Camp/BOOT-M6-SEM10-WDF/blob/main/infografias/M1_S7_Infografia%2002.pdf)



>#### ¿Qué te pareció esta clase? Si tienes alguna duda recuerda que tus coaches y U Campers están disponibles para ayudarte, escríbeles. También te recuerdo, que puedes revisar el código anterior en Visual Studio Code o en algún IDE online como https://codepen.io/pen/ o  https://codesandbox.io/ para que vayas practicando y analizándolos. 
