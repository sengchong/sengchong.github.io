---
layout: post
title: Representing points and vectors in computer graphics
---



In mathematics to define a point or a vector we will usually do it in the form of $p$ = ($x$, $y$, $z$).This means: <br/>

 <center> $$x \cdot \hat{i} + y \cdot \hat{j} + z \cdot \hat{k} $$  </center> <br/>

However this is not good enough as we need a way to differentiate between a point and a vector in our program. 
Therefore we need to add in an extra component, the origin. <br/><br/>

For points we can reprsent it with a 1 at the fourth attribute of the equation.
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

For vectors, simply replace 0 with 1.<br/>

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


