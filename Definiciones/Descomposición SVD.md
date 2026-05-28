La Descomposición en Valores Singulares (SVD) establece que cualquier matriz real $A$ de dimensión $m \times n$ se puede factorizar de la siguiente manera:

$$A = U \Sigma V^T$$

Donde:
- **$U$** es una matriz de $m \times m$ cuyas columnas son vectores ortonormales llamados [[Valor propio|autovalores]] **izquierdos**. Se calculan a partir de la matriz simétrica $A A^T$.
- **$V$** es una matriz de $n \times n$  cuyas columnas son vectores ortonormales llamados **autovectores derechos**. Se calculan a partir de la matriz simétrica $A^T A$. ^1f430d
- **$\Sigma$** es una matriz de $m \times n$ que contiene los **valores singulares** $\sigma_i$ ordenados de mayor a menor en su diagonal principal. Estos valores son las raíces cuadradas de los autovalores distintos de cero de $A^T A$.

#### Propiedad Fundamental
1. Para calcular los subvectores de $U$: $u_i = \frac{1}{\sigma_i} A v_i$.