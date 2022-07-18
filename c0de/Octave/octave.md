# Coding in Octave

<!--SuiGn-->

```octave
x = -3:3;
ans =
-3, -2 , -1, 0, 1, 2, 3

x = -3: .5 : 3;
ans = 
-3.0000  -2.5000  -2.0000  -1.5000  -1.0000  -0.5000     0  0.5000  1.0000  1.5000  2.0000  2.5000  3.0000

```

Para Octave todos los elementos son matrices:

**Vectors:** 1 x n

**Columnas:** n x 1

```octave
matrix = [1,2; 3,4];
ans = 
1 2
3 4

vector1D = [1,2,3,4];
answ = 
1 2 3 4

vectorC = [1;2;3;4];
ans = 
1
2
3
4
```

Para acceder a los valores de una variable:

Es importante notar que la numeraci ́on de los vectores y matrices comienza en 1 y
no en 0 como en otros lenguajes de programación.

```octave
matrix=[0.9 0.3 0.2;0.3 0.9 0.4; 0.4 0.2 0.9];
matrix(1,3)
ans = 0.20000
```

El operador ‘:’  indica acceso a todos los elementos de una
fila o columna, y de esta manera tomar filas y/o columnas individuales dentro
de una matriz:

```octave
matrix(1,:)
ans =
0.90000 0.30000 0.20000
matrix(:,1)
ans =
0.90000
0.30000
0.40000

```



**Multivariate Statistical Techniques**
**Matrix Operations in Octave**
http://www.philender.com/courses/multivariate/notes/matoctave.html

**Command: who**  - show variables
**Command: disp() **- to print text or variables

**Operator Index**:
https://octave.org/doc/v4.2.1/Operator-Index.html













