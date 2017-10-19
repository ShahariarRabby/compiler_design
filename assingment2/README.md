# Compiler Design Lab Assignment 2
### Problem Description:

In this assignment, you will implement how to evaluate a mathematical expression. The program will ask the user to input a value (say n). Then user will input n lines of input each of which contains an identifier and its corresponding value. Then program will ask the user again to input a value (say m). Then user will input m lines of expressions. Your job is to calculate the final value for each of the given expression using first n lines of input. If you can't evaluate any expression from given numbers of identifiers then output 'Compilation Error'. Allowed mathematical operators are +(add), -(subtract), x(multiply), /(divide).


### input 1:
<ul>
  <li>number of variables: 3</li>
    <li>a = 1
</li>
  <li>b = 2
</li>
  <li>c = 2
</li>

  </ul>
 
<ul>
  <li>number of equations: 2</li>
    <li>a x b + a x c + b x c
</li>
  <li>a x c - b / c + c x c
</li>

  </ul>



## output 2:

<ul>
  <li>number of equations: 2</li>
    <li>8 : for first equation
</li>
  <li>5 : for second equation
</li>

  </ul>
  


### input 2:
<ul>
  <li>number of variables: 4</li>
    <li>g = 2

</li>
  <li>p = 3
</li>
  <li>t = 1
</li>
 <li>w = 2
</li>

  </ul>
 
<ul>
  <li>number of equations: 3</li>
    <li>g + p x t - w x p

</li>
  <li>t - g + t - w
</li>
  <li>e + t x t - m
</li>
  </ul>



## output 2:

<ul>
  <li>number of equations: 2</li>
    <li>-1 //for first equation

</li>
  <li>-2 //for second equation
</li>
  <li>Compilation Error // for third equation
</li>
  </ul>
