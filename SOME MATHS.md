OK, so let’s suppose that we express the coordinates of a body as a quaternion rotation of the $z$-axis.

Then we can write:

(and this is a simple piece of text to see if git will detect the change!)

$$\mathbf{r}(t) = \mathcal{Q}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t)$$

(This obviously give us an extra degree of freedom but, for the moment, let’s roll with it. - we will resolve this with the bilinear condition as set out below)

Now, we can calculate the velocity by taking the time derivative:

$$\mathbf{v}(t) = \dot{\mathbf{r}}(t) = \dot{\mathcal{Q}}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t) + \mathcal{Q}(t)\,\mathbf{k}\,\dot{\mathcal{Q}}^\dagger (t)$$

Now, we have:

$$\begin{align*}
\mathbf{r}(t)\,\mathbf{r}^\dagger(t)&=   \mathcal{Q}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t)\,\left(  \mathcal{Q}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t) \right)^\dagger \\
&=  \mathcal{Q}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t)\,\mathcal{Q}(t)\,\mathbf{k}^\dagger\,\mathcal{Q}^\dagger(t) \\
&= r(t)\,  \mathcal{Q}(t)\,\mathbf{k}\,\mathbf{k}^\dagger\,\mathcal{Q}^\dagger(t) \\
&= r(t)\,  \mathcal{Q}(t)\,\mathcal{Q}^\dagger(t) \\
&= r(t)^2
\end{align*}$$

Where we have introduced the requirement that $\mathcal{Q}(t)\,\mathcal{Q}^\dagger (t) = r(t) = \mathcal{Q}^\dagger (t)\,\mathcal{Q}(t)$

Let’s also introduce the requirement that:

$$ \dot{\mathcal{Q}}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t) = \mathcal{Q}(t)\,\mathbf{k}\,\dot{\mathcal{Q}}^\dagger (t)$$

This is the bilinear condition and, on a quaternion component basis amounts to:

$$ q_0(t)\,\dot{q}_3(t) - q_1(t)\,\dot{q}_2(t) + q_2(t)\,\dot{q}_1(t) - q_3(t)\,\dot{q}_0(t) = 0 $$

This means that we can write the velocity as:

$$\mathbf{v}(t) = 2\,\dot{\mathcal{Q}}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t) $$

Which means that we express a simple Lagrangian as:

$$\begin{align*}
\mathcal{L} &= \frac{1}{2}\,\dot{\mathbf{r}}(t)\,\dot{\mathbf{r}}^\dagger(t) \\
&=\frac{1}{2}\,\left(2\,\dot{\mathcal{Q}}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t)\right)\,\left(2\,\dot{\mathcal{Q}}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t)\right)^\dagger \\
&= 2\, \dot{\mathcal{Q}}(t)\,\mathbf{k}\,\mathcal{Q}^\dagger(t)\, \mathcal{Q}(t)\, \mathbf{k}^\dagger\, \dot{\mathcal{Q}}^\dagger(t) \\
&= 2\, r(t) \, \dot{\mathcal{Q}}(t)\,\mathbf{k}\, \mathbf{k}^\dagger\, \dot{\mathcal{Q}}^\dagger(t) \\
&= 2\, r(t) \, \dot{\mathcal{Q}}(t)\, \dot{\mathcal{Q}}^\dagger(t) \\
\end{align*}$$

Because we don’t have a potential term, here, we end up with the straightforward form for the Hamiltonian:

$$\mathcal{H} = \frac{1}{8\,r(t)} \, \mathcal{P}(t)\, \mathcal{P}^\dagger(t)$$

Where we have introduced the generalized momentum, $\mathcal{P}(t)$ such that:

$$\mathcal{P}(t) = 4\,r(t)\,\dot{\mathcal{Q}}(t)$$

From this, we can construct a new Hamiltonian, $\mathcal{G}$ in a new time variable $\tau$:

$$\begin{align*}
\mathcal{G} &= \left(\mathcal{H} - \epsilon\right)\,4\,r(\tau) \\
&= \left( \frac{1}{8\,r(\tau)} \, \mathcal{P}(\tau)\, \mathcal{P}^\dagger(\tau)- \epsilon\right)\,4\,r(\tau) \\
&= \frac{1}{2} \, \mathcal{P}(\tau)\, \mathcal{P}^\dagger(\tau)- 4\,\epsilon\,r(\tau)\\
&= \frac{1}{2} \, \mathcal{P}(\tau)\, \mathcal{P}^\dagger(\tau)- 4\,\epsilon\,\mathcal{Q}(\tau)\,\mathcal{Q}^\dagger(\tau)
\end{align*}$$

The equation of motion for this are:

$$\begin{align*}
\dot{\mathcal{Q}}(\tau) &= \mathcal{P}(\tau) \\
\dot{\mathcal{P}}(\tau) &= 8\,\epsilon\,\mathcal{Q}(\tau) 
\end{align*}$$

Or, more straightforwardly:

$$\ddot{\mathcal{Q}}(\tau) - 8\,\epsilon\,\mathcal{Q}(\tau) == 0$$

Which admits a general solution:

$$\mathcal{Q}(\tau) = \mathcal{A}\,\cosh(\sqrt{8\,\epsilon}\,\tau) + \mathcal{B}\,\mathcal\,\sinh(\sqrt{8\,\epsilon}\,\tau) $$

Now, given the requirements that:

$$\begin{align*}
\mathcal{Q}(0)\,\mathcal{Q}^\dagger(0) &= r \\
0 + x\,\mathbf{i} + y\,\mathbf{j} + z\,\mathbf{k} &= \mathcal{Q}(0)\,\mathbf{k}\,\mathcal{Q}^\dagger(0)
\end{align*}$$

We can show that the general form for the components of $\mathcal{A}$ are:

$$\begin{align*}
a_0 &= -\frac{\sqrt{r+z}}{\sqrt{2}}\, \sin(\phi) \\
a_1 &= + \frac{x\cos(\phi)+y\sin(\phi)}{\sqrt{2}\sqrt{r+z}} \\
a_2 &= + \frac{y\cos(\phi)-x\sin(\phi)}{\sqrt{2}\sqrt{r+z}} \\
a_3 &= +\frac{\sqrt{r+z}}{\sqrt{2}}\, \cos(\phi)
\end{align*}$$

Where $\phi$ is an arbitrary angle.  What, if anything, determines, the phase angle.  Let’s consider the rotation operations on the three unit quaternions - $\mathbf{i}$, $\mathbf{j}$ and $\mathbf{k}$.  By construction, the last of these - $\mathbf{k}$ - maps the radial vector to the $k$-axis.  But what about the other two?   So, let’s think of $\mathbf{i}$, $\mathbf{j}$ and $\mathbf{k}$ forming a standard right-handed coordinate system.  If we say, that $\mathbf{k}$ is the radial unit vector, then $\mathbf{i}$ is the transpose unit vector and $\mathbf{j}$ is the out-of-plane unit vector.  So, to choose the gauge, we set:

$$\begin{align*}
\mathcal{Q}\,\mathbf{k}\,\mathcal{Q}^\dagger &= \mathbf{x} \\
\\
\mathcal{Q}\,\mathbf{i}\, \mathcal{Q} ^\dagger&= \frac{r}{v_t}\,\mathbf{v} - \frac{v_r}{v_t}\,\mathbf{x}\\
\\
\mathcal{Q}\,\mathbf{j}\,\mathcal{Q}^\dagger &= \frac{1}{v_t}\,\mathbf{h}
\end{align*}$$

Where:

$$\begin{align*}
\mathbf{x} &= x\,\mathbf{i} + y\,\mathbf{j} + z\,\mathbf{k} \\
\mathbf{v} &= v_x\,\mathbf{i} + v_y\,\mathbf{j} + v_z\,\mathbf{k} \\
\mathbf{h} &= h_x\,\mathbf{i} + h_y\,\mathbf{j} + h_z\,\mathbf{k}
\end{align*}$$


# Some more maths

Let's consider our rotating coordinate system in which the position of the vessel is always mapped to a point on the $r$-axis; and the $velocity vector is mapped to a vector that always lies in the $r$-$t$ plane.

$$\begin{aligned}
\mathbf{r} &= \mathcal{Q}\,(r\,\mathbf{i})\,\mathcal{Q}^\dagger \\
\dot{\mathbf{r}} &=\mathcal{Q}\,(\dot{r}\,\mathbf{i} + r\,\dot{\theta}\,\mathbf{j})\,\mathcal{Q}^\dagger \\
\mathcal{Q}\,\mathcal{Q}^\dagger &= 1= \mathcal{Q}^\dagger\,\mathcal{Q}
\end{aligned}$$

This is definitional in that it describes the rules that the rotation quaternion must obey for it to undertake the required mapping.  We note that we can also take the time deriative of the first of these equations as follows:

$$\dot{\mathbf{r}} = \dot{\mathcal{Q}}\,(r\,\mathbf{i})\,\mathcal{Q}^\dagger +  \mathcal{Q}\,(\dot{r}\,\mathbf{i})\,\mathcal{Q}^\dagger +  \mathcal{Q}\,(r\,\mathbf{i})\,\dot{\mathcal{Q}}^\dagger$$

But this must equal the second of the equations.  So, we get:

$$\begin{aligned}
\mathcal{Q}\,(\dot{r}\,\mathbf{i} + r\,\dot{\theta}\,\mathbf{j})\,\mathcal{Q}^\dagger &= \dot{\mathcal{Q}}\,(r\,\mathbf{i})\,\mathcal{Q}^\dagger +  \mathcal{Q}\,(\dot{r}\,\mathbf{i})\,\mathcal{Q}^\dagger +  \mathcal{Q}\,(r\,\mathbf{i})\,\dot{\mathcal{Q}}^\dagger \\
\dot{\theta}\,\mathcal{Q}\,\mathbf{j}\,\mathcal{Q}^\dagger &= \dot{\mathcal{Q}}\,\mathbf{i}\,\mathcal{Q}^\dagger +  \mathcal{Q}\,\mathbf{i}\,\dot{\mathcal{Q}}^\dagger 
\end{aligned} $$

But the turn on the left-hand side is just the rate of change of the radial unit vector $\mathbf{r}$ and the left-hand side is simply $\dot{\theta}$ times the transverse radial vector, $\mathbf{t}$ - *i.e.*,

$$\dot{\mathbf{r}} = \dot{\theta}\,\mathbf{t} $$

which, of course, is obviously correct.  (N.B., it also seems self-evident that  (in the absence of perturbative forces) $\dot{\mathbf{t}}=-\dot{\theta}\,\mathbf{r}$; and $\dot{\mathbf{p}}=0$.

If we construct the system Lagrangian as:

$$L = \frac{1}{2}\,\dot{\mathbf{r}}\,\dot{\mathbf{r}}^\dagger + \frac{\mu}{r}$$

Then we can show that the system Lagraniangian ultimately reduces to:

$$ L = \frac{1}{2}\,\left(\dot{r}^2 + r^2\,\dot{\theta}^2\right) + \frac{\mu}{r} $$

There is nothing surprising in this except that for the fact that dynamical description of the quaternion is absent.   Instead, this has been transferred to a rule defining the quaternion rotation as:

$$ \dot{\mathcal{Q}}\,\mathbf{i}\,\mathcal{Q}^\dagger +  \mathcal{Q}\,\mathbf{i}\,\dot{\mathcal{Q}}^\dagger = \dot{\theta}\,\mathcal{Q}\,\mathbf{j}\,\mathcal{Q}^\dagger$$

In fact, we can extend these set of rules for how coordinate axes transform with time as:

$$\begin{aligned}
\dot{\mathcal{Q}}\,\mathbf{i}\,\mathcal{Q}^\dagger +  \mathcal{Q}\,\mathbf{i}\,\dot{\mathcal{Q}}^\dagger &= +\dot{\theta}\,\mathcal{Q}\,\mathbf{j}\,\mathcal{Q}^\dagger \\
\dot{\mathcal{Q}}\,\mathbf{j}\,\mathcal{Q}^\dagger +  \mathcal{Q}\,\mathbf{j}\,\dot{\mathcal{Q}}^\dagger &= -\dot{\theta}\,\mathcal{Q}\,\mathbf{i}\,\mathcal{Q}^\dagger \\
\dot{\mathcal{Q}}\,\mathbf{k}\,\mathcal{Q}^\dagger +  \mathcal{Q}\,\mathbf{k}\,\dot{\mathcal{Q}}^\dagger &= 0
\end{aligned}$$

The solution of which is:

$$\dot{\mathcal{Q}} = \frac{1}{2}\,\dot{\theta}\,\mathcal{Q}\,\mathbf{k}$$

The dynamics of the quaternion are 'slaved' to the two-dimensional Keplerian system described by the system, $L$.  We can set up the quaternion rotation as a separate Lagrangian system - in $\theta$-time.  This, or course, will leas to a simple linear system of equations that can readily be solved.  We can introduce perturbations into this mix.  This is quite an exciting prospect!

**Equations of motion**

What, then are the equations of motion; and what do these look like in $\theta$-time?

$$\begin{aligned}
\ddot{r} &= -\frac{\mu}{r^2} + r\,\dot{\theta}^2 \\
\frac{d}{dt}\left(r^2\,\dot{\theta}\right) &= 0
\end{aligned}$$

These equations of motion are, of course, entirely expected, although not entirely helpful.  The system Hamiltonian is given by:

$$H = \frac{1}{2}\,p_r^2 + \frac{1}{2\,r^2}\,p_\theta^2 - \frac{\mu}{r} $$

wherethe generalised momenta are $p_r = \dot{r}$ and $p_\theta = r^2\,\dot{\theta}$.  The equations of motion for this are:

$$\begin{aligned}
\dot{r} &= p_r \\
\dot{p}_r &= \frac{p_\theta^2}{r^3} - \frac{\mu}{r^2} \\
\\
\dot{\theta} &=\frac{p_\theta}{r^2} \\
\dot{p}_\theta &= 0
\end{aligned}$$

By convention, we normally write this as:

$$\begin{aligned}
\dot{r} &= p_r \\
\dot{p}_r &= \frac{h^2}{r^3} - \frac{\mu}{r^2} \\
\\
\dot{\theta} &=\frac{h}{r^2} \\
\dot{h} &= 0 \\
\end{aligned}$$

* * *
 
 It the first section above, we reviewed the general procedure that was used to establish the K-S transformation.   In many ways, the transformation to rotating coordinate is similar - except, we wish to map the position of the spacecraft to a point on the radial axis.
 
 In particular, we have:
 
 $$\mathbf{r} = r\,\mathcal{Q}\,\mathbf{i}\,\mathcal{Q}^\dagger $$
 
 If we differentiate this with respect to time, we get:
 
  $$\dot{\mathbf{r}} = r\,\dot{\mathcal{Q}}\,\mathbf{i}\,\mathcal{Q}^\dagger + \dot{r}\,\mathcal{Q}\,\mathbf{i}\,\mathcal{Q}^\dagger + r\,\mathcal{Q}\,\mathbf{i}\,\dot{\mathcal{Q}}^\dagger $$
  
  Now, in much the same way where we make the ansatz that:
  
  $$ \dot{\mathcal{Q}}\,\mathbf{i}\,\mathcal{Q}^\dagger = \mathcal{Q}\,\mathbf{i}\,\dot{\mathcal{Q}}^\dagger $$
  
  (which in the K-S transformation scheme is described as the bilinear condition), then we have:
  
  $$\dot{\mathbf{r}} =2\, r\,\dot{\mathcal{Q}}\,\mathbf{i}\,\mathcal{Q}^\dagger + \dot{r}\,\mathcal{Q}\,\mathbf{i}\,\mathcal{Q}^\dagger $$
  
  and from this, we conclude that:
  
  $$\frac{1}{2}\,\dot{\mathbf{r}}\,\dot{\mathbf{r}}^\dagger = \frac{1}{2}\,\dot{r}^2 + 2\,r^2\,\dot{\mathcal{Q}}\,\dot{\mathcal{Q}}^\dagger$$ 
  
  subject of course to the condition that $\mathcal{Q}\,\mathcal{Q}^\dagger=1$; and the bilinear condition as set out above. The Lagrangian for this system is:
  
$$L = \frac{1}{2}\,\dot{r}^2 + 2\,r^2\,\dot{\mathcal{Q}}\,\dot{\mathcal{Q}}^\dagger + \frac{\mu}{r} $$

This is, however, a constrained Lagrangian system.  To this, we also need to add the requirement that $\mathcal{Q}\,\mathcal{Q}^\dagger = 1$ and the bilinear constraint.  (N.B., In all probability, the bilinear constraint is probably satisfied if initial conditions satisfy the condition.  So, our Lagrangian system becomes:

$$L = \frac{1}{2}\,\dot{r}^2 + 2\,r^2\,\dot{\mathcal{Q}}\,\dot{\mathcal{Q}}^\dagger + \frac{\mu}{r} + \lambda\,\left(\mathcal{Q}\,\mathcal{Q}^\dagger - 1\right)$$

The equations of motion for this are:

$$\begin{aligned}
\ddot{r} &= 4\,r\,\dot{\mathcal{Q}}\,\dot{\mathcal{Q}}^\dagger - \frac{\mu}{r^2} \\
\frac{d}{dt}\left(r^2\,\dot{\mathcal{Q}}\right) &= \frac{\lambda}{2}\,\mathcal{Q}
\end{aligned}$$

Let’s try a specific solution:

$$\dot{\mathcal{Q}} = \frac{\alpha}{2\,r^2}\,\mathcal{Q}\,\mathbf{k} $$

Substituting into these equations, we have:

$$\begin{aligned}
\ddot{r} &= \frac{\alpha^2}{r^3} - \frac{\mu}{r^2} \\
-\frac{1}{2}\,\frac{\alpha^2}{r^2} &= \lambda
\end{aligned}$$

Because this is the Kepler problem, the first equation allows us to identify $\alpha$ as the specific angular momentum, $h$.  In which case, we can write the Lagrangian as:

$$\begin{aligned}
L &= \frac{1}{2}\,\dot{r}^2 + 2\,r^2\,\dot{\mathcal{Q}}\,\dot{\mathcal{Q}}^\dagger + \frac{\mu}{r} - \frac{1}{2}\,\frac{h^2}{r^2}\,\left(\mathcal{Q}\,\mathcal{Q}^\dagger - 1\right) 
\end{aligned}$$

This doesn’t necessarily help us much - but at least we now have the system Lagrangian.   We can now use this to help set up the variational integrator for this system.  Again, this is not of much use to us in the non-perturbed Keplerian case (since we already have the problem solution), but it does help us in the case of the perturbed Keplerian case since we now have a means of setting up the appropriate variational integration scheme.

In any event, the equations of motion are as follows:

$$\begin{aligned}
\ddot{r} &= 4\,r\,\dot{\mathcal{Q}}\,\dot{\mathcal{Q}}^\dagger - \frac{\mu}{r^2} \\
\frac{d}{dt}\left( 4\,r^2\,\dot{\mathcal{Q}}\right) &=  - \frac{h^2}{r^2}\,\mathcal{Q}
\end{aligned}$$

A specific solution of the second of these equations is:

$$\dot{\mathcal{Q}} = \frac{1}{2}\,\frac{h}{r^2}\,\mathcal{Q}\,\mathbf{k} $$

And substituting into the first of the equations of motion gives:

$$ \ddot{r} = \frac{h^2}{r^3} - \frac{\mu}{r^2} $$

These are, of course, already well know to us as non-perturbed Keplerian motion.