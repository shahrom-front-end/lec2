# lec2

# 01 SCOPE
# 02 HOISTING
# RECURSION
# CLOSURE

## Область видимости — это текущий контекст выполнения, в котором значения и выражения являются «видимыми» или на них можно сослаться. Если переменная или выражение не находятся в текущем масштаб, он не будет доступен для использования. Области также могут быть разделены на слои в иерархии,чтобы дочерние области имели доступ к родительским областям, но не наоборот.

## 1 GLOBAL SCOPE-Область действия по умолчанию для всего кода, работающего в режиме сценария
    GLOBAL SCOPE
```js
    let a=3
    var b="Umed"
    const c=1234
```
## 2 FUNCTION SCOPE-Область действия, созданная с помощью функции.
```js
    function get(a){
    FUNCTION SCOPE
    }
    console.log(3);
```
## 3 BLOCK SCOPE-This scope restricts the variable that is declared inside a specific block, from access by the outside of the block.
```js
    if(true){
        BLOCK SCOPE
    }
    for(let i=0;i<a;i++){
        BLOCK SCOPE
    }
```
## 4 MODULE SCOPE-Область действия кода, работающего в модульном режиме
```js
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <script src="main.js" type="module"></script>
        <script src="main2.js"></script>
    </body>
    </html>
```
# HOISTING
## HOISTING- — это механизм JavaScript, в котором переменные и функции объявления перемещаются в верхнюю часть своей области перед кодом исполнение
```js
    console.log(a);//kor mekna undefined mega
    var a=2
```
# -----------------------------------------------
    FUNCTION DECLARATION
```js
    get(123)
    function get(num1){
        console.log(num1);//123 kor mekna nishon meta
        return num1
    }
```
# -----------------------------------------------
```js
    TDZ-(TEMPORAL DEAD ZONE) мёртвая зона
    let a=2
    const b=2
```

# RECURSION
## Рекурсия — это когда функция вызывает сама себя до тех пор, пока кто-то ее не остановит. Если никто не остановит это, то это будетрекурсия (вызвать себя) навсегда. Рекурсивные функции позволяют выполнять единицу работы несколько раз.В современных языках программирования, таких как JavaScript, уже есть операторы for и while.Альтернативы рекурсивным функциям. Но некоторые языки, такие как Closure, не имеют циклов.операторы, поэтому вам нужно использовать рекурсию для многократного выполнения фрагмента кода
    RECURSION
```js
    function recurse() {
        recurse();
    }
    recurse()
```
## Рекурсивная функция должна иметь условие для прекращения вызова самой себя. В противном случаефункция вызывается бесконечно.Как только условие выполнено, функция перестает вызывать себя. Это называется база состояние.Чтобы предотвратить бесконечную рекурсию, вы можете использовать оператор if...else (или аналогичный подход) где одна ветвь делает рекурсивный вызов, а другая нет.


# CLOSURE
## Замыкание — это комбинация функции, связанной вместе (приложенной) со ссылками на окружающее его состояние (лексическое окружение). Другими словами, замыкание дает вам доступ к области действия внешней функции из внутренней функции
```js
    function get(a){
        return function(b){
            return a+b  //CLOSURE
        }
    }
    console.log(get(2)(4));
```
