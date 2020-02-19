# Intro (19.02.2020)

![image-20200219084335631](webpr_notes.assets/image-20200219084335631.png)

## Quiz

http://86.119.37.112:9090
Matrikel Nr & key
Plan: 11 points per week
Passing threshold: 60%  

Key: **543**

# Functions

```js
function fun2()    { return 1; }
function fun2(arg) { return arg; } //Hier wird fun2 überschrieben

document.writeln( fun2() !== 1  );
document.writeln( fun2() === undefined ); // <-- fun2() ist nun undefined
document.writeln( fun2(42) === 42 );
```

**Eine Funktion kann nur einmal erstellt werden. Es gibt nur eine referenz auf diese. => kein overloading möglich!**

```js
function noReturn()    { 1; } //undefined => no return statement
const noReturn2 = () => { 1; }; //undefined => da {} kein ausdruck sind und nach => kommt ein ausdruck
```

> In einem Block "{}" sind eine reihe von Anweisungen, getrennt mit ;

### Definitionsmöglichkeiten

```js
function fun1()	{ return 1; }
const fun2 = () => 1; //can't overwrite fun2 => runtime error
```

Javascript ist compilerlos => variable überschreiben oder runtime error

(**zuweisung) wird als ausdruck gewertet!**
js forced ausdruck

**Yoda Conditional** RightValue === LeftValue instead of LV == RV

```js
 function doit(waszutunist) {
 return function bla(arg) { return waszutunist(arg) };
 }
document.writeln( doit(fun1)(10) === 1 ); //Curried fun1()()
document.writeln( doit(fun2)(10) === 10 );

//equivalent zu
 const doit2 = (callme => (arg => callme(arg)) ;
 document.writeln( doit2(fun1)(10) === 1 );

```

**Function scope ist der einzig verlässliche scope in JS!**

```js
const plus = x => y => x+y; //can be called with plus(x)(y) curried
```

