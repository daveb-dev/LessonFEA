## Finite Difference Method for linear partial differential equation

$\newcommand{\R}{\mathbb{R}}}$
$\newcommand{\L}{\mathcal{L}}}$
$\newcommand{\dert}[1]{\frac{\partial #1}{\partial t}}$
$\newcommand{\derx}[1]{\frac{\partial #1}{\partial x}}$
$\newcommand{\derf}[2]{\frac{\partial #1}{\partial #2}}$
$\newcommand{\derxx}[1]{\frac{\partial^2 #1}{\partial x^2}}$
$\newcommand{\derk}[2]{\frac{\partial^2 #1}{\partial {#2}^2}}$
$\newcommand{\derm}[3]{\frac{\partial^2 #1}{\partial {#2} \partial {#3}}}$

```

# Classification of Partial differential equation
Let assume $x,y,\ldots$ are indipendent variables. There is a dependent variable that is an unknown function
of the variable $u(x,y,\ldots)$. A PDE is an identity that relates the indipendent variable,
the  dependent variable $u$ and the partial derivatives of $u$. It can be expressed by

$$F(x,y,t, u(x,y,t), \dert{u},\derx{u},\derxx{u},\derk{u}{y},\derm{u}{x}{y}=0$$

The order of an equation is the highest derivative that appears.
Linearity. Let written the equation in form of operator $\L u=0$. Let $v$ is any function, then $\mathcal{L} v$ is function. The definition of linearity is 
$$\mathcal{L}(u+v)= \L u+ \mathcal{L} v $$
$$\L(\alpha\cdot v)=\alpha \L v $$
for any function $u,v$ and constant $\alpha$.
If the rhs is null then the equation is called homogeneous.
Whereas if $\L u=g$ with $g$ not null then equation is call inhomogeneous.

Note: The space of solutions which solve the homogenous linear PDE is a vectorial space. 

Let consider the solution of non homogenous linear PDE namely $\L (u) = f$.
Let suppose that its non-trivial  solution is  $\L(u_0)=f$, then also the $S=\left\{u : \L u=0 \right\} +u_0$ is also solution of the non homoegenous PDE.
Proof. If $v=u+u_0$ with $\L u =0$, then 
$$ \L(v)= \L(u+u_0) =\L(u)+\L(u_0)=0+f$$
Viceversa, if $w \in S$ and $\L(w-u_0)= \L(w)-\L(u_0)= f-f=0$
thus $u= w+u_0 $ is homogenous solution and union of homogenous solution and non homogenous solution constitute all solution of the PDE.

Note: If $\L(u)=0$ and $\L$ is linear. The linear combination of $n$ indipendent solution is still a solution $\L( \sum_{i=0}^{n} c_i u_i)=0$. 


#### Characteristic line
Let consider $a u_x + b u_y =0$ with boundary condition $u(x,y)=g(y)$ that is equivalent to $(a,b) \cdot \nabla u=0$. if $v=(a,b)$ then
$a u_x + b u_y$ is directional derivative of u respect to the direction $v$.
If we assume it is null, this implies that $u(x,y)$ is constant on direction $v$.
And all the parallel line to the gradient has the direction $(b,-a)$ so that $bx -ay=c$ (characteristic line).
This argument lead to state that the solution $u(x,y)= g(bx-ay)$ (depend of $(bx-ay)$). 


#### Non constant coeffiencient
$$ a(x,y) u_x + b(x,y) u_y =0 $$
we can rewritten as an ODE
$$\frac{dy}{dx} = \frac{b(x,y)}{a(x,y)}$$
Abuse of notation: we use $dx$ to denote $\partial x$.
Argument: is conside the particular case $u_x + y u_y=0$ is equivalent to say that directional derivative respect to $(1,y)$ is 0. Then the caratteristic curve with $(x,y)$ as tangent vector  depends on $y $ and $x$ have the equation $\frac{dy}{dx}= \frac{y}{x}$ that is an ode $\dot{y}y(x)=x$ that can rewritten as $\frac{d}{dx}(0.5\cdot y^2)=x$ so $0.5\cdot y^2 - x^2\cdot 0.5= c$, up to rescaling the constant c, the characteristic curve is $ y^2 - x^2 = c$. Thus, the solution is of form 
$u(x,y)=g(y^2-x^2)$. If we imposed that BC $u(0,y)= e^{-y^2}$ then $u(x,y)=e^{-(y^2+x^2)}$.

#### Example of  equations:

+ Transport equation (linear and 1st order) $$\derf{u}{t}+ \beta \cdot \nabla u = f$$
+ Diffusion or heat equation, (second order and linear equation)
    $$\derf{u}{t} - \beta \nabla^2 u = f$$
    where $\nabla^2=\Delta$ is the Laplace operator (sum of 2nd derivative and 
                                                     not mixed).
+ Wave equation (2nd order)
    $$ \derk{u}{t} - c^2 \Delta u = 0 $$
+ Laplace or potentential equation (second order)
    $$\Delta u =0 $$
+ Black Scholes equation (second order)
   $$\derf{u}{t} + 0.5 * \sigma^2 x^2  \derk{u}{x} +r x \derx{u} - ru =0 $$
   evolution of the price $u$ of derivative (e.g. European option) based on
   underlying asset (stock) whose price is $x$
+ Vibrating plate (4th order)
$$   \derk{u}{t} -\Delta^2 u =0 $$
where $$\Delta^2 = \frac{\partial^4 u}{\partial x_1^4} + 2 
\frac{\partial^4 u}{\partial x_1^2 \partial x_2^2 }+ 
= \frac{\partial^4 u}{\partial x_2^4}$$
It is used also as biharmomic operator in Fluid structure interaction.
+ Burger's equation quasilinear first order
   $$ \derf{u}{t} + c u \derf{u}{x} =0 $$
   it models the 1d flux of non viscous fluid. Its variation model the 
   traffic dynamics
   $$ \derf{u}{t} + c u \derf{u}{x} =  \alpha \derk{u}{x} $$
   $\alpha>0$.
   Dissipation part is the address by rhs term where as the common term
   with Burger's equation govern the shock formation.
+ Porous media equation (quasilinear and 2nd order)
   $$\rho \derf{u}{t} = k \nabla \cdot (u^{\gamma} \nabla u) $$
   where $k$ is permeability, $\rho$ density and $\gamma>1$.
   This equation has been use for filtration phenomena, percolation (
   PFAS model).
+ Minimal surface equation (quasilinear, second order) soap bubble model
   $$\nabla \cdot (\frac{\nabla}{\sqrt{1+|\nabla u|^2}}=0$$
   Graph of the solution $u$ minimize the area amon all surface $z=v(x,y)$
   whose boundary is a given curve.
+ Eikonal equation (fully non linear, first order). It appears in 
cardiovascular simulation for the electric potential and in optics. 
  $$|\nabla u | = c(x) $$
+ Navier equation of linear elasticity  (System of PDE, three 2nd order scalar
equation )
  $$ \derk{u}{t}= \mu \Delta u + (\mu+\lambda) \nabla \nabla \cdot u $$
+ Navier Stokes ( 3 quasilinear scalar equation and 1 linear first order)
  $$ \derf{u}{t} +(u \cdot \nabla)u = -\frac{1}{\rho} \nabla p + \nu 
  \Delta u $$
  $$ \nabla \cdot u =0 $$
  The term $(u \cdot \nabla)u$ represent the inertial accelaration due
  to fluid trasport.

## Boundary condition definition

In physical problem, it is necessary to specify some boundary condition to determine the solution. The most used boundary condition are
+  Dirichlet condition  u is specified at boundary
+  Neumann condition the normal derivative $\derf{u}{n}$ is specified 
+  Robin condition $\derf{u}{n} + \beta u$

## Partial differential equation classification

PDE can be classified in three families eliptic, parabolic and hyperbolic.
Let limiting to 2nd order linear with constant coefficient
$$L u = A \derf{u}{x} + B \frac{\partial^2 u}{\partial x \partial y }
  + C  \derf{u}{y} + (D,E) \cdot \nabla u + F u = G $$
The discrimant is $\Delta = B\cdot B - 4 AC $, then

+ $\Delta<0$ equation is defined elliptic
+ $\Delta=0$ equation is defined parabolic
+ $\Delta>0$ equation is defined hyperbolic

Among example above, we could prove that (exercise)
+ wave equation is hyperbolic
+ potential equation is elliptic
+ heat equation is parabolic

## Diffusion Equation
Let consider a motionless liquid filling a straight pipe, and a chemical contaminant which is diffusing through the liquid. In this setting, we focus on motion of contaminant (diffusion), whereas if we model the motion of liquid (convection-trasport). 
The contaminant moves from region of higher concetration to region of lower concetration.
Fick's law of diffusion states rate of motion is proportional to the concetration gradient.
Let $u(x,t)$ the concentration (mass per unit length) of the cominantant at position $x$ of the pipe at time $t$.
In the section of pipe from $a$ to $b$ the mass of contaminat is defined by 
$$ mass(t) = \int_{a}^{b} u(x,t) dt $$
$$\derf{mass(t)}{t} =\int_{a}^{b} \derf{u(x,t)}{t} dt  $$
The mass in this section of domain can not change except by exiting or entering in the pipe (inflow and outflow). Applying the Fick Law
$$\derf{mass(t)}{t} = \mathrm{flow in} - \mathrm{flow out} = k\derf{u}{x}(a,t) -k\derf{u}{x}(b,t) $$
where $k$ is constant. Combining the expression above we obtain
$$ \int_{a}^{b} \derf{u(x,t)}{t} dt = k\derf{u}{x}(a,t) -k\derf{u}{x}(b,t) $$
Now if we differentiate respect to $x$ we get 
$$\dert{u}= a\cdot \derxx{u}$$

#### Transport equation (physical interpretation and analytical solution)
$$ u_t + c u_x =0$$
Let consider a fluid at speed $c$ in horizontal ppipe with constant section ( orizontal to outflow direction). A contaminant is immersed in the fluid $u(x,t)$ $(g/cm^3)$ at time $t$.
$u_t$ is the rate of change of concentration and it is proporzional to gradient of contaminant. We consider negligible the diffusion. Using the characteristic line to derive the analytical solution, we obtain that the solution is of shape $f(cx-t)= u(x,t)$,


#### How we could solve analytically the 1d diffusion equation?
Steady state solution is 
$$u_0 + (u_1-u_0)\frac{x}{L}$$
Hint: if we integrate both side of pde $\Delta u =0$ (1st time we get a constant in right, 2nd time we get  something of shape $u_0(x)= C_1+ C_2 x$ (imposing the bc we get the form above).

Method of separation of variable, since the equation is linear
we can use superposition principle and find a particular solution
$$ u(x,t) = w(x) v(t) $$
1. 1st step consist in replace it in the PDE so we get
$$ \derk{w}{x} - \lambda w(x) =0 $$
we can assume that w(0)=w(1)=0 and 
$$ \derk{v}{t} - \lambda v(t) =0 $$
2. 2nd step solving the first equation with dirichlet Boundary condition
lead to following cases
+ $\lambda =0 $ then $w(x) = A + B x$, following the condition we get $A=B=0$
+ $\lambda >0 $, let $\lambda= \mu^2>0$ then $w(x)= A e^{-\mu x}+ B e^{\mu x}$,  following the condition we get $A=B=0$
+ $\lambda <0 $, let $\lambda=- \mu^2<0$ then $w(x)= A \sin(\mu x)+ B \cos(\mu x)$, 
if $w(0)=B=0$, $w(1)= A \sin \mu B \cos\mu=0$ so $A$ is arbitrary and $\mu_m= m \pi$.
the non trivial solution is $w_m(x)= A sin(m \pi x)$
With $\lambda = -\mu^2_m$ in the other equation involving time, we get the general solution as $v_m(t)= C e^{-m^2 \pi^2 t}$
It follows that the solution of equation with Dirichlet homogenous BC can be written as
$$ U(x,t) = \sum_{m=1}^\infty A_m e^{-m^2 \pi^2 t} \sin(m \pi x) $$
If we impose the initial solution we find the coefficient $A_m$ and it is given 
by sine Fourier series. 
The full solution is overlap of steady state and particular solution (it follows from note above on linear PDE).


## Finite Difference 1D

Definition
0. Derivate definition 1d.
1. Taylor Expansion.
2. Finite Difference 1D.


$$f(x+\delta x)=f(x)+f'(x)\delta x+\frac{f''(x)}{2!}\delta x^2+\dots + \frac{f^{(k)}(x)}{k!}\delta x^k + C_{k+1}$$
Remainder 
$$C_{k+1} = \frac{f^{(k+1)}(\xi)}{(k+1)!}\delta x^{k+1}, \quad\quad x\leq \xi \leq x+\delta x$$
if the $k+1$-th derivative of $f$ is bound by $\alpha$ we have $\vert C_{k+1}\vert \leq \frac{\alpha}{(k+1)!}\delta x^{k+1}$ and if we take the limit for increment that tends to 0, the remainder term will tend to 0 as well.

Let take 1st order derivative:

$$f(x+\delta x)= f(x)+f'(x)\delta x+O(\delta x^2)$$

Let center it with negative increment
$$f(x-\delta x)= f(x)-f'(x)\delta x+O(\delta x^2)$$

We would approximate the 1st derivative. We introduce a grid and from two expansion above we derive the forward and backword finite-difference

Let now approximate the 2th order for 1st derivative

\begin{split}& f(x+\delta x) \approx f(x)+f'(x)\delta x+\frac12 f''(x)\delta x^2 \\
& f(x-\delta x) \approx f(x)-f'(x)\delta x+\frac12 f''(x)\delta x^2.\end{split}
By subtraing them we get

$$f'(x) = \frac{f(x+\delta x) - f(x-\delta x)}{2\delta x}+O(\delta x^2)$$


Let derive approximation for higher order derivative (2nd order)
\begin{split}& f(x+\delta x) = f(x)+f'(x)\delta x+\frac12 f''(x)\delta x^2+\frac16 f'''(x)\delta x^3+O(\delta x^4) \\
& f(x-\delta x) = f(x)-f'(x)\delta x+\frac12 f''(x)\delta x^2-\frac16 f'''(x)\delta x^3+O(\delta x^4).\end{split}

$$f''(x_i)=\frac{f(x_{i-1})-2f(x_i)+f (x_{i+1})}{\delta x^2}.$$

Exercise Hand on: Using the finite difference formulas
1) solve Heat equation
2) solve transport equation
3) Courant Number and stability 


1. Foundamental Solution (n>2)  (next lesson)
2. 2D case Frencht Derivative (next lesson)
3. Finite Difference Method in time and in space (next lesson)



```python

```
