---
layout: post
title: Representing points and vectors in computer graphics
---
In mathematics to define a point or a vector we will usually do it in the form of $p$ = ($x$, $y$, $z$).This means: <br/>

 <center> $$x \cdot \hat{i} + y \cdot \hat{j} + z \cdot \hat{k} $$  </center> <br/>

However this is not good enough as we need a way to differentiate between a point and a vector in our program. 
Therefore we need to add in an extra component, the origin. <br/><br/>

A point is describing a location in a space and we can represent it with a 1 at the fourth attribute of the equation.
<center>$x$ $\cdot$ $\hat{i}$ + $y$ $\cdot$ $\hat{j}$ + $z$ $\cdot$ $\hat{k}$ + 1 $\cdot$ $\omicron$ </center>

This can be also represented in 

$$ \left[
    \begin{array}{c}
      x \\
      y \\
	  z \\
	  1
    \end{array}
\right] 
\cdot 
\left[
    \begin{array}{c}
      \hat{i}\\
      \hat{j}\\
	  \hat{k}\\
	  \omicron
    \end{array}
\right]
$$

 <center> or  </center>

$$ \left[
    \begin{array}{c}
      x & y & z & 1
    \end{array}
\right] 
\left[
    \begin{array}{c}
      \hat{i}\\
      \hat{j}\\
	  \hat{k}\\
	  \omicron
    \end{array}
\right]
$$

While a vector is describing a direction, to represent a vector, simply replace the fourth attribute 0 with 1.<br/>

<center>$x$ $\cdot$ $\hat{i}$ + $y$ $\cdot$ $\hat{j}$ + $z$ $\cdot$ $\hat{k}$ + 0 $\cdot$ $\omicron$ </center>

This can be also represented in 

$$ \left[
    \begin{array}{c}
      x \\
      y \\
	  z \\
	  0
    \end{array}
\right] 
\cdot 
\left[
    \begin{array}{c}
      \hat{i}\\
      \hat{j}\\
	  \hat{k}\\
	  \omicron
    \end{array}
\right]
$$

 <center> or  </center>

$$ \left[
    \begin{array}{c}
      x & y & z & 0
    \end{array}
\right] 
\left[
    \begin{array}{c}
      \hat{i}\\
      \hat{j}\\
	  \hat{k}\\
	  \omicron
    \end{array}
\right]
$$

For a 3 X 3 Matrix (2 X 2 Matrix for two dimension), we can use it to perform linear transformation such as rotation, scaling and shear.<br/>
However we are unable to perform translation. This will not matter to a vector as translation has no meaning to a vector but it is meaningful>to a point. <br/>

This is why the introduction of homogeneous notions is useful for vectors and points transformation.  Also the ability to only do translation for points only. <br/>

A 3 X 3 Matrix will becomes a 4 X 4 Matrix. <br/>

$$ \left[
    \begin{array}{c}
      m00 \\
      m10 \\
	  m20 \\
	  0
    \end{array}

    \begin{array}{c}
      m10\\
      m11\\
	  m21\\
	  0
    \end{array}
\right]
\cdot 
\left[
    \begin{array}{c}
      \m20\\
      \m12\\
	  \m13\
	  \0
    \end{array}
\right]
\cdot 
\left[
    \begin{array}{c}
      \0\\
      \0\\
	  \0\\
	  \1
    \end{array}
\right]
$$

Rotating, scaling and shear matrix can replace M, and it will affect the vector and point. <br/>
Translation however uses the addition element of the 4 X 4 Matrix.<br/>
A translation Matrix T will look like this.  <br/>

$$ \left[
    \begin{array}{c}
      \1 \\
      \0 \\
	  \0 \\
	  \0
    \end{array}
\right] 
\cdot 
\left[
    \begin{array}{c}
      \0\\
      \1\\
	  \0\\
	  \0
    \end{array}
\right]
\cdot 
\left[
    \begin{array}{c}
      \0\\
      \0\\
	  \1\
	  \0
    \end{array}
\right]
\cdot 
\left[
    \begin{array}{c}
      \tx\\
      \ty\\
	  \tz\\
	  \1
    \end{array}
\right]
$$

