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
Todo lo que este dentro del template literal pasa a ser multilinea.
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
  .catch(error => console.log(error))
`
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




