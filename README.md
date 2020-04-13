# ECMAScript6
Implementaciones a partir de ECMAScript 6+

## Qué es ECMAScript 
- Es la especificación del lenguaje propuesta por ECMA que es el consorcio que define lo estandares. JS Aplica esto a partir de 2015 que se lanzó ECMAScript 6. 

JS Nace en 1996 con la propuesta de Netscape.

## ECMAScript 6 
Cambia la forma de enviar parametros a las funciones: 
Antes: 
`function newFunction(name,  age, country){
var name = name || 'Ramon'
var age = age || 33
var country = country || 'CO'
}`

Ahora: 
`function newFunction2(name = 'Ramon', age = 33, country = 'CO'){
  doSomething...
}`

Al invocarla: 
`newFunction2()`
Sin parametros, traería los establecidos ó
`newFunction2('Ricardo', 23, 'MX')`
















