---
title: "La identidad de la reciproca de la gamma por integración compleja"
date: 2026-02-15T23:35:59-06:00
draft: false
math: true 
---
 Demuestre la reflectividad de la función gamma
				\begin{equation}
						 \Gamma( z )  \Gamma( 1-z )  = \frac{\pi}{\sin( \pi z ) } 
				\end{equation}
				Podemos partir desde la definición de la $\beta( 1- \alpha,  \alpha ) $ 
				\begin{align}
						 \Gamma( 1- \alpha )  \Gamma(  \alpha ) &= \beta (  1- \alpha,  \alpha ) = \int^\infty_0 \frac{t ^{1- \alpha-1}dt}{( 1+ t  )^{1- \alpha+ \alpha} } \\
						 &= \int^\infty_0 \frac{t ^{-\alpha} dt}{1 + t} \\
						 &= \int^\infty_{-\infty} \frac{e ^{-\alpha x} e^x dx}{1+ e^x} = \int^\infty_{-\infty} \frac{e ^{( 1-\alpha )x }}{ 1 + e^{x}} = I
				\end{align}
				donde usamos la sustitución $t=e^x$ entonces $dt = e^xdx$ con límites $t=0 \implies x=\infty$ y $t=\infty\implies x=\infty $. 
<script type="text/tikz">
  \begin{tikzpicture}
    \draw (0,0) circle (1in);
  \end{tikzpicture}
</script>

<script type="text/tikz">
	\begin{tikzpicture}[decoration={markings,
    mark=at position 1cm   with {\arrowreversed[line width=2pt]{stealth}},
    mark=at position 4.5cm with {\arrowreversed[line width=2pt]{stealth}},
    mark=at position 7cm   with {\arrowreversed[line width=2pt]{stealth}},
    mark=at position 9.5cm with {\arrowreversed[line width=2pt]{stealth}}
  }]
  \draw[thick, ->] (-3,0) -- (3,0) coordinate (xaxis);

  \draw[thick, ->] (0,0) -- (0,3) coordinate (yaxis);

  \filldraw[red] (0,1) circle (2pt);

  \node[above] at (xaxis) {$\mathrm{Re}(z)$};

  \node[right]  at (yaxis) {$\mathrm{Im}(z)$};

  \path[draw,blue, line width=1pt, postaction=decorate]
        (-2,2)
    --  (2, 2)  node[midway, above right, black] {$C_R$} node[above, black] {$R+2\pi i$} 
	--  (2, 0)  node[midway, right, black] {} node[below, black] {$R$}     
	--  (-2,0)  node[midway, below, black] {} node[below, black] {$-R$}
	--  (-2,2)  node[midway, left, black] {} node[above, black]{$-R+2\pi i$};
\end{tikzpicture} 
</script>
				Ahora realicemos la integración sobre el contorno rectangular $C_R$ con vértices $-R, R, R + 2\pi i , - R + 2\pi i$
				\begin{align}
					\oint_{C_R} \frac{e ^{( 1-\alpha ) z} dz}{1 + e^z}	&= \int^R_{-R} \frac{\exp( ( 1- \alpha ) x ) dx}{1 + e^x} + \int ^{2\pi}_0 \frac{\exp( ( 1-\alpha ) ( R+iy )  ) dx}{1 + \exp( R+i y ) } +\\
																		&+ \int^{-R}_{R} \frac{\exp( ( 1- \alpha ) ( x+2\pi i )  ) dx}{1 + \exp( x + 2\pi i ) } + \int ^{0}_{2\pi i} \frac{\exp( ( 1-\alpha ) ( -R+iy )  ) dx}{1 + \exp( -R+i y ) } 
				.\end{align}
				Evaluemos el límite de $R\to\infty$ de los integrandos que van paralelos al eje imaginario. El primero notamos que al evaluar el límite tenemos una indefinición cociente de infinitos, así que podemos usar la regla de l'Hopital
				\begin{align}
						\lim_{R \to \infty} \frac{\exp( ( 1- \alpha ) R ) \exp( ( 1- \alpha ) iy ) }{1 + \exp( R ) \exp( iy ) } &=\lim_{R \to \infty}  \frac{( 1-\alpha ) \exp( ( 1-\alpha ) R ) \exp( ( 1-\alpha ) iy ) }{\exp( R ) \exp( iy ) } \\
																																&=\lim_{R \to \infty}  ( 1-\alpha ) \exp( -\alpha  R ) \exp(-\alpha  iy ) = 0
				\end{align}
				para el segundo integrando es solamente simplificar y evaluar
				\begin{align}
						\lim_{R \to \infty} \frac{\exp( ( \alpha -1 ) R ) \exp( ( 1- \alpha ) iy ) }{1 + \exp( -R ) \exp( iy ) } &=  \frac{\lim_{R \to \infty} \exp( ( \alpha -1) R ) \exp( ( 1-\alpha ) iy ) }{\lim_{R \to \infty}  1 +\exp( -R ) \exp( iy ) } \\
																																&=\lim_{R \to \infty}  \exp( \alpha  R ) \exp(-\alpha  iy ) = 0
				\end{align}
resulta igualmente en cero dado que suponemos  $\alpha-1<0$. 
De modo tal que cuando evaluamos el límite en la intrgral de contorno tenemos
\begin{align}
		\lim_{R \to \infty} \oint \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } &= \lim_{R \to \infty} \left\{  \int^R_{-R} \frac{\exp( ( 1- \alpha ) x ) dx}{1 + e^x} + \int^{-R}_{R} \frac{\exp( ( 1- \alpha ) ( x+2\pi i )  ) dx}{1 + \exp( x + 2\pi  i) }   \right\} \\
																				  &=   \int^\infty_{-\infty} \frac{\exp( ( 1- \alpha ) x ) dx}{1 + e^x} - \int^{\infty}_{-\infty} \frac{\exp( ( 1- \alpha ) x) \exp(( 1- \alpha )   2\pi i  ) dx}{1 + \exp( x ) \exp( 2\pi i )  }  \\
																				  &= ( 1- \exp( ( 1- \alpha ) 2\pi i )  )  \int ^\infty_{-\infty} \frac{\exp( (   1- \alpha )x ) }{1 + \exp( x ) } \\
																				 &= [ 1 - \exp( ( 1-  \alpha )2\pi i  )  ] I \\
\end{align}
con esta igualdad podemos evaluar el contorno con el teorema del residuo
\begin{align}
		\lim_{R \to \infty} \oint \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } &=  2\pi i\sum_k \text{Res}\left(  \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } , z_k \right) 
\end{align}
que es fácil ver que solamente hay un polo simple $z_0$ dentro del contorno dado por $1 + \exp( z )= 0  \implies z_0= i\pi$, evaluemos su residuo con l'Hopital
\begin{align}
		\text{Res}\left(  \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } , i\pi \right) &=  \lim_{z \to i \pi} ( z-i\pi )  \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } \\
																						 &= \lim_{z \to i\pi}  \frac{\exp( ( 1-\alpha )z  ) + ( z- i\pi )  ( 1- \alpha ) \exp( ( 1- \alpha ) z )  }{\exp( z ) } \\
																						 &= \frac{e ^{i\pi} e ^{-\alpha \pi i}}{e^{i\pi}} = e ^{- \alpha \pi i}.
\end{align}
Así podemos despejar la integral de interes $I$  como
\begin{align}
		I &= \frac{ 2\pi i e ^{- \alpha \pi i}}{1- e ^{2\pi i} e^{- \alpha \pi i}} = \pi \frac{2i }{e ^{ \alpha \pi i} - e ^{- \alpha \pi i}} \\
		  &= \frac{\pi}{\sin( \pi \alpha ) } \\
		\therefore  \Gamma(  \alpha )  \Gamma( 1 -  \alpha )  &= \frac{\pi}{\sin( \pi z ) } .
\end{align}
<script type="text/tikz">
  \begin{tikzpicture}
    \draw (0,0) circle (1in);
  \end{tikzpicture}
</script>
