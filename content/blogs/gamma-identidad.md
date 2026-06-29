---
title: "The Reflection Identity of the Gamma Function via Complex Integration"
date: 2026-02-15T23:35:59-06:00
draft: false
math: true
tikz: true
---
The reflection identity of the gamma function is: 

\begin{equation}
		 \Gamma( z )  \Gamma( 1-z )  = \frac{\pi}{\sin( \pi z ) } 
\end{equation}

We can start from the definition of $\beta( 1- \alpha,  \alpha ) $ 

\begin{align}
		 \Gamma( 1- \alpha )  \Gamma(  \alpha ) &= \beta (  1- \alpha,  \alpha ) = \int^\infty_0 \frac{t ^{1- \alpha-1}dt}{( 1+ t  )^{1- \alpha+ \alpha} } \\\
		 &= \int^\infty_0 \frac{t ^{-\alpha} dt}{1 + t} \\\
		 &= \int^\infty_{-\infty} \frac{e ^{-\alpha x} e^x dx}{1+ e^x} = \int^\infty_{-\infty} \frac{e ^{( 1-\alpha )x }}{ 1 + e^{x}} = I
\end{align}

where we used the substitution $t=e^x$, so $dt = e^xdx$ with limits $t=0 \implies x=-\infty$ and $t=\infty\implies x=\infty $. 
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

Now let us integrate over the rectangular contour $C_R$ with vertices $-R, R, R + 2\pi i , - R + 2\pi i$:


\begin{align}
	\oint_{C_R} \frac{e ^{( 1-\alpha ) z} dz}{1 + e^z}	&= \int^R_{-R} \frac{\exp( ( 1- \alpha ) x ) dx}{1 + e^x} + \int ^{2\pi}_0 \frac{\exp( ( 1-\alpha ) ( R+iy )  ) dx}{1 + \exp( R+i y ) } +\\\
	&+ \int^{-R}\_{R} \frac{\exp( ( 1- \alpha ) ( x+2\pi i ) ) dx}{1 + \exp( x + 2\pi i ) } + \int ^{0}\_{2\pi i} \frac{\exp( ( 1-\alpha ) ( -R+iy ) ) dy}{1 + \exp( -R+iy ) }
\end{align}

Let us evaluate the limit $R\to\infty$ of the integrands along the sides parallel to the imaginary axis. For the first one we notice that the limit is an indeterminate form $\infty/\infty$, so we can apply L'Hôpital's rule

\begin{align}
\lim_{R \to \infty} \frac{\exp( ( 1- \alpha ) R ) \exp( ( 1- \alpha ) iy ) }{1 + \exp( R ) \exp( iy ) } &=\lim_{R \to \infty}  \frac{( 1-\alpha ) \exp( ( 1-\alpha ) R ) \exp( ( 1-\alpha ) iy ) }{\exp( R ) \exp( iy ) } \\\
		&=\lim_{R \to \infty}  ( 1-\alpha ) \exp( -\alpha  R ) \exp(-\alpha  iy ) = 0
\end{align}

for the second integrand it is only a matter of simplification

\begin{align}
		\lim_{R \to \infty} \frac{\exp( ( \alpha -1 ) R ) \exp( ( 1- \alpha ) iy ) }{1 + \exp( -R ) \exp( iy ) } &=  \frac{\lim_{R \to \infty} \exp( ( \alpha -1) R ) \exp( ( 1-\alpha ) iy ) }{\lim_{R \to \infty}  1 +\exp( -R ) \exp( iy ) } \\\
		&=\lim_{R \to \infty}  \exp( \alpha  R ) \exp(-\alpha  iy ) = 0
\end{align}

which also vanishes since we assume $\alpha-1<0$.
So when we take the limit in the contour integral we get

\begin{align}
		\lim_{R \to \infty} \oint \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } &= \lim_{R \to \infty} \left\lbrace \int^R_{-R} \frac{\exp( ( 1- \alpha ) x ) dx}{1 + e^x} + \int^{-R} \_{R} \frac{\exp( ( 1- \alpha ) ( x+2\pi i )  ) dx}{1 + \exp( x + 2\pi  i) } \right\rbrace  \\\
&=   \int^\infty_{-\infty} \frac{\exp( ( 1- \alpha ) x ) dx}{1 + e^x} - \int^\infty_{\infty} \frac{\exp( ( 1- \alpha ) x) \exp(( 1- \alpha )   2\pi i  ) dx}{1 + \exp( x ) \exp( 2\pi i )  }  \\\
&= ( 1- \exp( ( 1- \alpha ) 2\pi i )  )  \int ^\infty_{-\infty} \frac{\exp( (   1- \alpha )x ) }{1 + \exp( x ) } \\\
&= [ 1 - \exp( ( 1-  \alpha )2\pi i  )  ] I 
\end{align}

with this equality we can evaluate the contour using the residue theorem

\begin{align}
		\lim_{R \to \infty} \oint \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } &=  2\pi i\sum_k \text{Res}\left(  \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } , z_k \right) 
\end{align}

It is easy to see there is only one simple pole $z_0$ inside the contour, given by $1 + \exp( z )= 0  \implies z_0= i\pi$. We evaluate its residue with L'Hôpital's rule

\begin{align}
		\text{Res}\left(  \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } , i\pi \right) &=  \lim_{z \to i \pi} ( z-i\pi )  \frac{\exp( ( 1- \alpha ) z ) }{1 + \exp( z ) } \\\
		&= \lim_{z \to i\pi}  \frac{\exp( ( 1-\alpha )z  ) + ( z- i\pi )  ( 1- \alpha ) \exp( ( 1- \alpha ) z )  }{\exp( z ) } \\\
		&= \frac{e ^{i\pi} e ^{-\alpha \pi i}}{e^{i\pi}} = e ^{- \alpha \pi i}.
\end{align}

We can now solve for the integral of interest $I$

\begin{align}
		I &= \frac{ 2\pi i e ^{- \alpha \pi i}}{1- e ^{2\pi i} e^{- \alpha \pi i}} = \pi \frac{2i }{e ^{ \alpha \pi i} - e ^{- \alpha \pi i}} \\\
		  &= \frac{\pi}{\sin( \pi \alpha ) } \\\
		\therefore  \Gamma(  \alpha )  \Gamma( 1 -  \alpha )  &= \frac{\pi}{\sin( \pi z ) } .
\end{align}


