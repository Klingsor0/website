---
title: "La forma de una transformada de Lorentz general por generadores"
date: 2026-02-12T15:52:52-06:00
draft: false
---

En el presente documento daremos solución a la tarea siguiendo el capítulo 11 del Jackson Tercera Edición, el cuál hace uso de las propiedades matemáticas del espacio tiempo de Minkowski. 
Se realizarán precisiones donde falten en el libro con apoyo de argumentos originales.

Sea $\mathcal{M}$ un espacio tiempo de Minkowski, pensemos en él como el espacio tiempo físico,  sean  $x: \mathcal{M} \to \mathbb{R}^4$ y $x': \mathcal{M} \to \mathbb{R}^4$ cartas que mandan eventos de este espacio tiempo a un espacio vectorial de Minkowski. 
Deseamos una aplicación lineal $A$ que tome componentes $x_i$ y las mande las componentes  $x'_i$
$$Ax =x'$$
siendo sobre y uno a uno, además lineal, pero sobre todo que preserve la estructura del espacio tiempo.
Esto último es que el intervalo espacio tiempo se preserve, definido del siguiente modo:
Siendo $V$ un espacio vecotorial Minkowski existe un isomorfismo $\overline{g}$ entre el $V$ y su dual $V^*$ $\overline{g}: V \to V^*$ tal que si tomamos las bases canónicas de ambas se cumple la siguiente relación
$$
\overline{g}(e_i) = e^i \forall i \neq 0
$$ 
$$\overline{g}(e_0) = - e^0$$
denotemos como $(u, v)$ a la aplicación del covector  $u \in V^*$ sobre el vector $v \in V$, su evaluación $(u,u)$ es el intervalo espacio tiempo del evento  $u$. 
Dada esta aplicación bilineal simetrica existe una forma cuadrática a través de una matriz $g$ tal que
\[
u^T g v = (\overline{g}(u), v)
.\] 
Dado el isomorfismo $\overline{g}$, la matriz $g$ debe ser de la forma
$$g = \begin{pmatrix} -1 & & & \\ & 1 & & \\ & & 1 & \\ & & & 1 \end{pmatrix} $$
y las transformaciones de Lorentz dadas la forma cuadrática satisfacen
\begin{equation}
x^T g x = x'^T g x' \implies (Ax)^T g (Ax) = xg x \implies A^T g A = g
\label{lorentz}
\end{equation}
De aquí observamos la primera propiedad, y es que 
$$det(A^T g A) det(A^T) det(g) det(A)= det(g)$$
 $$\implies det(A^T) det(A) = det(A)^2= 1 \implies det(A) = \pm 1$$
  Dado a que consideraremos únicamente transformaciones propias de Lorentz restringimos $det(A) = 1$, esto no es más que definir una orientación.
  De \eqref{lorentz} tenemos que los coeficientes de la matriz $g$ cumplen el siguiente sistema de ecuaciones 
  $$a_{ij} g_{jl} a_{lk} = g_{ik}$$
  la simetría de la matriz $g$ reduce el número de ecuaciones independientes de 16 a 10
   lo cuál nos da una forma de coordenar a las componentes con 6 números.
   3 de ellos son ángulos para rotaciones espaciales ordinarias, los otros tres de los boosts o rotaciones hiperbólicas de los que principalmente estamos interesados.
   En esta solución usaremos al generador $L$ para  $A$
   $$A = e^L$$ 
   indaguemos en sus propiedades.
   Sabemos que el determinante  de $A$ es unitario así que se debe cumplir
   $$det(A) = e^{trL} =1 \implies trL =0 $$ 
   recordemos que la traza de una matriz es la suma de los valores característicos de esta, por tanto si llegasemos a suponer que $L$ es solamente boost sus eigenvalores son tres $\lambda_i$ y cumplen  
   \begin{equation}
    \lambda_1 + \lambda_2 + \lambda_3 =0. 
	\label{eigen}
   \end{equation}
	Manipulemos un poco la ecuación (1) a sabiendas de que $g^2=I$
$$A^TgA A^{-1}g = g A ^{-1}g \implies A^T = gA ^{-1}g$$	
tomando la definición del generador
\[
		A^T= e^{L^T} \implies gA^Tg = e^{g L^Tg} \implies g^2 A^{-1} g^2 = A^{-1}= e^{g L^T g} \implies e^{-L} = e^{g L^T g}
.\] 
Esto nos da la siguiente propiedad
\begin{equation}
- gL = gg L ^T g = L^T g = (gL)^T 
\label{antisimetria}
\end{equation}
quiere decir que $gL$ es anti simétrica i.e $(gL)_{ij} = - (gL)_{ji}$, analicemos indicialmente esta ecuación.
Expandamos
\begin{align*}
		(gL)_{ij} = g_{il} L_{lj} i&= - g_{jl} L_{li} \\
\implies g_{ii} L_{ij} &= - g_{jj} L_{ji}  \\
\text{si i=0, j=0: } g_{00}  L_{00} &= -g_{00} L_{00} \\
\implies -L_{00} &= -(-1) L_{00} \implies L_{00} = 0\\
\text{ si } i=0 j\neq 0: \ g_{00} L_{0j} &= - g_{jj} L_{j_0} \implies -L_{0j} = - L_{j_0}\\ 
\text{si \ } i\neq 0, j \neq 0: \ g_{ii} L_{ij} &= - g_{jj} L_{ji} \implies L_{ij} = -L_{ji} 
.\end{align*}
Por lo cuál $L$ es de la forma
\[
		L = \begin{pmatrix} 0 & L_{01} & L_{02} & L{03} \\ 
		L_{01} & 0 & L_{12} L_{13} \\ 
L_{02} & -L_{12} & 0 & L_{23} \\
L_{03} & - L_{13} & -L_{23} & 0 \end{pmatrix} 
.\] 
Sabemos que dentro de las posibles transformaciones que incluye la forma general de $L$ están las rotaciones espaciales ordinarias que satisfacen
$A A^T = I \implies L^T = -L$ por tanto ignoraremos las partes anti simétricas de esta forma general.
Por lo tanto los generadores del grupo de rotaciones hiperbólicas en un espacio de Minkowski es el siguiente
\[
		K_1 = \begin{pmatrix} 0 & 1 & 0 & 0 \\ 1& 0 & & \\ 0 & & 0 & \\ 0 &  & &  \end{pmatrix} , \ \ \ 
		K_2 = \begin{pmatrix} 0 & 0 & 1 & 0 \\ 0& & & \\ 1 & & & \\ 0 & & &  \end{pmatrix} , \ \ \ 
		K_2 = \begin{pmatrix} 0 & 0 & 0 & 1 \\ 0& & & \\ 0 & & & \\ 1 & & &  \end{pmatrix}  \ \ \ 
.\] 
Denotaremos a $\epsilon \cdot  K$ como una combinación lineal de las matrices esto es $\epsilon = \epsilon_1 K_1 + \epsilon_2 K_2 + \epsilon_3 K_3$.
Si $\epsilon$ es un vector unitario, se cumple la siguiente igualdad $(\epsilon \cdot K)^3 = \epsilon \cdot K$. 
Esta propiedad se sostiene dado que los eigenvalores de una matriz cúbicamente idempotente son de la siguiente manera. Sea $F$ una matriz cúbicamente idempotente, supongamos que es diagonalizable
\begin{align*}
		Fv &= \lambda v \\
		F^3 v &= \lambda^3 v \implies \lambda^3 = \lambda\\
		\lambda(\lambda^2 -1) &= 0
\end{align*}
en conclusión una matriz cúbica idempotente tiene sus eigen valores son unitarios positivo, negativo o nulo. 

Veamos el caso particular de nuestra matriz $L$, con ayuda de \eqref{antisimetria} si calculamos su determinante tenemos
$$det (gL^T) = det(-gL)$$
 $$\implies det(L) = - det(L) \implies det(L) =0$$
  por lo tanto $L$ tiene al menos un eigenvalor nulo $\lambda_1=0$. 
  Veamos el caso aún más particular de $\epsilon \cdot  K$, es fácil ver que tiene el siguiente eigen vector
  \[
		  \begin{pmatrix} 0 & \epsilon_1 & \epsilon_2 & \epsilon_3 \\ \epsilon_1 & & & \\ \epsilon_2 & & & \\ \epsilon_3 & & & \end{pmatrix} \begin{pmatrix} 1 \\ \epsilon_1 \\ \epsilon_2 \\ \epsilon_3 \end{pmatrix} = \begin{pmatrix} \epsilon_1^2 + \epsilon_2^2 + \epsilon_3^2 \\ \epsilon_1 \\ \epsilon_2 \\ \epsilon_3 \end{pmatrix}  = 
\begin{pmatrix} 1 \\ \epsilon_1 \\ \epsilon_2 \\ \epsilon_3 \end{pmatrix} 
  \] 
  con eigen valor $\lambda_2 =1$, por \eqref{eigen} $\lambda_3=-1$. Así acabamos de demostrar que $\epsilon \cdot K$ es cúbicamente idempotente cuando $\epsilon$ sea unitario.
Esto nos será de fundamental ayuda a la hora de realizar la expansión exponencial.
Sea $\beta = \frac{v}{c}$ tal que $\hat{\beta}= \begin{pmatrix} \frac{\beta_1}{\beta}, \frac{\beta_2}{\beta}, \frac{\beta_3}{\beta} \end{pmatrix} $ la dirección, dado que es unitario, de la velocidad relativa de un marco de referencia a otro.
Nuestro boost general es de la forma
$$A = \exp(-\hat{\beta}\cdot K \tanh^{-1}\left( \beta \right) )$$
donde $\tanh ^{-1} \beta$ es el ángulo de rotación hiperbólica. 
Expandamos en series
\begin{align*}
		 \exp(-\tanh^{-1}\left( \beta \right) \hat{\beta} \cdot K ) &= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \tanh ^{-1} (\beta)\right)^n }{n!} \\
&= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
 \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} \\
&= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \right)^{2n+1} \left( \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
\sum_{n=1}^{\infty} \frac{\left( - \hat{\beta} \cdot K\right)^{2n} \left(\tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} + \\
& + (-\hat{\beta}\cdot K \tanh ^{-1} \beta)^0 + (\hat{\beta} \cdot K)^2 - (\hat{\beta} \cdot K)^2 \\
&= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \right) \left( \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
\sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K\right)^{2} \left(\tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} + I - (\hat{\beta} \cdot K)^2\\
&= \left( - \hat{\beta} \cdot K \right)\sum_{n=0}^{\infty} \frac{ \left( \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
 \left(  \hat{\beta} \cdot K\right)^{2}\sum_{n=0}^{\infty} \frac{ \left(\tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} + I - (\hat{\beta} \cdot K)^2\\
&= \left( - \hat{\beta} \cdot K \right)\sinh(\tanh ^{-1}\beta) +
 \left(  \hat{\beta} \cdot K\right)^{2} \cosh(\tanh ^{-1} \beta) + I - (\hat{\beta} \cdot K)^2\\
.\end{align*}
evaluemos los términos que tenemos aquí. Primeramente recurrimos a las definiciones logarítmicas y exponenciales del funciones trigonométricas hiperbólicas.
El seno y coseno hiperbólico de $\tanh ^{-1} (\beta) = \frac{1}{2} \ln\left( \frac{1+ \beta}{1-\beta} \right) $ es 
\begin{align*}
		\sinh \left( \tanh ^{-1} \beta \right) &= \frac{1}{2} \left\{ \exp \left( \ln \sqrt{\frac{1+ \beta}{1-\beta}} \left) - \exp \left( \ln \sqrt{\frac{1- \beta}{1+\beta}} \right)  \right\}  \\
				&= \frac{1}{2} \left( \frac{\sqrt{(1+ \beta)^2} - \sqrt{(1-\beta)^2}  }{\sqrt{1-\beta^2}  } \right) = \frac{1}{2} \left(\frac{1+\beta -1 +\beta}{\sqrt{1-\beta ^2} }  \right)  \\
				&= \gamma \beta\\
		\cosh \left( \tanh ^{-1} \beta \right) &= \frac{1}{2} \left\{ \exp \left( \ln \sqrt{\frac{1+ \beta}{1-\beta}} \left) + \exp \left( \ln \sqrt{\frac{1- \beta}{1+\beta}} \right)  \right\}  \\
				&= \frac{1}{2} \left( \frac{\sqrt{(1+ \beta)^2} - \sqrt{(1-\beta)^2}  }{\sqrt{1-\beta^2}  } \right) = \frac{1}{2} \left(\frac{1+\beta +1 -\beta}{\sqrt{1-\beta ^2} }  \right)  \\
				&= \gamma 
.\end{align*}
Por lo cuál la transformación queda de la siguiente manera
$$A = - \hat{\beta} \cdot K \gamma \beta + \left( \hat{\beta} \cdot K \right)^2 (\gamma - 1) + I $$
sencillamente falta evaluar el valor matricial $\hat{\beta}\cdot K$ y su cuadrático
\begin{align*}
		\hat{\beta} \cdot K &= \frac{1}{\beta} \left( \beta_1 K_1 + \beta_2 K_2 + \beta_3 K_3 \right) \\
							&= \frac{1}{\beta} \begin{pmatrix} 0 & \beta_1 & \beta_2 & \beta_3 \\ \beta_1 & & & \\ \beta_2 & & & \\ \beta_3 & & &  \end{pmatrix}  \\
		\implies (\hat{\beta} \cdot K)^2 &= \frac{1}{\beta^2} \begin{pmatrix} \beta_1^2 + \beta_2^2 + \beta_3^2 & 0 & 0& 0 \\ 0 & \beta_1^2 & \beta_1 \beta_2 & \beta_1\beta_3 \\ 0 & \beta_1\beta_2 & \beta_2^2 & \beta_2 \beta_3 \\ 0 & \beta_1\beta_3 & \beta_2 \beta_3  & \beta_3^2\end{pmatrix}  \\
.\end{align*}
sustituyamos en la expresión para $A$ y tenemos
\begin{align*}
		A &= - \frac{\gamma \beta}{\beta}  \begin{pmatrix} 0 & \beta_1 & \beta_2 & \beta_3 \\ \beta_1 & & & \\ \beta_2 & & & \\ \beta_3 & & &  \end{pmatrix}  + 
		\frac{\gamma - 1}{\beta^2}    \begin{pmatrix} \beta_1^2 + \beta_2^2 + \beta_3^2 & 0 & 0& 0 \\ 0 & \beta_1^2 & \beta_1 \beta_2 & \beta_1\beta_3 \\ 0 & \beta_1\beta_2 & \beta_2^2 & \beta_2 \beta_3 \\ 0 & \beta_1\beta_3 & \beta_2 \beta_3  & \beta_3^2\end{pmatrix}   +I\\
		&=  
		  \begin{pmatrix}\gamma-1 & -\beta_1 \gamma & -\beta_2 \gamma& -\beta_3 \gamma \\ -\beta_1 \gamma & \beta_1^2\frac{\gamma -1}{\beta} & \beta_1 \beta_2 \frac{\gamma -1}{\beta}& \beta_1\beta_3 \frac{\gamma -1}{\beta}\\ -\beta_2\gamma & \beta_1\beta_2 \frac{\gamma -1}{\beta}& \beta_2^2 \frac{\gamma -1}{\beta}& \beta_2 \beta_3 \frac{\gamma -1}{\beta}\\ -\beta_3 \gamma & \beta_1\beta_3 \frac{\gamma -1}{\beta}& \beta_2 \beta_3 \frac{\gamma -1}{\beta} & \beta_3^2\frac{\gamma -1}{\beta} \end{pmatrix}   +I\\
								  &=	   \begin{pmatrix} \gamma -1 + 1 & -\gamma \beta_1 & -\gamma_2 \beta_2& -\gamma \beta_3 \\ \gamma \beta_1 & 1+ (\gamma -1)\frac{\beta_1^2}{\beta} &(\gamma -1) \beta_1 \beta_2 & (\gamma -1)  \frac{\beta_1\beta_3 }{\beta} \\ -\gamma \beta_2 & \frac{\gamma -1}{\beta} & 1+(\gamma - 1) \frac{\beta_2^2}{\beta}  & \frac{\gamma -1 }{}\beta\\ -\gamma \beta_3 & (\gamma -1) \frac{\beta_1\beta_3}{\beta} & (\gamma -1) \frac{\beta_2 \beta_3}{\beta}  & 1 + (\gamma -1) \frac{\beta_3^2}{\beta}\end{pmatrix}   
.\end{align*}
Por lo tanto 
\[
	A=	   \begin{pmatrix} \gamma  & -\gamma \beta_1 & -\gamma_2 \beta_2& -\gamma \beta_3 \\ \gamma \beta_1 & 1+ (\gamma -1)\frac{\beta_1^2}{\beta} &(\gamma -1) \beta_1 \beta_2 & (\gamma -1)  \frac{\beta_1\beta_3 }{\beta} \\ -\gamma \beta_2 & \frac{\gamma -1}{\beta} & 1+(\gamma - 1) \frac{\beta_2^2}{\beta}  & \frac{\gamma -1 }{}\beta\\ -\gamma \beta_3 & (\gamma -1) \frac{\beta_1\beta_3}{\beta} & (\gamma -1) \frac{\beta_2 \beta_3}{\beta}  & 1 + (\gamma -1) \frac{\beta_3^2}{\beta}\end{pmatrix}   
.\] 


