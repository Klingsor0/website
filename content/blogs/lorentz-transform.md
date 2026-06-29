---
title: "General Lorentz Transformation via Group Generators"
date: 2026-02-12T15:52:52-06:00
draft: false
math: true
---

In this post we derive the functional form of a generic Lorentz transformation from its group generators.
At first glance I considered this trivial, as I was unaware of the role played by their non-commutativity — which made it an interesting exercise to present.
We follow Chapter 11 of Jackson (Third Edition), which makes use of the mathematical properties of Minkowski spacetime.
Clarifications missing from the book are supplied with original arguments.

Let $ \mathcal{M} $ be a Minkowski spacetime, thought of as physical spacetime, and let $ x: \mathcal{M} \to \mathbb{R}^4 $ and $ x': \mathcal{M} \to \mathbb{R}^4 $ be charts mapping events of this spacetime to a Minkowski vector space.
We seek a linear map $A$ that takes components $x_i$ to components $x^\prime_i$

\begin{equation}
Ax =x'
\end{equation}

being surjective and injective, linear, and above all preserving the spacetime structure.
This last condition means the spacetime interval is preserved, defined as follows:
For $V$ a Minkowski vector space there exists an isomorphism $\overline{g}$ between $V$ and its dual $V^\ast$, $\overline{g}: V \to V^\ast$, such that taking the canonical bases of both we have the relation

$$
\overline{g}(e_i) = e^i \forall i \neq 0
$$ 
$$\overline{g}(e_0) = - e^0$$

Denote by $(u, v)$ the action of the covector $u \in V^*$ on the vector $v \in V$; the evaluation $(u,u)$ is the spacetime interval of the event $u$.
Given this symmetric bilinear form there exists a quadratic form via a matrix $g$ such that

$$
u^T g v = (\overline{g}(u), v)
$$ 

Given the isomorphism $\overline{g}$, the matrix $g$ must take the form

$$g = \begin{pmatrix} -1 & & & \\ & 1 & & \\ & & 1 & \\ & & & 1 \end{pmatrix} $$

and Lorentz transformations given this quadratic form satisfy

\begin{equation}
x^T g x = x'^T g x' \implies (Ax)^T g (Ax) = xg x \implies A^T g A = g
\label{lorentz}
\end{equation}

From this we observe the first property, namely that 

$$det(A^T g A) det(A^T) det(g) det(A)= det(g)$$
 $$\implies det(A^T) det(A) = det(A)^2= 1 \implies det(A) = \pm 1$$

  Since we consider only proper Lorentz transformations we restrict to $det(A) = 1$, which is simply a choice of orientation.
  From \eqref{lorentz} the coefficients of $g$ satisfy the system of equations

  $$a_{ij} g_{jl} a_{lk} = g_{ik}$$

  The symmetry of $g$ reduces the number of independent equations from 16 to 10,
  which gives us a way to parameterize the components with 6 numbers.
  Three of them are angles for ordinary spatial rotations; the other three are for boosts (hyperbolic rotations), which are our primary interest.
  In this solution we use the generator $L$ for $A$

   $$A = e^L$$ 

   Let us investigate its properties.
   We know that the determinant of $A$ is unity, so we must have

   $$det(A) = e^{trL} =1 \implies trL =0 $$ 

   Recall that the trace of a matrix is the sum of its eigenvalues, so if we suppose that $L$ is a pure boost its three eigenvalues $\lambda_i$ satisfy 

   \begin{equation}
    \lambda_1 + \lambda_2 + \lambda_3 =0. 
	\label{eigen}
   \end{equation}

Let us manipulate equation (1) knowing that $g^2=I$

$$A^TgA A^{-1}g = g A ^{-1}g \implies A^T = gA ^{-1}g$$	

taking the definition of the generator

\begin{align*}
A^T &= e^{L^T} \implies gA^Tg = e^{g L^Tg} \\\
\implies g^2 A^{-1} g^2 &= A^{-1}= e^{g L^T g}\\\ 
\implies e^{-L} &= e^{g L^T g}
\end{align*}

This gives us the following property

\begin{equation}
-gL = gg L ^T g = L^T g = (gL)^T 
\label{antisimetria}
\end{equation}

meaning that $gL$ is anti-symmetric, i.e. $(gL)\_{ij} = -(gL)\_{ji}$. Let us analyze this equation index by index.
Expanding

\begin{align*}
		(gL)\_{ij} = g_{il} L_{lj} i&= - g_{jl} L_{li} \\\
\implies g_{ii} L_{ij} &= - g_{jj} L_{ji}  \\\
\text{si i=0, j=0: } g_{00}  L_{00} &= -g_{00} L_{00} \\\
\implies -L_{00} &= -(-1) L_{00} \implies L_{00} = 0\\\
\text{ si } i=0 j\neq 0: \ g_{00} L_{0j} &= - g_{jj} L_{j_0} \implies -L_{0j} = - L_{j_0}\\\
\text{si \ } i\neq 0, j \neq 0: \ g_{ii} L_{ij} &= - g_{jj} L_{ji} \implies L_{ij} = -L_{ji} 
.\end{align*}

Therefore $L$ takes the form

\[
		L = \begin{pmatrix} 0 & L_{01} & L_{02} & L{03} \\ 
		L_{01} & 0 & L_{12} & L_{13} \\ 
L_{02} & -L_{12} & 0 & L_{23} \\
L_{03} & - L_{13} & -L_{23} & 0 \end{pmatrix} 
.\] 

We know that among the transformations contained in the general form of $L$ are ordinary spatial rotations satisfying
$A A^T = I \implies L^T = -L$, so we discard the anti-symmetric parts of this general form.
The generators of the hyperbolic rotation group in Minkowski space are therefore

\[
		K_1 = \begin{pmatrix} 0 & 1 & 0 & 0 \\ 1& 0 & & \\ 0 & & 0 & \\ 0 &  & &  \end{pmatrix} , \ \ \ 
		K_2 = \begin{pmatrix} 0 & 0 & 1 & 0 \\ 0& & & \\ 1 & & & \\ 0 & & &  \end{pmatrix} , \ \ \ 
		K_2 = \begin{pmatrix} 0 & 0 & 0 & 1 \\ 0& & & \\ 0 & & & \\ 1 & & &  \end{pmatrix}  \ \ \ 
.\] 

We denote $\epsilon \cdot  K$ as a linear combination of the matrices, i.e. $\epsilon = \epsilon_1 K_1 + \epsilon_2 K_2 + \epsilon_3 K_3$.
If $\epsilon$ is a unit vector, then the equality $(\epsilon \cdot K)^3 = \epsilon \cdot K$ holds.
This follows from the eigenvalues of a cubically idempotent matrix. Let $F$ be a cubically idempotent matrix; assuming it is diagonalizable

\begin{align*}
		Fv &= \lambda v \\
		F^3 v &= \lambda^3 v \implies \lambda^3 = \lambda\\
		\lambda(\lambda^2 -1) &= 0
\end{align*}

we conclude that a cubically idempotent matrix has eigenvalues that are $+1$, $-1$, or $0$.

Let us look at the particular case of our matrix $L$. Using \eqref{antisimetria} and computing its determinant we get
$$det (gL^T) = det(-gL)$$
 $$\implies det(L) = - det(L) \implies det(L) =0$$
  therefore $L$ has at least one zero eigenvalue $\lambda_1=0$.
  Looking at the even more particular case of $\epsilon \cdot  K$, it is straightforward to verify the eigenvector

  \[
		  \begin{pmatrix} 0 & \epsilon_1 & \epsilon_2 & \epsilon_3 \\ \epsilon_1 & & & \\ \epsilon_2 & & & \\ \epsilon_3 & & & \end{pmatrix} \begin{pmatrix} 1 \\ \epsilon_1 \\ \epsilon_2 \\ \epsilon_3 \end{pmatrix} = \begin{pmatrix} \epsilon_1^2 + \epsilon_2^2 + \epsilon_3^2 \\ \epsilon_1 \\ \epsilon_2 \\ \epsilon_3 \end{pmatrix}  = 
\begin{pmatrix} 1 \\ \epsilon_1 \\ \epsilon_2 \\ \epsilon_3 \end{pmatrix} 
  \] 

  with eigenvalue $\lambda_2 =1$; by \eqref{eigen}, $\lambda_3=-1$. We have thus shown that $\epsilon \cdot K$ is cubically idempotent when $\epsilon$ is a unit vector.
This will be essential when performing the exponential expansion.
Let $\beta = \frac{v}{c}$ and $\hat{\beta}= \begin{pmatrix} \frac{\beta_1}{\beta}, \frac{\beta_2}{\beta}, \frac{\beta_3}{\beta} \end{pmatrix} $ be the (unit) direction of the relative velocity between two frames.
Our general boost takes the form
$$A = \exp(-\hat{\beta}\cdot K \tanh^{-1}\left( \beta \right) )$$
where $\tanh ^{-1} \beta$ is the hyperbolic rotation angle.
Expanding in series

\begin{align*}
		 \exp(-\tanh^{-1}\left( \beta \right) \hat{\beta} \cdot K ) &= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \tanh ^{-1} (\beta)\right)^n }{n!} \\\
&= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
 \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} \\\
&= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \right)^{2n+1} \left( \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
\sum_{n=1}^{\infty} \frac{\left( - \hat{\beta} \cdot K\right)^{2n} \left(\tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} + \\\
& + (-\hat{\beta}\cdot K \tanh ^{-1} \beta)^0 + (\hat{\beta} \cdot K)^2 - (\hat{\beta} \cdot K)^2 \\\
&= \sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K \right) \left( \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
\sum_{n=0}^{\infty} \frac{\left( - \hat{\beta} \cdot K\right)^{2} \left(\tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} + I - (\hat{\beta} \cdot K)^2\\\
&= \left( - \hat{\beta} \cdot K \right)\sum_{n=0}^{\infty} \frac{ \left( \tanh ^{-1} (\beta)\right)^{2n+1}	 }{(2n +1)!} +
 \left(  \hat{\beta} \cdot K\right)^{2}\sum_{n=0}^{\infty} \frac{ \left(\tanh ^{-1} (\beta)\right)^{2n}	 }{(2n )!} + I - (\hat{\beta} \cdot K)^2\\\
&= \left( - \hat{\beta} \cdot K \right)\sinh(\tanh ^{-1}\beta) +
 \left(  \hat{\beta} \cdot K\right)^{2} \cosh(\tanh ^{-1} \beta) + I - (\hat{\beta} \cdot K)^2\\\
.\end{align*}

Let us evaluate the terms we have here. We first resort to the logarithmic and exponential definitions of the hyperbolic trigonometric functions.
The hyperbolic sine and cosine of $\tanh ^{-1} (\beta) = \frac{1}{2} \ln\left( \frac{1+ \beta}{1-\beta} \right) $ are 

\begin{align*}
		\sinh \left( \tanh ^{-1} \beta \right) &= \frac{1}{2} \left\lbrace \exp \left( \ln \sqrt{\frac{1+ \beta}{1-\beta}} \right) - \exp \left( \ln \sqrt{\frac{1- \beta}{1+\beta}} \right)  \right\rbrace  \\\
				&= \frac{1}{2} \left( \frac{\sqrt{(1+ \beta)^2} - \sqrt{(1-\beta)^2}  }{\sqrt{1-\beta^2}  } \right) = \frac{1}{2} \left(\frac{1+\beta -1 +\beta}{\sqrt{1-\beta ^2} }  \right)  \\\
				&= \gamma \beta\\\
		\cosh \left( \tanh ^{-1} \beta \right) &= \frac{1}{2} \left\lbrace \exp \left( \ln \sqrt{\frac{1+ \beta}{1-\beta}} \right) + \exp \left( \ln \sqrt{\frac{1- \beta}{1+\beta}} \right)  \right\rbrace  \\\
				&= \frac{1}{2} \left( \frac{\sqrt{(1+ \beta)^2} - \sqrt{(1-\beta)^2}  }{\sqrt{1-\beta^2}  } \right) = \frac{1}{2} \left(\frac{1+\beta +1 -\beta}{\sqrt{1-\beta ^2} }  \right)  \\\
				&= \gamma 
.\end{align*}

Therefore the transformation becomes

$$A = - \hat{\beta} \cdot K \gamma \beta + \left( \hat{\beta} \cdot K \right)^2 (\gamma - 1) + I $$

It remains to evaluate the matrix $\hat{\beta}\cdot K$ and its square

\begin{align*}
		\hat{\beta} \cdot K &= \frac{1}{\beta} \left( \beta_1 K_1 + \beta_2 K_2 + \beta_3 K_3 \right) \\\
							&= \frac{1}{\beta} \begin{pmatrix} 0 & \beta_1 & \beta_2 & \beta_3 \\\ \beta_1 & & & \\\ \beta_2 & & & \\\ \beta_3 & & &  \end{pmatrix}  \\\
		\implies (\hat{\beta} \cdot K)^2 &= \frac{1}{\beta^2} \begin{pmatrix} \beta_1^2 + \beta_2^2 + \beta_3^2 & 0 & 0& 0 \\\ 0 & \beta_1^2 & \beta_1 \beta_2 & \beta_1\beta_3 \\\ 0 & \beta_1\beta_2 & \beta_2^2 & \beta_2 \beta_3 \\\ 0 & \beta_1\beta_3 & \beta_2 \beta_3  & \beta_3^2\end{pmatrix}  
.\end{align*}

Substituting into the expression for $A$ we get

\begin{align}
A &= - \frac{\gamma \beta}{\beta}  \begin{pmatrix} 0 & \beta_1 & \beta_2 & \beta_3 \\\ \beta_1 & & & \\\ \beta_2 & & & \\\ \beta_3 & & &  \end{pmatrix}  + 
\/gfrac{\gamma - 1}{\beta^2}    \begin{pmatrix} \beta_1^2 + \beta_2^2 + \beta_3^2 & 0 & 0& 0 \\\ 0 & \beta_1^2 & \beta_1 \beta_2 & \beta_1\beta_3 \\\ 0 & \beta_1\beta_2 & \beta_2^2 & \beta_2 \beta_3 \\\ 0 & \beta_1\beta_3 & \beta_2 \beta_3  & \beta_3^2\end{pmatrix}   +I\\\
&=  
  \begin{pmatrix}\gamma-1 & -\beta_1 \gamma & -\beta_2 \gamma& -\beta_3 \gamma \\\ -\beta_1 \gamma & \beta_1^2\frac{\gamma -1}{\beta} & \beta_1 \beta_2 \frac{\gamma -1}{\beta}& \beta_1\beta_3 \frac{\gamma -1}{\beta}\\ -\beta_2\gamma & \beta_1\beta_2 \frac{\gamma -1}{\beta}& \beta_2^2 \frac{\gamma -1}{\beta}& \beta_2 \beta_3 \frac{\gamma -1}{\beta}\\\ -\beta_3 \gamma & \beta_1\beta_3 \frac{\gamma -1}{\beta}& \beta_2 \beta_3 \frac{\gamma -1}{\beta} & \beta_3^2\frac{\gamma -1}{\beta} \end{pmatrix}   +I\\\
&=	   \begin{pmatrix} \gamma -1 + 1 & -\gamma \beta_1 & -\gamma_2 \beta_2& -\gamma \beta_3 \\\ \gamma \beta_1 & 1+ (\gamma -1)\frac{\beta_1^2}{\beta} &(\gamma -1) \beta_1 \beta_2 & (\gamma -1)  \frac{\beta_1\beta_3 }{\beta} \\\ -\gamma \beta_2 & \frac{\gamma -1}{\beta} & 1+(\gamma - 1) \frac{\beta_2^2}{\beta}  & \frac{\gamma -1 }{}\beta\\\ -\gamma \beta_3 & (\gamma -1) \frac{\beta_1\beta_3}{\beta} & (\gamma -1) \frac{\beta_2 \beta_3}{\beta}  & 1 + (\gamma -1) \frac{\beta_3^2}{\beta}\end{pmatrix}   
.\end{align}

Therefore 

\[
	A=	   \begin{pmatrix} \gamma  & -\gamma \beta_1 & -\gamma_2 \beta_2& -\gamma \beta_3 \\ \gamma \beta_1 & 1+ (\gamma -1)\frac{\beta_1^2}{\beta} &(\gamma -1) \beta_1 \beta_2 & (\gamma -1)  \frac{\beta_1\beta_3 }{\beta} \\ -\gamma \beta_2 & \frac{\gamma -1}{\beta} & 1+(\gamma - 1) \frac{\beta_2^2}{\beta}  & \frac{\gamma -1 }{}\beta\\ -\gamma \beta_3 & (\gamma -1) \frac{\beta_1\beta_3}{\beta} & (\gamma -1) \frac{\beta_2 \beta_3}{\beta}  & 1 + (\gamma -1) \frac{\beta_3^2}{\beta}\end{pmatrix}   
.\] 


