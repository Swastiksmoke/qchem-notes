# Quantum Chemistry Journey — Day 2

These notes collect the material we studied in Day 2, in a sequence that follows the course packets. They are written as a study reference: start with the plain-language idea, then use the equations to make it precise.

## Course map and what we covered

The IIT Kharagpur course packets place the material roughly in this order:

1. Quantum-mechanics postulates and measurement (Lectures 2–3)
2. Exactly solvable models: particle in a box, harmonic oscillator, angular momentum, hydrogen atom (Lectures 4–6)
3. Variational principle, excited states, applications, and the linear variational method (Lectures 7–11)
4. Variational applications to chemical bonding (Lectures 12–13)

We skimmed commutators, the uncertainty principle, and angular momentum because they were already familiar. We gave molecular-orbital theory an early preview, but in this course it appears later as an application of variational methods.

---

# 1. Quantum states, observables, and measurement

## 1.1 The wavefunction represents the state

A quantum state can be represented by a wavefunction. For a particle in position space, write it as \(\psi(\mathbf r,t)\). It is not a tiny path traced by the particle. Instead, it is a mathematical object that lets us calculate probabilities for measurement outcomes.

The probability density for position is

\[
|\psi(\mathbf r,t)|^2.
\]

The probability of finding the particle in a region \(R\) is

\[
P(R)=\int_R |\psi(\mathbf r,t)|^2\,d\tau,
\]

where \(d\tau\) is a small volume element. In one dimension, this becomes \(P(R)=\int_R|\psi(x,t)|^2 dx\).

A wavefunction for one particle must be normalized:

\[
\int_{\text{all space}}|\psi|^2d\tau=1.
\]

This says the probability of finding the particle somewhere in all space is 1. The wavefunction may be complex; \(|\psi|^2=\psi^*\psi\) is real and nonnegative.

## 1.2 Observables are represented by operators

A measurable physical quantity is called an observable. Examples include position, momentum, and energy. Each observable has an associated operator, commonly marked with a hat:

\[
\hat x=x,\qquad
\hat p_x=-i\hbar\frac{d}{dx},\qquad
\hat H=\text{Hamiltonian (total-energy operator)}.
\]

An operator is a mathematical instruction acting on a function. For example, \(\hat p_x\) differentiates the wavefunction and multiplies by \(-i\hbar\).

## 1.3 Eigenfunctions and possible measurement values

If applying an operator to a function returns that same function multiplied by a number, the function is an eigenfunction:

\[
\hat A\phi_n=a_n\phi_n.
\]

Here \(\hat A\) represents an observable, \(\phi_n\) is one of its eigenfunctions, and \(a_n\) is the corresponding eigenvalue. The eigenvalue is a possible measurement result. If the system is already in the eigenfunction \(\phi_n\), measuring \(A\) gives \(a_n\) with certainty.

For energy, the eigenvalue equation is the time-independent Schrödinger equation:

\[
\hat H\psi_n=E_n\psi_n.
\]

Its solutions give the allowed energy eigenfunctions and energies.

## 1.4 Probabilities and expectation values

For a Hermitian observable operator, its eigenfunctions can be used as an orthonormal basis (under the usual conditions). Expand a normalized state in that basis:

\[
\psi=\sum_n c_n\phi_n.
\]

The probability of measuring eigenvalue \(a_n\) is

\[
P(a_n)=|c_n|^2,
\qquad \sum_n |c_n|^2=1.
\]

This is the Born rule. A single measurement gives one allowed eigenvalue; it does not return an average of several values.

The expectation value is the long-run average over many repetitions on identically prepared systems:

\[
\langle A\rangle=\sum_n |c_n|^2a_n
=\langle\psi|\hat A|\psi\rangle.
\]

In position representation,

\[
\langle A\rangle=\int\psi^*(x)\hat A\psi(x)\,dx.
\]

For position specifically,

\[
\langle x\rangle=\int x|\psi(x)|^2dx.
\]

Example: if outcomes 1 and 3 have probabilities 3/4 and 1/4, respectively, then the expectation value is

\[
\langle A\rangle=\frac34(1)+\frac14(3)=1.5.
\]

A single result is still 1 or 3; 1.5 is the average across many measurements.

In the idealized measurement rule, after an outcome \(a_n\) is obtained, the state becomes the corresponding eigenstate \(\phi_n\). Measuring the same observable immediately again then returns \(a_n\) with certainty.

## 1.5 Hermitian operators

Observable operators are Hermitian. Their important properties include:

- their eigenvalues are real, as measured values must be;
- their eigenfunctions can be chosen to form a complete orthonormal set.

“Orthonormal” means distinct basis functions are orthogonal and each has unit norm. Completeness means the set is rich enough to represent allowed states.

## 1.6 Commutators and uncertainty — skim review

The commutator of two operators is

\[
[\hat A,\hat B]=\hat A\hat B-\hat B\hat A.
\]

If the commutator is zero, the operators commute. Under appropriate conditions, commuting observables can have a common set of eigenstates. Noncommuting observables generally cannot both have exact values in the same state.

For position and momentum,

\[
[\hat x,\hat p_x]=i\hbar,
\]

which leads to

\[
\Delta x\,\Delta p_x\geq\frac{\hbar}{2}.
\]

Here \(\Delta x\) and \(\Delta p_x\) are the spreads in position and momentum measurements. This is a property of quantum states, not just a limitation of measuring devices.

---

# 2. Exactly solvable models

Exactly solvable models are simplified systems whose Schrödinger equations can be solved exactly. They teach us how the potential-energy function and boundary conditions shape wavefunctions and energies.

## 2.1 Particle in a one-dimensional box

A particle of mass \(m\) is confined between \(x=0\) and \(x=L\). The idealized potential is

\[
V(x)=\begin{cases}
0,&0<x<L,\\
\infty,&x\leq0\text{ or }x\geq L.
\end{cases}
\]

Because the walls are infinitely high, the wavefunction is zero at the walls and outside the box:

\[
\psi(0)=\psi(L)=0.
\]

Inside the box, the time-independent Schrödinger equation is

\[
-\frac{\hbar^2}{2m}\frac{d^2\psi}{dx^2}=E\psi.
\]

Define \(k^2=2mE/\hbar^2\). The equation becomes \(\psi''+k^2\psi=0\), whose general solution is

\[
\psi(x)=A\sin(kx)+B\cos(kx).
\]

The boundary condition at \(x=0\) requires \(B=0\). The condition at \(x=L\) requires \(\sin(kL)=0\), so

\[
k_n=\frac{n\pi}{L},\qquad n=1,2,3,\ldots
\]

The value \(n=0\) would give a wavefunction that is zero everywhere, which cannot represent a particle. Normalizing each allowed state gives

\[
\boxed{\psi_n(x)=\sqrt{\frac2L}\sin\left(\frac{n\pi x}{L}\right)}
\quad(0<x<L)}
\]

and the allowed energies are

\[
\boxed{E_n=\frac{n^2\pi^2\hbar^2}{2mL^2}}.
\]

Consequences:

- Energies are discrete because only certain waves fit the boundary conditions.
- The ground-state energy is positive; it is not possible to have \(n=0\).
- Energy grows as \(n^2\): \(E_2=4E_1\), \(E_3=9E_1\).
- Energy scales as \(1/L^2\), so a narrower box has higher energies.
- State \(n\) has \(n-1\) internal nodes.
- The probability density is \(|\psi_n(x)|^2\), not \(\psi_n(x)\) itself.

### Variational example: a parabolic trial shape in the box

This is a useful bridge from exactly solvable models to the variational principle. Try

\[
\psi_{\rm trial}(x)=A x(L-x),\qquad 0<x<L.
\]

It is zero at both walls, so it respects the box boundary conditions. Normalize it:

\[
1=A^2\int_0^Lx^2(L-x)^2dx=A^2\frac{L^5}{30},
\]

so \(A=\sqrt{30/L^5}\).

Inside the box there is no potential energy. Integration by parts, with the wavefunction zero at both ends, gives the kinetic-energy expectation as

\[
E_{\rm trial}=\frac{\hbar^2}{2m}\int_0^L|\psi'_{\rm trial}(x)|^2dx.
\]

Since \(\psi'_{\rm trial}=A(L-2x)\),

\[
\int_0^L|\psi'_{\rm trial}|^2dx
=A^2\int_0^L(L-2x)^2dx
=\frac{30}{L^5}\frac{L^3}{3}
=\frac{10}{L^2}.
\]

Therefore

\[
\boxed{E_{\rm trial}=\frac{5\hbar^2}{mL^2}}.
\]

The exact ground energy is

\[
E_1=\frac{\pi^2\hbar^2}{2mL^2}
\approx\frac{4.9348\hbar^2}{mL^2}.
\]

Our trial value, \(5\hbar^2/(mL^2)\), is slightly higher, as the variational principle predicts. Its error is about 1.3% in this example.

## 2.2 Harmonic oscillator

A harmonic oscillator models a particle pulled toward an equilibrium point. Its potential is a parabola:

\[
V(x)=\frac12m\omega^2x^2,
\]

where \(\omega\) is the angular frequency. For a molecular vibration, \(m\) is replaced by the reduced mass \(\mu\), and \(\omega=\sqrt{k/\mu}\).

The Hamiltonian is

\[
\hat H=-\frac{\hbar^2}{2m}\frac{d^2}{dx^2}+\frac12m\omega^2x^2.
\]

The allowed energies are

\[
\boxed{E_v=\hbar\omega\left(v+\frac12\right)},
\qquad v=0,1,2,\ldots
\]

Neighboring levels are separated by the same amount, \(\hbar\omega\). Even the ground state has nonzero energy \(E_0=\hbar\omega/2\), called zero-point energy.

The ground-state wavefunction is a Gaussian:

\[
\psi_0(x)=\left(\frac{\alpha}{\pi}\right)^{1/4}e^{-\alpha x^2/2},
\qquad \alpha=\frac{m\omega}{\hbar}.
\]

A Gaussian is a bell-shaped curve. The wavefunction describes amplitudes; its square,

\[
|\psi_0(x)|^2=\left(\frac{\alpha}{\pi}\right)^{1/2}e^{-\alpha x^2},
\]

is the bell-shaped position probability density. The particle is most likely near the equilibrium position, but it is not fixed there.

Molecular bonds are approximately harmonic for small displacements from equilibrium. Real molecular potentials depart from a perfect parabola at larger stretches, so the harmonic model is an approximation.

## 2.3 Angular momentum — skim review

Orbital angular momentum is described by \(\hat L^2\) and one component, commonly \(\hat L_z\):

\[
\hat L^2\psi=\ell(\ell+1)\hbar^2\psi,
\qquad
\hat L_z\psi=m_\ell\hbar\psi.
\]

Here \(\ell=0,1,2,\ldots\) and \(m_\ell=-\ell,-\ell+1,\ldots,\ell\). Thus there are \(2\ell+1\) possible values of the z-component for a given \(\ell\). The magnitude is \(\sqrt{\ell(\ell+1)}\hbar\); the z-component is \(m_\ell\hbar\). The different components of angular momentum do not all commute, so they cannot all be simultaneously definite.

## 2.4 Hydrogen atom

Hydrogen has one electron attracted to one proton. Using the electron–proton reduced mass \(\mu\), the Hamiltonian in the relative coordinate is

\[
\hat H=-\frac{\hbar^2}{2\mu}\nabla^2
-\frac{e^2}{4\pi\varepsilon_0r}.
\]

The negative Coulomb potential represents attraction. We set the energy of a separated proton and electron at infinite distance to zero; bound states then have negative energy.

Because the potential depends only on distance \(r\), use spherical coordinates and separate the wavefunction:

\[
\psi_{n\ell m_\ell}(r,\theta,\phi)
=R_{n\ell}(r)Y_{\ell m_\ell}(\theta,\phi).
\]

The radial part describes dependence on distance; the spherical harmonic describes angular dependence.

The quantum numbers are restricted as follows:

\[
n=1,2,3,\ldots;
\qquad \ell=0,1,\ldots,n-1;
\qquad m_\ell=-\ell,\ldots,\ell.
\]

The energy depends on \(n\) in the nonrelativistic hydrogen model:

\[
E_n=-\frac{\mu e^4}{2(4\pi\varepsilon_0)^2\hbar^2n^2}
\approx-\frac{13.6\text{ eV}}{n^2}
\]

for ordinary hydrogen. The ground state is at \(-13.6\) eV; ionizing it to zero energy takes 13.6 eV. For a given \(n\), different \(\ell,m_\ell\) states have the same energy in this simple model; this is degeneracy.

The lowest state is called 1s: \(n=1,\ell=0,m_\ell=0\). It is spherical. It is a probability distribution, not an electron moving on a circular path. For 1s, the pointwise density \(|\psi|^2\) is largest at the nucleus, while the radial probability distribution (probability per interval of radius) peaks at the Bohr radius. These are different quantities.

---

# 3. Variational principle

## 3.1 The basic rule

For a normalized, physically acceptable trial wavefunction \(\psi_{\rm trial}\), calculate

\[
E_{\rm trial}=\langle\psi_{\rm trial}|\hat H|\psi_{\rm trial}\rangle.
\]

The variational principle says

\[
\boxed{E_{\rm trial}\geq E_0},
\]

where \(E_0\) is the exact ground-state energy. A valid trial energy is an upper bound to the true ground energy.

Why? Expand the trial function in the exact energy eigenfunctions:

\[
\psi_{\rm trial}=\sum_n c_n\psi_n.
\]

For a normalized state, its expected energy is

\[
E_{\rm trial}=\sum_n|c_n|^2E_n.
\]

Every exact energy satisfies \(E_n\geq E_0\), and the coefficients' squared magnitudes sum to 1. So this weighted average cannot be below \(E_0\).

If the trial function is not normalized, use the Rayleigh quotient:

\[
E[\psi]=\frac{\langle\psi|\hat H|\psi\rangle}
{\langle\psi|\psi\rangle}.
\]

The denominator divides out the overall scale of the guessed function.

## 3.2 What “optimize the trial function” means

Choose a family of plausible shapes with adjustable parameters, calculate \(E\) as a function of those parameters, and minimize it. The best result is the lowest energy within that chosen family. A poor family can still give a poor estimate; optimization cannot repair a fundamentally unsuitable shape.

For ground states, the variational estimate is an upper bound. This simple statement does not automatically hold for an excited-state guess unless it is constrained to be orthogonal to all lower states.

## 3.3 Oscillator example: why the Gaussian width matters

Try a normalized Gaussian with adjustable width:

\[
\psi_\alpha(x)=\left(\frac{\alpha}{\pi}\right)^{1/4}e^{-\alpha x^2/2},
\qquad \alpha>0.
\]

Large \(\alpha\) means narrow; small \(\alpha\) means broad. For the oscillator potential, the expectation values are

\[
\langle x^2\rangle=\frac{1}{2\alpha},
\qquad
\langle p^2\rangle=\frac{\hbar^2\alpha}{2}.
\]

Thus the kinetic and potential energies are

\[
T=\frac{\langle p^2\rangle}{2m}
=\frac{\hbar^2\alpha}{4m},
\qquad
V=\frac12m\omega^2\langle x^2\rangle
=\frac{m\omega^2}{4\alpha}.
\]

Total energy:

\[
E(\alpha)=\frac{\hbar^2\alpha}{4m}
+\frac{m\omega^2}{4\alpha}.
\]

A very narrow wave has high kinetic energy; a very broad wave spends more time high on the sides of the potential bowl and has high potential energy. Minimize the sum:

\[
\frac{dE}{d\alpha}=\frac{\hbar^2}{4m}
-\frac{m\omega^2}{4\alpha^2}=0
\quad\Longrightarrow\quad
\alpha=\frac{m\omega}{\hbar}.
\]

At this width,

\[
E_{\min}=\frac12\hbar\omega.
\]

The Gaussian happens to have exactly the right shape for the oscillator ground state, so this trial family gives the exact ground energy.

## 3.4 Excited states

If we minimize energy without constraints, the method is pulled toward the ground state. To estimate the first excited state, require the trial function \(\phi\) to be orthogonal to the exact ground state:

\[
\langle\psi_0|\phi\rangle=0.
\]

For a higher excited state, require orthogonality to every lower state. In practice, if lower states are also approximate, their accuracy matters. The particle in a box illustrates the idea: its first excited state has a different nodal pattern from the ground state and is orthogonal to it.

---

# 4. Linear variational method

The previous Gaussian example adjusted one width parameter. In a linear variational calculation, build a trial function from several fixed basis functions and optimize their coefficients:

\[
\psi_{\rm trial}=\sum_{j=1}^{N}c_j\phi_j.
\]

“Linear” means the unknown coefficients \(c_j\) enter as a linear combination. The basis functions themselves can be complicated.

## 4.1 Hamiltonian and overlap matrices

For each pair of basis functions, calculate

\[
H_{ij}=\langle\phi_i|\hat H|\phi_j\rangle,
\qquad
S_{ij}=\langle\phi_i|\phi_j\rangle.
\]

- \(H_{ij}\) is a Hamiltonian matrix element.
- \(S_{ij}\) is an overlap matrix element.
- If the basis is orthonormal, \(S\) is the identity matrix.
- If basis functions overlap, retain the overlap matrix \(S\); do not assume it is the identity.

For coefficient vector \(\mathbf c\), the trial energy is

\[
E(\mathbf c)=\frac{\mathbf c^\dagger H\mathbf c}
{\mathbf c^\dagger S\mathbf c}.
\]

Minimizing with respect to the coefficients gives the generalized eigenvalue problem

\[
\boxed{H\mathbf c=E S\mathbf c}.
\]

A nonzero coefficient vector exists only when

\[
\boxed{\det(H-ES)=0}.
\]

Solving this secular equation gives approximate energies; the corresponding eigenvectors give the coefficients that describe each approximate state. The lowest root is the best ground-state energy in the chosen basis span.

## 4.2 Small two-function illustration

Suppose, purely as a simple matrix example, the two basis functions are orthonormal and the Hamiltonian matrix is

\[
H=\begin{pmatrix}2&-1\\-1&2\end{pmatrix}.
\]

Then \(S=I\), and solving \(\det(H-EI)=0\) gives

\[
(2-E)^2-1=0,
\quad E=1\text{ or }3.
\]

The lower-energy mixture is \((\phi_1+\phi_2)/\sqrt2\); the higher is \((\phi_1-\phi_2)/\sqrt2\). This toy matrix illustrates how the method compares combinations. It is not itself a numerical molecular calculation.

## 4.3 Why more basis functions help—and what they do not guarantee

If we enlarge the basis by adding useful functions, the variational ground-state energy can stay the same or decrease; it cannot increase when the old basis is retained inside the new one. The estimate approaches the exact result as the basis becomes sufficiently flexible.

Energy convergence and wavefunction convergence are not identical. An energy can look stable while some details of the wavefunction are still inaccurate. Also, a basis must describe the important physical features of the state; simply adding irrelevant functions may not help much.

## 4.4 Connection to molecular calculations

In a molecule, basis functions are often centered on atoms. A trial molecular orbital can be written as a weighted sum of those atomic-centered functions. The linear variational method determines the best coefficients and energies within that basis.

This is the mathematical foundation of methods such as LCAO molecular-orbital calculations. In a real molecule the basis functions usually overlap, so the overlap matrix \(S\) matters. For many-electron systems, additional ideas are needed because electrons repel one another; that leads toward Hartree–Fock and other electronic-structure methods.

The IIT course then applies variational ideas to hydrogen polarizability and to chemical bonding, including a valence-bond treatment of H\(_2\). Those are applications of the same core logic, with more complicated trial functions and integrals.

---

# 5. Common points to keep straight

1. **Wavefunction vs. probability:** \(\psi\) is an amplitude; \(|\psi|^2\) is probability density.
2. **Eigenvalue vs. expectation:** an eigenvalue can be a single measurement result; an expectation value is the repeated-measurement average.
3. **Energy levels vs. energy spacing:** the box levels grow as \(n^2\); oscillator levels are equally spaced.
4. **Orbital vs. orbit:** an atomic orbital is a wavefunction/probability pattern, not a classical path.
5. **Variational upper bound:** applies directly to ground-state estimates from valid trial functions.
6. **Trial function vs. exact function:** a trial function is a controlled guess. Optimizing it gives the best result only within its chosen family or basis.
7. **Linear method:** the unknown coefficients are linear; this does not mean the wavefunction is a straight line in space.
8. **Overlap:** distinct basis functions need not be orthogonal. In that case, use \(S\) in \(H\mathbf c=ES\mathbf c\).

# 6. What we can study next

The uploaded course continues with perturbation theory, applications to multi-electron atoms (including helium), and self-consistent-field/Hartree–Fock methods. You also mentioned “HCF”; I have written Hartree–Fock here as the likely intended topic, and we can adjust if you meant something else.

## References for this study session

- Sabyashachi Mishra, *Approximate Methods in Quantum Chemistry*, IIT Kharagpur course packets, especially Lectures 2–13.
- Ira N. Levine, *Quantum Chemistry*, 7th edition (2014).
- Attila Szabo and Neil S. Ostlund, *Modern Quantum Chemistry: Introduction to Advanced Electronic Structure Theory*, as an advanced companion for later electronic-structure topics.
