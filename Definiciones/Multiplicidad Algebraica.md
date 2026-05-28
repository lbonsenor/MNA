La **multiplicidad algebraica** de un autovalor $\lambda$ es la cantidad de veces que ese autovalor aparece como raíz en el polinomio característico de la matriz.
- **¿De dónde sale?** Al calcular el polinomio característico mediante el determinante $\det(A - \lambda I) = 0$, obtienes una ecuación polinómica. Al factorizarla por completo, toma la forma:
$$P(\lambda) = (\lambda - \lambda_1)^{m_1}(\lambda - \lambda_2)^{m_2}\dots$$
El exponente al que está elevado cada binomio es su multiplicidad algebraica.
    
- **Significado práctico:** Te dice cuántas veces está "repetido" un autovalor desde el punto de vista puramente matemático o algebraico.
- **Ejemplo:** Si tu polinomio característico da $P(\lambda) = (\lambda - 3)^2(\lambda + 1)$, entonces:
    - El autovalor $\lambda = 3$ tiene una multiplicidad algebraica de **$2$**.
    - El autovalor $\lambda = -1$ tiene una multiplicidad algebraica de **$1$**.