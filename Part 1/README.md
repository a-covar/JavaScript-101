#JavaScript 
==========

## La Historia

El primer Browser famoro  NCSA MOSAIC

NetScape y HTML junto con la era del web iniciaron y agregaron interactividad 

Java  + Scheme + Self = LiveScript 

Scheme = Dialecto de List 
Self= Version mas rapida y sencilla de SmalTalk
Java 

LiveScript la herramienta principal de NetScape 
Sun + NetScape unieron fuerzas 
SunMicrosystems dio la licencia para llamarlo JavaScript 

Standar fue hecho European Computer Association pero no podian llamarlo JavaScript y lo registraon con el "working title" el cual fue ECMAScript

##ECMAScript 

Fue desarrollado en 2 semanas

1999 Thrid Editions ES3 

2009 Fifth Editions ES5  -> Primera cambio en 10 años
-Default 
-Strict  

-Para el corto plazo , trabajar en la interseccion de ES3 y ES5/Strict
-Para largo plazo , trabajar con ES5/Strict
-Evitar ES5/Default

## Lenguaje de Objects (mas que Java)

En javascrip un objecto es una collecion dinamica de propiedades. ( Cada propiedad tiene un llave string que es unica dentro del objeto)

###Operaciones fundamentales de los objectos 

* get 
	- **object.name** 
	- **object[expression]**
* set
	- **object.name=value;**
	- **object[expression]=value;**
* delete
	- **delete object.name;**
	- **delete object[expression];**


### Property

Una propiedad es una collecion de atributos con un nombre 

Hay dos tipos de **Data Properties y Accessor properties**

- value : (cualquier tipo de valor en Javascript)
- writable :  (boolean)
- enumerable: (boolean)
- configurable: (boolean)
ES5 (agregaron) 
- get: 	function(){.. return value;}
- set: function(value){...}


####Object literals 

```
var my_object= {foo:bar};

var my_object = Object.defineProperties(
	Object.create(Object.prototype,{
		foo:{
			value: bar ,
			writeable: true,
			enumerable: true,
			configurable: true
	}
	});

```

####Accessor property

```
Object.defineProperty('my_object,'inch',{
	get: function(){
		return this.mm /2.4;
	},set: function(value){
		this.mm = value * 25.4;
	},enumerable: true
});

```

###Classes v Protoypes

####Prototypes

- Creas un Objeto como tu quieres 
- Creas instancias nuevas que heredan de ese objeto 
- Customizas el nuevo objecto
- Taxonomia y clasificaciones no son necesarias 

#### Delegation (Differential Inheritance)

Objetos tienen un atributo prototype

- prototype: object or null
- Object.create(object,properties..)
- Object.getPrototypeOf(object)

```

function new(func, arguments ) {
	var that = Oject.create(func.prototype),
		result = func.apply(that, arguments);
	return ( typeof result === 'object' && result ) || that;
}

```

Soluciones ES5

- Object.create(null) crea un objecto que no hereda de nadie
- enumerable : false cuando agreges metodos nuevos , de esa manera no seran enlistados 
- Object.keys(object) , enlista su propias llaves de sus propiedades ( no las heredadas )




