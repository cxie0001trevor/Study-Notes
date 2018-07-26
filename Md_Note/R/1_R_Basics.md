# R Basics

标签：R

## 1. Main Data types in R

* integers

  ```R
  x <- 5L
  typeof(x)
  #>> [1] "integer"
  ```

  ---

* double

  ```R
  y <- 2.5
  typeof(y)
  #>> [1] "double"
  ```

  R by default will store data in double. To specify the value to be integer mode, you need to explicitly add `L` as suffix. Otherwise, R will anticipate that you will need arithmetic operation in futurn and store the value in double mode.

  Integer in R, however, are specifically for variables that will not have any arithmetic operation, for example:

  1. sequencing(i.e 1st, 2nd, 3rd, ... )
  2. categories(i.e 1., 2., 3., ... )

  ---

* complex

  ```R
  z <- 3 + 2i
  typeof(z)
  #>> [1] "complex"
  ```

  ---

* character

  ```R
  a <- "A"
  typeof(a)
  #>> [1] "character"
  ```

  ---

* logical

  ```R
  q <- T
  typeof(q)
  #>> [1] "logical"
  ```

  `T` for TRUE, `F` for FALSE. **REMEBER USING CAPITAL LETTERS!**

  ---

> **Note**: Spacings in R don't matter

## 2. Arithmetic operations

* Addition:` var1 + var2`
* Division: `var1 / var2`
* Multiplication: `var1 * var2`
* Power:` var2 ** 2`
* Other: `sqrt(var2)`

## 3. Characters concatenation

char1 = 'Hey'
char2 = 'there'
paste(char1, char2)
## 4. Logical operations

* Comparison: `4 < 5`, `10 > 100`, `4>=1`, `3<=5`
* Equal/Not equal: `a == b`, `a != b`
* Or: a | b
* And: a & b
* Logical operation function: `isTRUE(b)`

## 5. Iteration

* While loop

  ```R
  a = 0
  b = 5
  while(b > a){
    print(a)
    a <- a + 1
  }
  ```

  

> **Note**: To stop endless loop, press `esc`

* For loop

  ```R
  for(i in 1:5){
    print(paste('Hello R', i))
  }
  ```

## 6. Vector

```R
1:5
#>> [1] 1 2 3 4 5
```

## 7. Flow control - if-else statement

```R
rm(answer) 
x <- rnorm(1) #Normal Distribution function
if(x > 1){
  print(paste(x, "Greater than 1"))
} else if(x >= -1){
    print(paste(x, "Between [-1, 1)"))
} else{
  print(paste(x, "less than -1"))
}
```

> **Note**:
>
> `rm()`: Remove variable
>
> `ctl+l`: Clear console screen

## 8. Exercise

* The law of large numbers

  ```R
  # Example of tossing coin
  head <- 0
  tail <- 0
  total <- 10000
  for(i in 1:total){
    toss <- rnorm(1)
    if(toss>0){
      head <- head + 1
    }
    else{
      tail <- tail + 1
    }
  }
  print(paste('head: ', head/total))
  print(paste('tail: ', tail/total))
  ```

* Justify 3 segma law

  ```R
  N <- 10000000
  counter <- 0
  for (i in rnorm(N)){
    if(-1 <=i & i <= 1){
      counter <- counter + 1
    }
  }
  print(counter/N)
  ```

  