> Es el marco teórico utilizado para resolver sistemas lineales del tipo $Ax = b$ que están **sobredeterminados** (tienen más ecuaciones que incógnitas) y no tienen una solución exacta compatible.

- **Mínimos Cuadrados:** Consiste en hallar un vector aproximado $\hat{x}$ que minimice la norma del error residual. Es decir, minimiza la distancia geométrica entre el resultado real y el ideal:
    $$\min_{x} \|Ax - b\|_2$$
    
    Se resuelve matemáticamente hallando la solución a las llamadas **Ecuaciones Normales**: $A^T A \hat{x} = A^T b$.
    
- **Matriz Pseudoinversa de Moore-Penrose ($A^\dagger$):** Es la generalización de la matriz inversa para matrices que no son cuadradas o que no tienen inversa distributiva. Si realizamos la descomposición SVD de una matriz ($A = U \Sigma V^T$), su pseudoinversa se define calculando la recíproca de los valores singulares no nulos dentro de $\Sigma$:
    
    $$A^\dagger = V \Sigma^\dagger U^T$$
    
    Permite escribir analíticamente la solución óptima de mínimos cuadrados de manera directa como: $\hat{x} = A^\dagger b$.