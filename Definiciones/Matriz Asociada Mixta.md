En una transformación lineal $T: V \to W$, la matriz asociada necesita saber en qué "idioma" (base) va a recibir los vectores de entrada y en qué "idioma" debe entregar los vectores de salida.
La posición de las letras en el subíndice sigue una regla estricta:
$$M_{\text{Salida} \leftarrow \text{Entrada}}(T) \quad \implies \quad M_{EB}(T)$$

- $B$ representa la **base del espacio de entrada (dominio)**. Significa que los vectores que le metas a la matriz deben estar expresados en coordenadas de la base $B$.
- $E$ representa la **base del espacio de llegada (codominio)**. En este caso, la $E$ se refiere a la **base estándar o canónica**. Significa que el resultado que te devuelva la matriz saldrá automáticamente en el formato tradicional de toda la vida.

> **Definición conceptual:** > $M_{EB}(T)$ es la matriz que toma un vector expresado en coordenadas de una base personalizada $B$, le aplica la transformación lineal $T$, y te escupe el resultado expresado en coordenadas de la base canónica $E$.

Para hallar todos los $v\in\mathbb{R}^{n}$ dado un $B$, hay que encontrar $c_{1},c_{2},\dots,c_{n}$ tal que
$$c_{1}B_{1}+c_{2}B_{2}+\dots+c_{n}B_{n}=T(v)$$

A partir de ahi
$$M_{EB}(T)\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\
\dots \\
x_{n}
\end{pmatrix}=\begin{pmatrix}
c_{1} \\
c_{2} \\
\dots \\
c_{n}
\end{pmatrix}$$
