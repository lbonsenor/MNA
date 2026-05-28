El teorema de factorización LU establece que si una matriz cuadrada $A$ de dimensiones $n \times n$ puede ser reducida a su forma escalonada superior **sin necesidad de realizar intercambios de filas**, entonces dicha matriz se puede descomponer de forma única como el producto de dos matrices:
$$A = L \cdot U$$

Donde:
- **$U$ (Upper):** Es una matriz **triangular superior** de $n \times n$ (con todos sus elementos por debajo de la diagonal principal iguales a cero). Es exactamente la matriz resultante tras aplicar la eliminación gaussiana clásica.
- **$L$ (Lower):** Es una matriz **triangular inferior unitaria** de $n \times n$. "Unitaria" significa que todos los elementos situados en su diagonal principal son exactamente iguales a **$1$**. Los espacios por debajo de la diagonal se rellenan con los _multiplicadores_ empleados durante la eliminación gaussiana.
    
### Pasos Generales para construir la Factorización LU
#### **Paso 1: Configurar las matrices iniciales**
- Se parte de la matriz cuadrada original $A$.
- Se inicializa la matriz $U$ como una copia exacta de $A$ (sobre la cual realizaremos las operaciones de fila).
- Se inicializa la matriz $L$ como una **matriz identidad** ($I$) del mismo tamaño que $A$ (una matriz con unos en la diagonal principal y ceros en el resto).

#### **Paso 2: Aplicar eliminación Gaussiana para hacer ceros bajo la diagonal**
Se procede columna por columna (desde la columna $j=1$ hasta la columna $n-1$) eliminando las entradas que se encuentren por debajo de la diagonal principal en la matriz $U$.
Para cada fila $i$ debajo de la fila del pivote $j$ (es decir, para toda fila $i > j$):
1. **Calcular el multiplicador ($m_{ij}$):** Es el valor numérico por el cual se debe multiplicar la fila del pivote para anular el elemento deseado. Se define formalmente como:
$$m_{ij} = \frac{u_{ij}}{u_{jj}}$$
    - _Propiedad/Condición crítica:_ El elemento de la diagonal $u_{jj}$ se denomina **pivote**. Para poder calcular el multiplicador, el pivote **no puede ser cero ($u_{jj} \neq 0$)**. Si algún pivote es cero, la factorización LU clásica no es posible y se requiere obligatoriamente aplicar pivoteo (Factorización PLU).

2. **Modificar la fila en la matriz $U$:** Se efectúa la operación elemental de fila reemplazando la fila $i$ por la resta de sí misma con el multiplicador por la fila del pivote:
$$F_i \leftarrow F_i - m_{ij} \cdot F_j$$
3. **Registrar el multiplicador en la matriz $L$:** El multiplicador exacto $m_{ij}$ calculado se guarda directamente en la posición de la fila $i$ y columna $j$ dentro de la matriz $L$:
$$l_{ij} = m_{ij}$$
#### **Paso 3: Conclusión de las matrices**
- Una vez procesadas todas las columnas inferiores, la matriz $U$ habrá quedado completamente en forma **triangular superior**.
- La matriz $L$ habrá recolectado todos los multiplicadores por debajo de sus unos diagonales, quedando en forma **triangular inferior**.
- Se verifica el teorema: $A = L \cdot U$.