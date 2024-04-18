Se tiene:
$$\begin{align}
a_{11}x+a_{12}y=b_{1}\\
a_{21}x+a_{22}y=b_{2}
\end{align}$$
- Si $a_{12} = 0$, entonces $x=\frac{b_{1}}{a_{11}}$  y se puede usar la segunda ecuación para despejar a $y$.
- Si $a_{22} = 0$, entonces $x=\frac{b_{2}}{a_{21}}$ y se puede usar la primera ecuación para despejar y.
- Si $a_{12} = a_{22} = 0$, entonces el sistema contiene solo una incógnita $x$.

Si se multiplica la primera ecuación por $a_{22}$ y la segunda por $a_{12}$ se tiene:
$$\begin{align}
a_{11}a_{22}x + a_{12}a_{22}y = a_{22}b_{1}\\
a_{12}a_{21}x + a_{12}a_{22}y = a_{12}b_{2}
\end{align}$$
Después si restamos la segunda ecuación de la primera:
$$(a_{11}a_{22}-a_{12}a_{21})x = a_{22}b_{1}-a_{12}b_{2}$$
Despejando:
$$x = \frac{a_{22}b_{1}-a_{12}b_{2}}{a_{11}a_{22}-a_{12}a_{21}}$$
### Si $a_{11}a_{22}-a_{12}a_{21} \neq 0$, entonces el sistema tiene una [[solución única]].