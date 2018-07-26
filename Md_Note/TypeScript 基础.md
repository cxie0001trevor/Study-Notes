# TypeScript 基础

> *  Install TypeScript:
>
>    `sudo npm install -g typescript `
>
> * Check TypeScript compiler version:
>
>   `tsc --version `



1. 声明变量：`var`和`let`的区别主要在scope的范围。

   如果用`var`声明变量，举例如下

   ```typescript
   function doSomething(){
       for (var i = 0; i<5; i++){
           console.log(i);
       }
       console.log("Finally "+i);
   }
   ```

   此时变量`i`在整个function的定义内都是可以读写的。

   相反，若用`let`进行声明

   ```typescript
   function doSomething(){
       for (let i = 0; i<5; i++){
           console.log(i);
       }
       console.log("Finally "+i); //error
   }
   ```

   此时变量`i`仅限于在for循环内读写，可以有效的避免很多问题。

   需要注意的是，即使在IDE中会将这个问题报错，但当我们用ts的编译器时，tsc会自动转换成ES5版本的js（几乎所有浏览器都支持ES5版本），而该版本并没有关键词`let`，编译器会自动将其声明为`var`。因此虽然编译时会报错，但最终我们得到的js是可以运行的：

   ```javascript
   function doSomething() {
       for (var i = 0; i < 5; i++) {
           console.log(i);
       }
       console.log("Finally " + i);
   }
   doSomething();
   ```

   

