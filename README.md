# ECMAScript6
Implementaciones a partir de ECMAScript 6+

## Qué es ECMAScript 
- Es la especificación del lenguaje propuesta por ECMA que es el consorcio que define lo estandares. JS Aplica esto a partir de 2015 que se lanzó ECMAScript 6. 

JS Nace en 1996 con la propuesta de Netscape.

## ECMAScript 6 
- Cambia la forma de enviar parametros a las funciones: 

- Antes: 
`function newFunction(name,  age, country){
var name = name || 'Ramon'
var age = age || 33
var country = country || 'CO'
}`

- Ahora: 
`function newFunction2(name = 'Ramon', age = 33, country = 'CO'){
  doSomething...
}`

- Al invocarla: 
`newFunction2()`

- Sin parametros, traería los establecidos ó
`newFunction2('Ricardo', 23, 'MX')`

## Teplates Literal // Templates String
Concatenar valores es ECMAScript 6 es más claro: 
`let hello = "Hello"
let world = "World"
console.log(`${hello} ${world}`)
`
Se utilizan comillas francesas o inversas y para llamar a las variables se llaman ${}.

## Multilinea en ECMAScript
Todo lo que este dentro del template literal (comilla francesa) pasa a ser multilinea.
`{Todo 
lo 
que este
aquí adentro es 
multilinea}`

## Destructuración de los objetos
`let person ={
  "name" : "Carlos",
  "age" : 34,
  "country" : "JO"
}`
- antes: 
`console.log(person.name, person.age)`
- Ahora: 
`let {name, age, country} = person // se traen solo los que necesitamos
console.log(name, age, country)
`

## Operador de propagación
Nos permite unir arreglos dentro de arreglos. 
`let team1 = ['nombre', 'nombre2', 'nombre3']
let team2 = ['nombre4', 'nombre5', 'nombre6']
let education = ['otroNombre', ... team1, ...team2]
`

## Variables
Se definene según su "Scope" ó alcance. 
### Var
Las origiales de JS, pero cada vez se usan menos. Erán globales. Se puede reasignar a lo largo del código. 
### Let
Existe solo en el scope, dentro del bloque en el que es creada. 
### Const
Constante, valores que son constantes. No se puede reasignar. 

## Crear objetos a partir de variables
- Es más simple con ECMAScript 6
`
let name = "Leo"
let age = 34
obj = {name, age}
`

### Arrow Function o Funciones de tipo flecha
- Son funciones anonimas y son más simples de escribir.
`const names = [
  {name: "Carla", age: 25},
  {name: "Elisa", age: 20}
]
`
- antes: 
`let listOfNames = names.map(function(item){
  console.log(item.name)
})
`
- ahora: 
` let listOfnames2 = names.map(item => console.log(item.name))
  const listOfNames3 = (name, age, country) => { ... doSomething}
`
## Promesas
Se trabaja el asicronismo, JS ejecuta una por una las tareas. Resuleven el problema del callbackhell.
`const holaPromesa = () =>{
  return new Promise((resolve, reject)=> {
  if (true){
  resolve ("Hola!")
  }
  else{
  reject("adios!")}
  })
}
`
- Para ejecutarla:
`holaPromesa()
  .then=>(response => console.log(response))
  .catch(error => console.log(error))`
  
## Clases
` class calculator{
    constructor(){
    this.valueA = 0
    this.valueB = 0
    }
    sumar(valueA, valueB){
    this.valueA = valueA
    this.valueB = valueB
    return this.valueA + this.valueB
    }
}

cont calc = new calculator()
console.log(calc.sum(2,2))
`
## Modulos
- import y export. Se puede separa la lógica en diferentes nodos. En el archivo a exporta se escribe: 
`experot default nombreFuncion`
- En el archivo que recibe la función es: 
`importe {nombreFuncion} from './nombreArchivo'`

## Generadores
- Es una función que retorna una serie de valores definidos: 
`function*helloWorld(){
    if(true){
        yield'Hello, '//Guarda el estado de forma interna
    }
    if(true){
        yield'World '//El segundo valor es llamado cuando se ejecuta el siguiente valor
    }
        
};

const generatorHello =helloWorld();
//Luego puedo utilizar valor next, ejecuto lógica, y al ejecutar el siguiente next se meustra el segundo valor, hasta n next.

console.log(generatorHello.next().value);
console.log(generatorHello.next().value);
console.log(generatorHello.next().value); // Al no tener ningún valor en el siguiente next, al ejectuar muestra un "Undefined".
`

## ECMAScript 7
- Se lanza en Junio de 2016:
-  Se agrega el metodo includes que verifica el contenido de un arreglo. 
`letnumber =[1,2,3,4,6];

if(number.includes(6)){
    console.log("Se encuentra el valor");
}else{
    console.log("No se encuentra el valor");
}
`
- Las potencias ahora se operan con doble asterisco :
`let base =4;
let exponent =3;
let resultado = base**exponent;

console.log(resultado);
`
## ECMAScript 8 
- Se lanza en juio de 2017.
- Object entries devuelve los valores de una matriz.
`
const data ={
    front:'Isabel',
    back: 'Ana'
};
`
- Tranformar este objeto en una matriz. 
`const entries =Object.entries(data);
console.log(entries);`
- Si queremos saber cuantos elementos posee nuestro arreglo ahora es posible con length:
`console.log(entries.length);`

- Objetc Values: Me devuelve los valores de un objeto a un arreglo. los transforma.
`const data= {
    front:'Isabel',
    back: 'Ana'
}

const values = Object.values(data);
console.log(values);
`
- Pading: nos permite añadir cadenas vacías a string, pudiendo modificar la cadena string como tal.
- Podría servir del lado del front , para mostrar una estructura de elementos.
`
const string ='hello';
console.log(string.padStart(7,'hi')) // se añade al inicio la palabra 'hi'
console.log(string.padEnd(12,'hi')) // Se añade al final la palabra 'hi'
`

- Trailing comas, nos permite asignar elementos al objeto mediante comas. Aun cuando no sean necesarias las comas al final se colocan.
`
const data= {
    front:'Ana',
    back: 'Isabel',
}
`
### Async Await 
Nos permime manejar el asincronismo: 
`const helloWorld =() =>{
    return new Promise((resolve,reject)=>{
        (true)
        ? setTimeout(()=>resolve('helloWorld'),3000)
        : reject(new Error ('Test Error'))
    })
}`
- luego de crear la promesa se invoca el await:
`const helloAsync =async() =>{
    const hello = await helloWorld();
    console.log(hello);

}
helloAsync();`

- Nos permitirá usar try, catch y trabajar los errores correctamente.

`const another =async() =>{
    try{
        const hello = await helloWorld();
        console.log(hello);

    } catch (error){
        console.log(error);
    }
}

another();`

## ECMAScript 9
- Operador de reposo puede extraer las propiedades de un objeto que aún no se ha construido. ...all
`const obj= {
    name:'Carlos', 
    nick: 'rcamaster',
    age: 34,
    country: 'MX'
}

let{name, ...all}=obj;
console.log(name,all); 
se extrae el nombre y lo demas se " encapsula" en un objeto.
`
- Utilizando propiedades de propagación se pueden añadir multiples objetos a otros objetos mediante ...nombre_objeto

`const obj= {
    name:'Carlos', 
    nick: 'rcamaster'
}
const obj1= {
    ...obj,
    alter:'rcarlosalba', 
    alternick: 'carielalba'
}
const obj2= {
    ...obj1,
    loveone:'Emma', 
    nickloveone: 'Elu'
}

console.log(obj2);
nos permite generar nuevos objetos in alterar los existentes
`
- Promise.finally podemos saber cuando ha terminado el llamado para ejecutar una función.
`
const helloWorld =() =>{
    returnnew Promise((resolve,reject)=>{
        (true)
        ? resolve('helloWorld')
        : reject(newError ('Test Error'))
    });
}

helloWorld()
    .then(response => console.log(response))
    .catch(error=>console.log(error))
    .finally(()=>console.log('finalizo'))
`
## RegEx
Agrupando bloques: 
`
const regexData = /([0-9]{4})-([0-9]{2})-([0-9]{2})/
const match = regexData.exec('2018-04-20');

const year = match[1]
const month = match[2]
const day = match[3]

console.log(year, month, day);
`
## ECMAScript 10
- .flat devuelve una matriz con una submatriz aplanada.
- recibe como argunmento la profundidad o nivel
`
let array = [1,2,3, [1,2,3, [1,2,3]]];

console.log(array.flat(2))
`

- .flatMap: mapear cada elemento, luego pasarle una funcion y aplanar
`
let array = [1,2,3,4,5];

console.log(array.flatMap(value => [value, value * 2]));
`
- trim: 
- Elimina los espacios en blanco de un string.
`
let hello = '                      hello world';
console.log(hello);
console.log(hello.trimStart()); // inicio

let hello = 'hello world                  ';
console.log(hello);
console.log(hello.trimEnd()); // final
`
- optional catch biding
`
try {
    
} catch/*(error) ya no es necesario colocarlo*/ {
    error
}
`
- fromEntries
- arreglo a objeto:
`let entries = [["name", "oscar"], ["age", 32]];
console.log(Object.fromEntries(entries))
`
- symbol object:
`
let mySymbol = 'My Symbol';
let symbol = Symbol(mySymbol);
console.log(symbol.description);
`
## TC39
























































