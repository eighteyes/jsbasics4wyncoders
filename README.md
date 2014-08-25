## Functions

### Named
function foo() { }

### Assigned
var foo = function(){ }

### Anonymous
function() { }

### Method
function foo() {
  return {
	bar: function() { return 'a' }
	}	
}

### Classes

#### Function Notation of Methods

var Car = function(c){
this.wheels = c;
Car.prototype.getWheels = function(){
return this.wheels;
}
return this;
}

// var c = new Car(4)

#### Object Notation of Methods
var Car = {
getWheels : function(n) {
return n;
}
}

// var w = Car.getWheels(4) 

### Recursion
function hi(n){
   return n>0 ? hi(n-1) + 'y' : 'he'
}

### Functions and Objects

#### Both have properties
var obj = {};
var fn = function(){};
obj.foo = "abc";
fn.foo = "abc"
(obj.foo == fn.foo) // true

### Scope

window.Foo = 123
// Foo = 123

function Car(){
  this.wheels = 4;
  return this
}
// Car() => sets global wheels to 4
// new Car() => makes { wheels: 4 }

var cat = {
	pet: function() {
   this.isHappy = !this.isHappy;
  },
feed: function(){
	this.isHappy = true
},
isHappy : false
}

function Cat(){
   Cat.prototype.pet = function(){
   this.isHappy = !this.isHappy;
}
Cat.prototype.feed = function() {
	this.isHappy = true;
}

this.isHappy = false;

return this
}

## Conditionals

### Basic
var truth = ( x == y );
// true

### Inversion
var untruth = !(x == y);
// false

### Coercion
var theTruth = !!( 100 )
// true

### Type checking
typeof {} => object
typeof [] => object
typeof '' => string
typeof null => object
typeof x => undefined

### Type Cocercion in Conditionals

( '0' == false ) //true
( '0' === false ) //false

( '1' == true ) // true
( '2' == true ) // false
( '1' === true ) // false


### Not A Number
isNaN('a') // true
isNaN('12') // false
isNaN(12) // false

### Parse Int
parseInt('123abc456') // => 123


### Single line optional brackets
if ( x == true ) { doThing(); }
if ( x == true ) doThing();

### Conditional Syntax
if ( x == true || y == false ) {
doThing();
} else if ( z == true ) {
doOtherThing();
} else ( a == false ) {
doFinalThing();
}

### Tertinary operations

var foo = ( x == y ) ? x + y : y*y

( what is it ) ? true : false; 

## Iterators

for ( var i = 0; i < l; i++) { }
for ( var i = 0, l = length; i<l; i++) {}
for ( var key in object )
for ( var i in array )

## Iterator as Conditional
var obj = { foo: 'bar' }
if ( "foo" in obj ) {
console.log('hi')
}

## DOM Primer
location.reload()
navigator.userAgent

## Geolocation
function geoWin( position ) {
console.log(position);
}
navigator.geolocation.getCurrentPosition( geoWin )

## Local Storage
localStorage.setItem('foo', 'bar')
localStorage.getItem('foo') // bar


## Timers

var doThing = function(){
console.log("hi")
clearTimeout(interval)
}
setTimeout( doThing, 500);
var interval = setInterval(doThing, 1000);

## Arrays

> var o = []
undefined
> o.push(1)
1
> o.push(2)
2
> o.thing = 'three'
'three'
> o
[ 1, 2, thing: 'three' ]
> o.length
2
> o.hasOwnProperty('thing')
true
> o.push("3")
3
> o
[ 1,
  2,
  '3',
  thing: 'three' ]
> o.length
3
> o[6] = "6"
// o.length = 7

var a = [1,2,3];
var b = new Array(1,2,3)
var c = new Array(3)
// a == b != c
// a.length == b.length == c.length

### Mutator Functions
a.pop() // => 3, a = [1,2]
a.push(4) // => 3, a = [1,2,4]
a.reverse() // => a = [4,2,1]
a.shift() // => 4, a = [2,1]
a.sort() // => a = [1,2]
a.splice(1, 1, 3, 5) // => 2, a = [1,3,5]
a.splice(-2, 2, 2,3,4,5) // => [3,5], a = [1,2,3,4,5]
a.unshift(0) // => 6, a = [0,1,2,3,4,5]

### Accessor Functions
a.concat(6,7,8) // => [0,1,2,3,4,5,6,7,8]
a.join('+') // => '0+1+2+3+4+5'
a.slice(1, 4) // => [1,2,3]
a.slice(-2) // => [4,5]
a.slice(1, -2) // => [1,2,3]
a.indexOf(1) // => 1
a.lastIndexOf('a') // => -1

## Iterators
function logIt(i){ console.log( i )};
function evens(i){ return i % 2 } 
function square(i){ return i*i }
function add( prev, next ) { return prev + next }

a.forEach(logIt) // c=> 012345
a.filter(evens) // => [1,3,5]
a.filter(events).map(square) // => [1, 9, 25 ]
a.filter(evens).map(square).reduce(add) // => 35
a.filter(evens).map(square).reduce(add, 5) // => 40


## Strings
'a' > 'A'
for (var i = 0; i < 126; i ++ ) { 
console.log( String.fromCharCode(i), i) 
}

var s = '';
for ( var i = 97; i <= 122; i++) {
s += ( String.fromCharCode(i)) }
}

// no mutator methods
s.charAt(25) // => z
s.concat("123") // => 'abcdefghijklmnopqrstuvwxyz123'
s.indexOf('a') // => 0
> s.split('m')
[ 'abcdefghijkl', 'nopqrstuvwxyz' ]
s.substr(12,6)
'mnopqr'
s.substr(-1,5)
'z'
> s.substring(10,6)
'ghij'
> s.substring(10,16)
'klmnop'
s.toUpperCase()
'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
> s.toLowerCase()
'abcdefghijklmnopqrstuvwxyz'

> s = "     a      "
'     a      '
> s.trim()
'a'




> s.match(/[mno]/)
[ 'm',
  index: 12,
  input: 'abcdefghijklmnopqrstuvwxyz' ]

### Regex
> s
'abcdefghijklmnopqrstuvwxyz'
> s.replace(/[a-m]/, '1')
'1bcdefghijklmnopqrstuvwxyz'
> s.replace(/[a-m]/g, '1')
'1111111111111nopqrstuvwxyz'
> s
'abcdefghijklmnopqrstuvwxyz'
> s.match(/[mno]/)
[ 'm',
  index: 12,
  input: 'abcdefghijklmnopqrstuvwxyz' ]





## Objects

Object.keys()


## Date

var date = new Date()
> date.getTime()
1408926555034

var d = new Date('01-01-1971')
undefined
> d
Fri Jan 01 1971 00:00:00 GMT-0500 (EST)
> d.getTime()
31554000000

> var d = Date.now()
undefined
> d
1408926700781

> var date = new Date()
undefined
> date.getTime()
1408926761586
> date
Sun Aug 24 2014 20:32:41 GMT-0400 (EDT)
> date.toString()
'Sun Aug 24 2014 20:32:41 GMT-0400 (EDT)'
> date.toString().substring(4,15)
'Aug 24 2014'

## Math


Math.random( Math.round() * 1000 ) 
