### This is an interactive bash program which allows to rent bikes from a bike rental shop.


## checking whether the pattern or variable contains numbers or not ?
```
$ [[ a =~ [0-9] ]]; echo $?
#output: 1 (Which means the expression is false)

$ [[ a1 =~ [0-9] ]]; echo $?
#output: 0

$ [[ a1 =~ ^[0-9]$ ]]; echo $?
#output: 1 ( ^ signifies start of pattern and $ end of pattern)

$ [[ 11 =~ ^[0-9]+$ ]]; echo $?
#output: 0 ( + is required for checking strings that start and end with numbers, also for multi-digit numbers)

$ [[ ! 11 =~ ^[0-9]+$ ]]; echo $?
#output: 1 ( It means 11 is a number and ! signifies for not equal to pattern)
```
