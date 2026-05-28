Este bloque temático de la materia describe un tipo de matrices con un comportamiento numérico extraordinario:

- **Matriz Simétrica:** Es una matriz cuadrada $A$ que es igual a su propia transpuesta ($A = A^T$).
- **Matriz Definida Positiva:** Una matriz simétrica $A$ de $n \times n$ es definida positiva si para cualquier vector no nulo $x \in \mathbb{R}^n (x \neq \vec{0})$, se cumple que el producto cuadrático es estrictamente mayor que cero:
$$x^T A x > 0$$
    
_(Equivalentemente: todos sus autovalores son estrictamente reales y positivos)._
    
- **Factorización de Cholesky (Teorema):** Si una matriz $A$ es simétrica y definida positiva, entonces se puede factorizar de forma única como el producto de una matriz triangular inferior con diagonales positivas ($G$) y su transpuesta:
    
    $$A = G \cdot G^T$$
    
    _Es una variante ultraeficiente de la factorización LU (donde $U = G^T$), ideal para optimización y computación de alto rendimiento._

Para una matriz de $3 \times 3$, el algoritmo deduce las fórmulas fila por fila:
$$\begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix} = \begin{pmatrix} g_{11} & 0 & 0 \\ g_{21} & g_{22} & 0 \\ g_{31} & g_{32} & g_{33} \end{pmatrix} \begin{pmatrix} g_{11} & g_{21} & g_{31} \\ 0 & g_{22} & g_{32} \\ 0 & 0 & g_{33} \end{pmatrix}$$

- **Paso 1 (Fila 1):** * $g_{11} = \sqrt{a_{11}}$
    - $g_{21} = \frac{a_{21}}{g_{11}}$
    - $g_{31} = \frac{a_{31}}{g_{11}}$
    
- **Paso 2 (Fila 2):**
    - $g_{22} = \sqrt{a_{22} - (g_{21})^2}$
    - $g_{32} = \frac{a_{32} - g_{31}g_{21}}{g_{22}}$
    
- **Paso 3 (Fila 3):**
    - $g_{33} = \sqrt{a_{33} - (g_{31})^2 - (g_{32})^2}$