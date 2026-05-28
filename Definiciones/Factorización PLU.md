En la práctica computacional o cuando un pivote se vuelve cero ($0$), no es posible avanzar con la eliminación gaussiana pura. Para solucionar esto, el teorema de la **Factorización PLU con pivoteo parcial** garantiza que **cualquier matriz cuadrada invertible $A$** de $n \times n$ se puede factorizar como:

$$P \cdot A = L \cdot U$$

Donde $L$ y $U$ conservan las mismas definiciones de [[Factorización LU]] (triangular inferior unitaria y triangular superior), y se introduce un nuevo componente:
- **$P$ (Matriz de Permutación):** Es una matriz cuadrada de $n \times n$ que se obtiene reordenando (permutando) las filas de una matriz identidad. Multiplicar $P \cdot A$ genera una nueva matriz que contiene exactamente las filas de $A$ pero intercambiadas en el orden óptimo para evitar divisiones por cero o reducir errores de redondeo numérico.
### Pasos Generales para hacer la Factorización PLU
#### **Paso 1: Configurar las matrices iniciales**
- Se inicia con la matriz original $A$.
- Se crea la matriz de permutación $P$ inicializándola como una **matriz identidad** ($I$).
- Se crea la matriz $L$ como una matriz de ceros, pero colocando **unos ($1$) en su diagonal principal**.
    
#### **Paso 2: Eliminación con estrategia de pivoteo parcial**
Al igual que antes, avanzamos columna por columna ($j = 1 \dots n-1$). Sin embargo, antes de calcular cualquier multiplicador en la columna $j$, realizamos la búsqueda del pivote:
1. **Búsqueda del elemento máximo (Pivoteo Parcial):** Se revisa el valor absoluto de todos los elementos que están en la columna $j$, desde la diagonal hacia abajo (filas de $j$ hasta $n$). Se identifica cuál es el número más grande en magnitud.
2. **Intercambio de filas (Permutación):** Si el número con mayor valor absoluto se encuentra en una fila inferior $k$ ($k > j$), se procede a realizar un intercambio de filas:
    - En la matriz $A$, se intercambia por completo la fila $j$ con la fila $k$.
    - En la matriz de permutación $P$, se realiza exactamente el mismo intercambio de la fila $j$ con la fila $k$.
    - _Propiedad de registro en $L$:_ Si ya se habían calculado multiplicadores en pasos o columnas anteriores, los elementos correspondientes de esas filas en la matriz $L$ también deben intercambiarse para mantener la coherencia de la historia de operaciones.
3. **Calcular multiplicadores y reducir:** Con el pivote óptimo ya posicionado en la diagonal $a_{jj}$, se calculan los multiplicadores para todas las filas inferiores de esa columna:
$$m_{ij} = \frac{a_{ij}}{a_{jj}}$$

    Se efectúa la resta en las filas de la matriz $A$: $F_i \leftarrow F_i - m_{ij} \cdot F_j$, y se almacena cada multiplicador en la matriz $L$: $l_{ij} = m_{ij}$.
#### **Paso 3: Ensamblar el resultado final**
- La matriz $A$, tras finalizar todas las operaciones y permutaciones de la eliminación, se convierte en nuestra matriz **$U$**.
- La matriz $P$ ha registrado el orden final acumulado de todos los intercambios de filas.
- La matriz $L$ contiene los multiplicadores ordenados de manera correspondiente.
- Se da por concluida la descomposición bajo la regla general: $P \cdot A = L \cdot U$.