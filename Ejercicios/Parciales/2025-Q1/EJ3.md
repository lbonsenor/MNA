![[Pasted image 20260526120311.png]]
### a)
Primero calculamos $A^{T}A$ y sus [[Valor propio|autovectores]] para hallar [[Descomposición SVD#^1f430d|Sigma y V]]
$$A^{T}A=\begin{pmatrix}
3 & 5 & -2 &  \\
1 & -1 & 3
\end{pmatrix}\begin{pmatrix}
3 & 1 \\
5 & -1 \\
-2 & -3
\end{pmatrix}=\begin{pmatrix}
38 & 4 \\
4 & 11
\end{pmatrix}$$
Ahora calculamos el [[Polinomio Característico]]:
$$
\begin{align}
\det(A^T A - \lambda I)  & = \left| \begin{matrix} 38 - \lambda & 4 \\ 4 & 11 - \lambda \end{matrix} \right|  \\
0 & = (38-\lambda)(11-\lambda) - 16  \\
0 & = \lambda^2 - 49\lambda + 418 - 16  \\
0 & =\lambda^2 - 49\lambda + 402 & \implies \lambda=\begin{cases}
38.58 \\
10.42
\end{cases} \\
 &  & \implies \sigma=\begin{cases}
 6.21 \\
 3.23
 \end{cases}
\end{align}
$$

Ahora armamos la matriz $\Sigma$ respetando las dimensiones de $A(3\times2)$
$$\Sigma=\begin{pmatrix}
6.21 & 0 \\
0 & 3.23 \\
0 & 0
\end{pmatrix}$$
Ahora calculamos $V$ en base a $(A^{T}A-\lambda I)v=0$
**Para $\lambda_1 \approx 38.58$:**

$$\begin{pmatrix} 38 - 38.58 & 4 \\ 4 & 11 - 38.58 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies -0.58x + 4y = 0 \implies x \approx 6.9y$$

Un autovector base es $\begin{pmatrix} 6.9 \\ 1 \end{pmatrix}$. Al normalizarlo dividiendo por su norma $\sqrt{6.9^2 + 1^2} \approx 6.97$:

$$v_1 = \begin{pmatrix}
6.9 \\
1
\end{pmatrix}\cdot \frac{1}{6.97}= \begin{pmatrix} 0.99 \\ 0.14 \end{pmatrix}$$
**Para $\lambda_2 \approx 10.42$:**
Al ser una matriz simétrica, el segundo autovector debe ser perpendicular al primero:
$$v_2 = \begin{pmatrix} -0.14 \\ 0.99 \end{pmatrix}$$Por lo tanto, la matriz **$V$** (y su transpuesta $V^T$) es:
$$V = \begin{pmatrix} 0.99 & -0.14 \\ 0.14 & 0.99 \end{pmatrix} \implies V^T = \begin{pmatrix} 0.99 & 0.14 \\ -0.14 & 0.99 \end{pmatrix}$$

Ahora encontramos $U$
- **Primera columna ($u_1$):**$$u_1 = \frac{1}{6.21} \begin{pmatrix} 3 & 1 \\ 5 & -1 \\ -2 & -3 \end{pmatrix} \begin{pmatrix} 0.99 \\ 0.14 \end{pmatrix} = \frac{1}{6.21} \begin{pmatrix} 3.11 \\ 4.81 \\ -2.4 \end{pmatrix} \approx \begin{pmatrix} 0.50 \\ 0.77 \\ -0.39 \end{pmatrix}$$

- **Segunda columna ($u_2$):**
$$u_2 = \frac{1}{3.23} \begin{pmatrix} 3 & 1 \\ 5 & -1 \\ -2 & -3 \end{pmatrix} \begin{pmatrix} -0.14 \\ 0.99 \end{pmatrix} = \frac{1}{3.23} \begin{pmatrix} 0.57 \\ -1.69 \\ -2.69 \end{pmatrix} \approx \begin{pmatrix} 0.18 \\ -0.52 \\ -0.83 \end{pmatrix}$$
- **Tercera columna ($u_3$):**
    Como $U$ debe ser una matriz de $3 \times 3$ ortogonal, buscamos un tercer vector que sea ortogonal a $u_1$ y $u_2$. Esto lo logramos fácilmente calculando el **producto vectorial** $u_1 \times u_2$:
$$u_3 = u_1 \times u_2 \approx \begin{pmatrix} -0.84 \\ 0.35 \\ -0.40 \end{pmatrix}$$

Reuniendo las columnas, obtenemos **$U$**:
$$U = \begin{pmatrix} 0.50 & 0.18 & -0.84 \\ 0.77 & -0.52 & 0.35 \\ -0.39 & -0.83 & -0.40 \end{pmatrix}$$Ya tenemos todas las componentes para expresar la SVD: $A = U \Sigma V^T$

### b)