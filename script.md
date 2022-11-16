querySelector puede llamar a cualquier etiqueta clase o ID del documento de HTML desde un archivo JS "existen especificos como getElementsBy para clases y IDs"
```js
const h1 = document.querySelector('h1');
const p = document.querySelectorAll('p');
const parrafito = document.getElementsByClassName('parrafito');
// cuando utilizas querySelector tienes que poner un '.' o un '#' dependiendo si es clase o ID.
// const parrafito = document.querySelector('.parrafito'); 
// const pid = document.querySelector('#pid');
const pid = document.getElementById('pid');
const input = document.querySelector('input');

console.log(input.value);

console.log({
    h1,
    p,
    parrafito,
    pid,
    input,
});

// .innerHTML = '...'; puede sobre escribir en el html ya que desde JS creas una variable y con su querySelector y aparte te deja escribir codigo html tambien por dentro del atributo.
h1.innerHTML = 'Patito <br> Feo';
// busca el atributo que nosotros queramos y lo imprime en la consola.
// console.log(h1.getAttribute('class'));
// cambia el atributo que nosotros querramos por otro, los Elementos del inspector.
// h1.setAttribute('class', 'Samsung');

// añade una nueva clase a la etiqueta de html, asi tiene dos clases una de html y la otra de JS.
h1.classList.add('samsung');
// puedes eliminar una clase desde JS.
h1.classList.remove('LG');
// h1.classList.toggle('LG'); añade la clase o se le quita dependiendo si ya lo tiene o no.
// h1.classList.contains('LG'); condicional dependiendo si nuestro elemento tiene o no la classe que estamos buscando.

input.value = "123"

// creamos un nuevo elemento en el JS para la consola
const img = document.createElement('img');
img.setAttribute('src', 'https://i.pinimg.com/736x/e2/dc/da/e2dcdac1afcc856ab538b0faf4ea94da.jpg')
console.log(img);

// bonus: como quitar el texto del parrafo del ID, agregandole un string vacio.
pid.innerHTML = "";
// insertamos un elemento del JS en otro elemto del html y se puede ver ya en la pantalla.
pid.append(img);

// por defecto cuando se suman los input son en forma string pero para hacer una suma numerica se puede utilizar este codigo.
const h1 = document.querySelector('h1');
const input1 = document.querySelector('#calculo1');
const input2 = document.querySelector('#calculo2');
const btn = document.querySelector('#btnCalcular');
    // en HTML lo que te permite escuchar el evento de escuchar lo que hace el usuario es el atrubuto de HTML es:
        ```
        <button id="btnCalcular" onclick = "btnOnClick()">Calcular</button>
        ```
function btnOnClick () {
    console.log(Number(input1.value) + Number(input2.value));
}

// para escribir el resultado en la pantalla hay que crear el elmento en JS
const pResult = document.querySelector('#result');

function btnOnClick () {
    // aqui solo se guarda en una variable.
    const sumaInputs = Number(input1.value) + Number(input2.value);
    pResult.innerText = "Resultado es: " + sumaInputs;
}

// en este nuevo metodo dejas mas limpio el HTML usando el atributo de:
btn.addEventListener('click', btnOnClick);
// no es necesario poner los parentesis () porque solo nombras la función.
function btnOnClick () {
    const sumaInputs = Number(input1.value) + Number(input2.value);
    pResult.innerText = "Resultado es: " + sumaInputs;
}
    // en este caso si usas la etiqueta de form de html tienes que cambiar el type en el butón: y listo
    <form> 
        <button type="button" id="btnCalcular">Calcular</button>
    </form>

// de la otra forma deberias cambiar por sumit en vez de click y el event debe ser event.preventDefault
const form = document.querySelector('#form');

form.addEventListener('submit', sumarInputValues);

function sumarInputValues(event) {
    // console.log({event});
    event.preventDefault();
    const sumaInputs = Number(input1.value) + Number(input2.value);
    pResult.innerText = "Resultado es: " + sumaInputs;
}
```
## recuerda que en el formulario (form) agarra el ultimo boton lo toma como event (sumit) y recarga la pagina.