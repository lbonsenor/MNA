![[Pasted image 20260525180342.png]]
### a) 
Planteamos 
$$\lambda I-A=\begin{vmatrix} \lambda-3 & 0 & -1 \\
-1 & \lambda-k & 1 \\
-2 & 0 & \lambda-2\\
\end{vmatrix}$$
Para que sea un [[Valor propio]] de $A$: $\det(\lambda I-A)=0$
$$\begin{align}
12(k+1)+4(k+1) & =0 \\
16(k+1) & =0 \implies \boxed{k=-1}
\end{align}$$

### b)
$$\begin{align}
p(\lambda) & =\det(\lambda I-A) \\
 0& =(\lambda-2)((\lambda-3)(\lambda-2)-2) \implies\boxed{\lambda=\{1,2,4\}} 
\end{align}$$
Buscamos los autovectores
$\lambda=1:$
$$(A-\lambda I)\vec{v}=\begin{pmatrix}
2 & 0 & 1 \\
1 & 1 & -1 \\
2 & 0 & 1
\end{pmatrix}\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}=\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}\implies \begin{cases}
2x+z=0 \\
x-z=0 \\
x+y-z=0
\end{cases}\implies \vec{v_{1}}=\begin{pmatrix}
1 \\
-3 \\
-2
\end{pmatrix}$$
...
$$
\vec{v}_{2}=\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}, \qquad \vec{v}_{3}=\begin{pmatrix}
1 \\
0 \\
1
\end{pmatrix}\implies P=\begin{pmatrix}
1 & 0 & 1 \\
-3 & 1 & 0 \\
-2 & 0 & 1
\end{pmatrix}\wedge D=\begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 4
\end{pmatrix}
$$
