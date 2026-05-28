Cualquier matriz real $A$ de $m \times n$ con columnas linealmente independientes puede factorizarse como:
$$A = QR$$

Donde:
- **$Q$** es una matriz de $m \times n$ cuyas columnas son vectores **ortonormales** que generan el mismo espacio que las columnas de $A$.
- **$R$** es una matriz de $n \times n$ **triangular superior** (tiene un cero en la esquina inferior izquierda) e invertible.

#### Calculo
El procedimiento general más común para obtenerla se basa en el **Método de Ortogonalización de Gram-Schmidt** aplicado a las columnas de la matriz $A$. A continuación se describen los pasos generales:

### Paso 1: Identificar las columnas de la matriz original

Se toma la matriz $A$ y se separan sus columnas como vectores individuales:

$$A = \begin{pmatrix} c_1 & c_2 & c_3 & \dots & c_n \end{pmatrix}$$

### Paso 2: Ortogonalizar y normalizar secuencialmente (Proceso de Gram-Schmidt)

El objetivo de este paso es transformar el conjunto de columnas originales $\{c_1, c_2, \dots, c_n\}$ en un nuevo conjunto de vectores unitarios y perpendiculares entre sí $\{q_1, q_2, \dots, q_n\}$, los cuales conformarán las columnas de la matriz $Q$.

1. **Para la primera columna ($c_1$):**
    - Como no hay vectores previos, simplemente calculamos su longitud (norma euclidiana): $\|c_1\|$.
    - Dividimos el vector por su norma para hacerlo unitario. Este será nuestro primer vector de la matriz $Q$:
$$q_1 = \frac{c_1}{\|c_1\|}$$
2. **Para la segunda columna ($c_2$):**
    - Debemos retirar de $c_2$ cualquier componente que apunte en la misma dirección que $q_1$. Para ello, calculamos el producto escalar (proyección) entre ambos: $c_2 \cdot q_1$.
    - Obtenemos un vector remanente que llamaremos $v_2$, restando dicha proyección:
$$v_2 = c_2 - (c_2 \cdot q_1)q_1$$
    - Calculamos la norma de este nuevo vector: $\|v_2\|$.
    - Lo normalizamos para obtener el segundo vector de la matriz $Q$:$$q_2 = \frac{v_2}{\|v_2\|}$$
3. **Para las siguientes columnas ($c_k$):**
    - Se repite la misma lógica. A la columna actual $c_k$ se le restan sus proyecciones sobre **todos** los vectores $q$ que ya hayan sido calculados previamente:
$$v_k = c_k - (c_k \cdot q_1)q_1 - (c_k \cdot q_2)q_2 - \dots - (c_k \cdot q_{k-1})q_{k-1}$$
    - Se calcula su norma $\|v_k\|$ y se genera el vector unitario correspondiente:
$$q_k = \frac{v_k}{\|v_k\|}$$
### Paso 3: Construir la matriz $Q$
Una vez obtenidos todos los vectores unitarios corregidos $\{q_1, q_2, \dots, q_n\}$, simplemente los acomodamos lado a lado como las columnas de nuestra matriz $Q$:
$$Q = \begin{pmatrix} q_1 & q_2 & q_3 & \dots & q_n \end{pmatrix}$$

### Paso 4: Construir la matriz $R$
La matriz $R$ almacena las relaciones métricas (longitudes y proyecciones) encontradas durante el proceso de Gram-Schmidt. Debido a la forma en que se construyeron los vectores, todos los elementos por debajo de la diagonal principal se vuelven automáticamente cero, resultando en una estructura triangular superior:
$$R = \begin{pmatrix}

|c_1| & c_2 \cdot q_1 & c_3 \cdot q_1 & \dots & c_n \in q_1 \\

0 & |v_2| & c_3 \cdot q_2 & \dots & c_n \in q_2 \\

0 & 0 & |v_3| & \dots & c_n \in q_3 \\

\vdots & \vdots & \vdots & \ddots & \vdots \\

0 & 0 & 0 & \dots & |v_n|

\end{pmatrix}$$

- **En la diagonal principal:** Van las normas de los vectores calculados antes de ser normalizados ($\|c_1\|, \|v_2\|, \|v_3\|, \dots$).
- **Por encima de la diagonal:** Van los productos escalares de las columnas originales de $A$ proyectadas sobre los vectores unitarios de $Q$ ($c_j \cdot q_i$).
- **Por debajo de la diagonal:** Se completa con ceros.

Una vez estructuradas ambas matrices, se concluye con la igualdad $A = QR$.