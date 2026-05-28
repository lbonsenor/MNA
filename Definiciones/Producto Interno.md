> Es una operación bilineal que toma dos vectores de un espacio vectorial y devuelve un número escalar (en $\mathbb{R}$ o $\mathbb{C}$).

Formalmente, un producto interno sobre un espacio vectorial $V$ es una función $\langle \cdot, \cdot \rangle : V \times V \to \mathbb{R}$ que cumple con las siguientes cuatro propiedades fundamentales para cualesquiera vectores $u, v, w \in V$ y un escalar $\alpha \in \mathbb{R}$:

- **Simetría:** $\langle u, v \rangle = \langle v, u \rangle$
- **Linealidad en el primer componente:** $\langle u + v, w \rangle = \langle u, w \rangle + \langle v, w \rangle$ y $\langle \alpha u, v \rangle = \alpha \langle u, v \rangle$
- **Positividad:** $\langle u, u \rangle \geq 0$
- **No degeneración:** $\langle u, u \rangle = 0 \iff u = \vec{0}$
    
_El producto interno habitual en $\mathbb{R}^n$ es el producto escalar canónico: $u \cdot v = u^T v$._

Si $u = (u_1, u_2, \dots, u_n)$ y $v = (v_1, v_2, \dots, v_n)$, entonces:
$$\langle u, v \rangle = u_1 v_1 + u_2 v_2 + \dots + u_n v_n$$