# bash

## Arithmetic Commands

    i=$((j + 3))   <== arithmetic expansion, use the same syntax as C

    let a=17+23    <== arithmetic Commands
    let a=17 + 23  <== WRONG, should not do it
    let a=17 a+=32 <== Right

    ((a=$a+7))     <== right way
    ((a = a + 7))  <== also right

## Random 

    number=$((1 + RANDOM%10)) #random number between 1-10


