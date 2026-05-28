La **multiplicidad geométrica** de un autovalor $\lambda$ es la dimensión del subespacio propio (autoespacio) asociado a ese autovalor.
- **¿De dónde sale?** Representa la cantidad máxima de autovectores linealmente independientes que puedes encontrar para ese autovalor en particular. Se calcula buscando la dimensión del núcleo (kernel) de la matriz armada $(A - \lambda I)$:
$$m_g(\lambda) = \dim(N(A - \lambda I))$$

- **Fórmula práctica de cálculo:** Para no complicarte buscando los vectores, puedes usar el Teorema de la Dimensión (Rango-Nulidad). Sabiendo que el tamaño de la matriz es $n \times n$:
$$m_g(\lambda) = n - \text{rango}(A - \lambda I)$$
    
- **Significado práctico:** Te dice cuántas direcciones (ejes geométricos independientes) en el espacio real se estiran bajo el factor de ese autovalor.