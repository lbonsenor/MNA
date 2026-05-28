> Es una función que asigna un número real no negativo a cada vector de un espacio vectorial, representando intuitivamente su "longitud", "magnitud" o "tamaño".

Formalmente, una norma es una función $\|\cdot\| : V \to \mathbb{R}$ que cumple con:

- **No negatividad:** $\|u\| \geq 0$, y $\|u\| = 0 \iff u = \vec{0}$.
- **Homogeneidad absoluta:** $\|\alpha u\| = |\alpha| \cdot \|u\|$ para cualquier escalar $\alpha$.
- **Desigualdad triangular:** $\|u + v\| \leq \|u\| + \|v\|$.

> **Nota de conexión:** Todo producto interno _induce_ naturalmente una norma geométrica mediante la raíz cuadrada del producto interno del vector consigo mismo:
> $$\|u\| = \sqrt{\langle u, u \rangle}$$