.. _statistical-description-of-physical-systems:

The Statistical Description of Physical Systems
###############################################

Given a physical system, how do you apply statistics to describe it?  What does that even mean?  There are lots of
aspects of the system you might try to compute statistics for, but what approach is the most useful?  This chapter will
attempt to answer these questions by introducing the basic techniques and concepts of statistical mechanics.

Along the way, we will define quantities with names like "temperature", "pressure", and "entropy".  Of course you have
heard these words before and you probably have an idea of what you think they mean.  For the moment, try to put those
ideas aside.  In Chapter :ref:`interpretation-of-statistical-quantities` we will come back to them and try to build up
an intuitive understanding of these quantities.  But for now, just treat them as mathematical definitions.


.. _microstates-and-macrostates:

Microstates and Macrostates
===========================

To describe an isolated physical system with statistics, we begin by making the following fundamental assumption:

.. admonition:: Assumption

    The system can exist in a discrete (but possibly infinite) set of *microstates*.  A microstate defines the values
    of all possible *microscopic variables*.

In a classical system of point particles, for example, a microstate defines the position and momentum of every particle.
In a quantum mechanical system, it defines the value of the wavefunction at every point in space.  To specify what
microstate the system is in, you must give the most detailed description you will ever care about.

You may be wondering whether this is a valid assumption.  What if the microstates are not discrete?  For example, the
position and momentum of a classical particle are continuous, not discrete.  Whether the universe is actually discrete
or continuous at its most fundamental level is still an open question.

Fortunately, this turns out not to matter very much.  You can always turn a continuous variable into a discrete one by
dividing it into very small bins.  For the classical particle, we treat all positions between :math:`x` and
:math:`x+\delta x` and all momenta between :math:`p` and :math:`p+\delta p` as a single microstate.  As long as we
choose :math:`\delta x` and :math:`\delta p` sufficiently small, the exact values turn out to have no effect on most
of our results.

This is illustrated in :autonumref:`Figure,phase space`, which shows the space of possible microstates for a single particle in one dimension.
Each microstate is defined by its values of :math:`x` and :math:`p`.  This space is known as *phase space*, and we will
use it often.  More generally, a system of :math:`N` particles in :math:`d` dimensions has a :math:`2dN` dimensional
phase space.  Every point (or rather, each tiny volume as shown in :autonumref:`Figure,phase space`) in this phase space represents a
microstate.

.. figure:: images/phase_space.*
    :align: center
    :scale: 80
    
    :autonumber:`Figure,phase space`. The phase space of a single particle in one dimension.  Each axis is divided into
    tiny intervals.  The volume defined by the intersection of one interval from each axis is a microstate.

For typical systems, the number of microstates is huge and they describe the system in far more detail than we usually
care about.  Consider a box filled with gas.  You have no way to measure the exact position and momentum of every last
gas molecule, and you would not care about them even if you could measure them.  Instead, you are usually interested in
a small number of *macroscopic variables*: the total energy of the system, the total number of gas molecules, the volume
of space it takes up, etc.  These are things you can measure and that have practical importance.

A *macrostate* is defined by specifying the value of every macroscopic variable.  There may be a huge number of
microstates all corresponding to the same macrostate.  For example, suppose you measure the total energy and volume of
a box of gas.  There are an enormous number of arrangements of the individual gas molecules that all add up to that
energy and volume.  You know the gas is in *one* of those states, but you have no idea *which* one.


.. _the-density-of-states:

The Density of States
=====================

The number of microstates corresponding to a macrostate is called the *density of states*.  It is written
:math:`\Omega(E, V, \dots)`, where the arguments are the macroscopic variables defining the macrostate.

Since we assumed the microstates are discrete, that means :math:`\Omega` is also a discrete function.  Each
variable can only take on specific values, and it is only defined for those values.  In practice, however, we usually
treat :math:`\Omega` as a continuous function.  As long as the allowed values are sufficiently close together, the total
number of states in any given interval will be huge and we can simply think of :math:`\Omega` as the number of
microstates per unit volume in the space defined by the macroscopic variables.  That is why we call it the "density" of
states.

.. admonition:: Example

    Compute :math:`\Omega(E)` for a single free particle in three dimensions.
    
    The energy is given by :math:`E=|\mathbf{p}|^2/2m`.  The microstates are defined by a six dimensional phase space,
    but since the energy does not depend on the positions, we can ignore them and just consider the three dimensional
    space of momentum coordinates.
    
    Each value of :math:`E` corresponds to a two dimensional surface in this three dimensional space, so :math:`\Omega`
    is proportional to the area of that surface.  In this case, it is just a sphere of radius :math:`|\mathbf{p}|`.
    Since the surface area of a sphere is equal to :math:`4 \pi r^2`,
    
    .. math::
        \Omega(E) \propto |\mathbf{p}|^2 \propto E

The proportionality constant in this example depends on what value we choose for :math:`\delta p` in discretizing the
momenta.  In most cases, however, we will only be interested in the ratios of :math:`\Omega` for different values of
:math:`E`, not in its absolute value for single energies, so we can ignore it.

In this example, the density of states increases with increasing energy.  That is nearly always true.  In this case it
grows only linearly with :math:`E`, but it often grows much faster.  Consider another example.

.. admonition:: Example

    Compute :math:`\Omega(E)` for a collection of :math:`N` free particles in three dimensions.
    
    This is nearly identical to the previous example, except we now have :math:`3N` momentum coordinates.  Each value of
    :math:`E` corresponds to a :math:`3N-1` dimensional surface.  Combining all the momenta into a single vector, we can
    write the result as
    
    .. math::
        \Omega(E) \propto |\mathbf{p}|^{3N-1} \propto E^{(3N-1)/2}

For macroscopic systems, :math:`N` will be on the order of 10\ :sup:`23`, and even a tiny increase in energy will
produce a huge increase in the density of states.  For this reason, we usually work with :math:`\mathrm{log}(\Omega)` instead,
which is a much smoother, slower changing function.


The Postulate of Equal *a priori* Probabilities
===============================================

Suppose you have measured a set of macroscopic variables for an isolated system.  You now know which macrostate it is
in, but there may be a huge number of microstates all consistent with that macrostate.  What can you say about which one
of those it is most likely to be in?

The answer, of course, is that you have no idea.  Your measurements do not provide any further information to answer
that question.  Nonetheless, to calculate any averages or other statistical quantities you must assume something.  This
leads us to the following assumption:

.. admonition:: The Postulate of Equal *a priori* Probabilities

     A system has an equal probability of being in any microstate that is consistent with its current macrostate.

Is there any justification for this assumption?  That turns out to be a very complicated question.  In practice it works
very well for many different cases, and there are theoretical arguments for it.  On the other hand, there certainly
are cases where it is not correct.  So instead we will approach the question from a slightly different direction and
treat it as a definition:

.. admonition:: Definition

    An isolated system that satisfies the postulate of equal *a priori* probabilities is said to be in *equilibrium*.

(But note that this definition is usually written in a slightly different way.  We will come back to it in the next
section.)

For the initial part of this book, we will only consider systems in equilibrium.  We will therefore treat this postulate
as a given.  Of course, there are many interesting situations involving systems that are *not* in equilibrium.  We will
examine some of those later in the book.  We will also look at the process by which systems come to be in equilibrium,
and what happens if they are then disturbed from it.


Time Averages and Ensemble Averages
===================================

I was a bit careless with terminology in the last section.  I spoke of the "probability" of a system being in a
particular microstate, but never defined what that meant.  After all, at any given moment the system *is* in a
particular microstate and not in any other.  There is no probability about it.

There are two approaches one can take to defining probabilities in this context.  The first is to realize that the
degrees of freedom making up the system are constantly changing.  At one instant the atoms have particular
positions and momenta, but the next instant they are different.  We therefore define the probability of the system
being in a microstate as the *fraction of time* it spends in that state.  Averages computed using this definition of
probability are called *time averages*.

This is the older of the two definitions.  Boltzmann used this definition in most of his work.  It turns out to have
problems, however, which led to the introduction of a new definition of probability.

Instead of looking at just one system, imagine preparing many identical systems by following the exact same procedure
many times.  All of these systems are in the same macrostate, but each one is in a different microstate.  You have to
simply imagine doing this, because in practice you have only one system in one microstate—but you do not know which one
it is.  We define the probability of the system being in a microstate as the *fraction* of these imaginary systems that
are in that state. The set of all the systems is called a *statistical ensemble*, and averages computed with this
definition of probability are called *ensemble averages*.

You might wonder whether these definitions are equivalent.  Do both types of averages give the same results?  The answer
is an emphatic, "Sometimes."  For some systems they do, and for other system they do not.  We therefore turn this into
another definition:

.. admonition:: Definition

    A system for which time averages and ensemble averages are equal is said to be *ergodic*.

(Isn't that a wonderful word?  Ergodic.  It comes from the Greek words for "work" and "path".  I recommend working it
into your conversation frequently.)

Having hopefully clarified that, we should reconsider the definition from the previous section.  I said that a system
satisfying the postulate of equal *a priori* probabilities (can I abbreviate that PoEapP?) is in equilibrium.  That is
not the definition you will find in most books.  Here is the more common definition:

.. admonition:: Definition (take 2)

    An isolated system is in *equilibrium* if the probability distribution of its microstates does not change with time.

It can be proven that if an isolated system ever satisfies the PoEapP, even for a moment, it will then continue to
satisfy it forever after.  So what I said before was certainly true: an isolated system that satisfies the PoEapP is in
equilibrium by either definition.  Furthermore, when using ensemble averages, the PoEapP is usually true by definition.
To perform any calculation you must first specify what statistical ensemble you are using, and ensembles nearly always
stipulate that macroscopically indistinguishable microstates have equal probabilities.  (Whether an ensemble is a good
description of a particular physical system is a different question, of course, one which must be answered by
experiment.)

But if you use time averages, the situation is more complicated.  A system is initially in some particular microstate.
It will then proceed through a series of other microstates as time passes, but there is no reason it *must* pass through
every microstate that is macroscopically indistinguishable from the original one.  If the system is not ergodic, it
might only pass through a subset of them, never going into others.  Its probability distribution would not satisfy the
PoEapP, but it would still be constant with time.

In this book we will usually work with ensemble averages.  Unless I specifically say otherwise, you should always
assume that probabilities are defined by a statistical ensemble, not by an average over time.


The Maxwell-Boltzmann Distribution
==================================

There is only so much to say about isolated systems.  Real systems are almost never isolated.  They are embedded in some
sort of environment, and the interaction with that environment is responsible for much of their complexity.

We can use a simple trick to extend our analysis to non-isolated systems.  Begin with an isolated system, then split it
into two parts.  Call them A and B.  A is the part we really care about, the thing we want to do experiments on.  B is
the environment it is connected to.  We only care about B to the extent that it affects A.  It is called a *heat bath*.

Here are some examples of the sort of thing I mean:

* Part A is the gas contained in a box.  Part B is the box itself, along with the whole room the box is sitting in.

* Part A is a test tube with chemicals in it.  Part B is a water bath the test tube is sitting in.

* The whole system is the air in a room.  Part A is the carbon dioxide molecules in the air.  Part B is everything else
  (the nitrogen, oxygen, and other trace gasses).

The energy of the system can be decomposed as

.. math::
    E_T = E_A + E_B + E_{AB}

The total energy of the system is the sum of three terms: one that depends only on the degrees of freedom that make up
A, one that depends only on the degrees of freedom that make up B, and one that depends on both parts of the system.

We now make a series of assumptions.

.. admonition:: Assumption

    :math:`E_{AB}` is small enough that we can ignore it and write
    
    .. math::
        E_T \approx E_A + E_B
        :label: assume-interaction-energy-small

This is a somewhat odd assumption.  If :math:`E_{AB}` were really zero, the two subsystems would not interact at all,
and we would just have two independent isolated systems.  Obviously that is not what we want.  But we do want them to be
*weakly coupled*.  :math:`E_{AB}` should be nonzero, but still much smaller than either :math:`E_A` or :math:`E_B`.
Actually, what we really care about is that it is much smaller than the *variations* in the energies of A and B.  If the
energy of A increases, we assume that energy has primarily come out of B, not just from a reduction in the interaction
energy between A and B.

.. admonition:: Assumption

    The degrees of freedom of A and B are specified independently so the density of states factorizes:
    
    .. math::
        \Omega_T = \Omega_A \Omega_B
        :label: assume-omega-factorizes

This is another aspect of requiring the subsystems to be weakly coupled.  The first assumption restricted them from
being coupled through the energy function.  This one restricts them from being coupled through the definitions of their
degrees of freedom.  We must be free to choose a state for A, and then independently to choose a state for B.  One must
not restrict the other.

.. admonition:: Assumption

    The log of the density of states of B can be approximated as linear in energy:
    
    .. math::
        \mathrm{log}(\Omega_B(E_B)) \approx \alpha + \beta E_B
        :label: assume-omega-linear-in-E

Any function can be approximated as linear over sufficiently small intervals (aside from pathological cases like
singularities and discontinuities).  So essentially we are assuming that we only care about a small range of values for
:math:`E_B`.  In practice, what this really means is that B must be much larger than A.  However much the energy of A
fluctuates, it must only have a very small effect on B.  A is a small test tube while B is a large water bath.  A is a
cup of coffee while B is the surrounding room.  

We now want to answer the following question: if the total energy of the system is :math:`E_T`, what is the probability
of A being in *one particular microstate* whose energy is :math:`E_A`?

We can reason this out in a series of steps, using each of our assumptions in turn.

1. The complete system can be in :math:`\Omega_T(E_T)` possible microstates.  By the PoEapP, every one of them is
   equally probable.  Some of those microstates involve A being in the desired microstate and others do not.  We
   therefore conclude:
   
   *The probability of A being in the desired microstate equals the fraction of microstates of the whole system for
   which A is in that microstate.*

2. By the first assumption above, the energy of B is :math:`E_B = E_T-E_A`.

3. By the second assumption, :math:`\Omega_B` is completely independent of what microstate A is in, and depends only on
   :math:`E_B`.  Therefore, the number of microstates of the whole system for which A is in the desired microstate is
   simply equal to :math:`\Omega_B(E_B) = \Omega_B(E_T-E_A)`.

4. By the third assumption, :math:`\Omega_B(E_B) = e^{\alpha+\beta E_B}`.

Combining these results, we find the probability of A being in the desired microstate is

.. math::
    p(E_A) \propto \Omega_B(E_T-E_A) \propto e^{-\beta E_A}

It is conventional to write this in a slightly different form by defining

.. math::
    \frac{1}{kT} \equiv \beta \equiv \frac{\partial \mathrm{log}(\Omega_B(E))}{\partial E}
    :label: define-temperature

:math:`T` is known as the *temperature* and :math:`k` is *Boltzmann's constant*, which equals 1.3806488·10\ :sup:`-23`
Joules/Kelvin.  :math:`\beta` is called the *inverse temperature*.  With this definition, the probability can be
written as

.. math::
    p(E_A) \propto e^{-E_A/kT}

This last step is quite a strange one.  For no obvious reason, we have just introduced a constant with a seemingly
arbitrary value, along with a completely new set of units.  (Just what are "Kelvins"?)  Of course, you probably have
already figured out why.  The concept of "temperature" was established long before statistical mechanics was developed,
and this definition is needed to make the statistical definition match the pre-existing one.  We will examine the
correspondence in Chapter :ref:`interpretation-of-statistical-quantities`.  For the moment, though, just think of it as
an arbitrary mathematical definition.

We have almost answered our question.  The only thing still missing is the proportionality constant.  That is easily
found: we just require that the probabilities of all microstates add to 1.  (The system is certain to be in *some*
state, after all.)  The normalization constant is therefore given by

.. math::
    Z = \sum e^{-E_A/kT}
    :label: define-partition-function

where the sum is taken over all microstates of A.  :math:`Z` is called the *partition function*.  Aside from being a
normalization constant, it turns out to be an interesting function in its own right with some useful properties.  We
will see more of it later.

We can now give the probability for A to be in the desired microstate:

.. math::
    p(E_A) = \frac{e^{-E_A/kT}}{Z}
    :label: maxwell-boltzmann

This is called the *Maxwell-Boltzmann distribution*, and it is probably the single most important equation in this
chapter (or possibly even in this entire book).  Maxwell originally derived it in 1860 based on a mechanical model of
gas molecules.  In the following years it was repeatedly re-derived based on a variety of arguments that extended its
generality.  As you have seen, it is not in any way specific to gas molecules or classical mechanics.  It is valid for
any system that satisfies a very general set of assumptions.


.. _thermodynaic-forces:

Thermodynamic Forces
====================

In the last section we assumed the only macroscopic variable we cared about was energy.  Let us now extend this to more
general cases.  As a concrete example, assume we have two macroscopic variables: energy and volume.  Perhaps we are
dealing with a balloon filled with helium, so it can stretch and contract, exchanging volume as well as energy with the
surrounding air.  The density of states is now a function of both variables, :math:`\Omega(E, V)`.

We can repeat the exact same argument as in the last section, simply replacing :math:`E` with :math:`V`.  This time we
assume :math:`\mathrm{log}(\Omega_B)` is linear in both variables:

.. math::
    \mathrm{log}(\Omega_B(E_B, V_B)) \approx \alpha + \beta E_B + \gamma V_B
    :label: assume-omega-linear-in-V

from which we conclude that the probability of a microstate is given by

.. math::
    p(E_A, V_A) \propto \Omega_B(E_T-E_A, V_T-V_A) \propto e^{-\beta E_A-\gamma V_A}

Once again it is conventional to write this in a slightly different form by defining a new quantity:

.. math::
    P \equiv kT \frac{\partial \mathrm{log}(\Omega_B(E, V))}{\partial V}
    :label: define-pressure

:math:`P` is called the *pressure*.  Using this definition, the probability for A to be in a particular microstate is

.. math::
    p(E_A, V_A) = \frac{e^{-(E_A+PV_A)/kT}}{Z}
    :label: maxwell-boltzmann-with-PV

where the partition function now equals

.. math::
    Z = \sum e^{-(E_A+PV_A)/kT}
    :label: enthalpy-partition-function

There is nothing special about volume.  The same calculation can be done for any macroscopic variable, producing an
identical result.  One other example that is especially important in thermodynamics is :math:`N`, the number of
particles in the system.  Perhaps we are studying a box filled with gas, but the box has a small hole in it allowing
molecules to diffuse in and out.  Rather than defining subsystem A to be particular set of molecules (whatever volume
of space they occupy), we instead define it to be a particular volume of space (whatever molecules it happens to contain
at any moment).  We then define

.. math::
    \mu \equiv -kT \frac{\partial \mathrm{log}(\Omega_B(E, N))}{\partial N}
    :label: define-chemical-potential

:math:`\mu` is called the *chemical potential*.  The negative sign in front of it is just a matter of convention.  The
probability of a microstate is

.. math::
    p(E_A, N_A) = \frac{e^{-(E_A-\mu N_A)/kT}}{Z}
    :label: maxwell-boltzmann-with-mu-N

Quantities like :math:`P` and :math:`\mu` are called *thermodynamic forces*.  Each one is said to be *conjugate* to the
macroscopic variable we differentiated with respect to.  Together, the macroscopic variable and the thermodynamic force
(:math:`V` and :math:`P`, or :math:`N` and :math:`\mu`) form a *conjugate pair*.

"Thermodynamic force" is another very suggestive name.  How do they relate to forces of the more conventional sort?  Do
they act to produce accelerations?  Are they derivatives of potential functions?  We will examine these questions in
Chapter :ref:`interpretation-of-statistical-quantities`.  As with everything else in this chapter, just treat them as
arbitrary mathematical definitions for now.

Having said that, I now need to indulge in a brief rant.  :math:`\mu` is a "thermodynamic force", but it is also called
the "chemical potential".  So is it a force, or is it a potential?  They are not the same thing!  Just to make matters
worse, we will soon encounter another type of quantity called a "thermodynamic potential" (of which :math:`\mu` is *not*
an example).  Could we at least use consistent terminology?  Sadly, the answer is no, we cannot.  These names were
established long ago, and now it is impossible to change them, even when they clearly do not make sense.


Probabilities of Macrostates
============================

Now that we know how to calculate the probability of the system being in a microstate, we can easily do the same for a
macrostate.  Just add up the probabilities for all the microstates it contains.  For simplicity, assume the only
macroscopic variable of interest is energy.  The probability of a macrostate is

.. math::
    p(E_A) = \frac{1}{Z} \sum e^{-E_A/kT}
    :label: macrostate-probability

The sum is taken over every microstate contained in the macrostate.  If there are other macroscopic variables, just use
the appropriate exponential factor.  For example, if the macrostate is defined by both energy and volume, replace
:math:`E_A` by :math:`E_A+PV_A`.

Every term of the sum has exactly the same value, so instead of summing we can just multiply by the number of
microstates:

.. math::
    p(E_A) = \Omega_A(E_A) \frac{e^{-E_A/kT}}{Z}
    :label: macrostate-probability-2

We now define another new quantity:

.. math::
    S = k \cdot \mathrm{log}(\Omega_A)
    :label: define-entropy

:math:`S` is called the *entropy* of the macrostate.  It is just another way of measuring the number of microstates
that make it up.  Given this definition, we can rewrite the probability as

.. math::
    p(E_A) = \frac{e^{-(E_A-TS)/kT}}{Z}
    :label: maxwell-boltzmann-with-TS


.. _thermodynaic-potentials:

Thermodynamic Potentials
========================

We now know how to compute the probability of finding a system in lots of different kinds of states: microstates or
macrostates, specified by arbitrary sets of macroscopic variables.  In every case, the probability takes exactly the
same form:


.. math::
    p = \frac{e^{-\Phi/kT}}{Z}
    :label: maxwell-boltzmann-with-phi

where the only difference is the quantity :math:`\Phi` appearing in the exponent.  This suggests the idea of
*thermodynamic potentials*, energy-like functions that capture the differences between different probability
distributions.  Several of the most common thermodynamic potentials have special names:

.. math::
    \begin{array}{rcll}
    H &=& E+PV & \text{(Enthalpy)} \\
    A &=& E-TS & \text{(Helmholtz free energy)} \\
    G &=& E+PV-TS & \text{(Gibbs free energy)} \\
    \Phi_G &=& E-\mu N-TS & \text{(Grand potential)}
    \end{array}
    :label: thermodynamic-potentials

The term *free energy* can also be used more generally to refer to any thermodynamic potential that describes the
probabilities of macrostates (that is, any thermodynamic potential that includes a :math:`TS` term).  The Helmholtz
free energy, the Gibbs free energy, and the grand potential are all examples of free energies.

You can think about the differences between thermodynamic potentials in two equivalent ways.  First, you can think of
starting with :math:`E` and then adding in terms based on the ensemble you want to use.  You want volume to be
variable?  Then add :math:`PV`.  You want to work with macrostates instead of microstates?  Subtract :math:`TS`.  And
so on.

Alternatively, you can think of all these potentials as special cases of a single potential that includes all possible
terms.  If the volume is held fixed, then :math:`PV` is a constant and can be ignored.  It just changes the
proportionality constant, which gets normalized away when we require the probabilities to add to 1.  If the number of
particles is fixed, then :math:`\mu N` is similarly a constant and can be ignored.  If you are working with microstates
then :math:`TS` is zero.  (Think of a microstate as being a tiny macrostate with exactly one microstate, so
:math:`\Omega` is 1 and :math:`S` is 0).

Just as there are special names for common thermodynamic potentials, some of the corresponding ensembles also have
special names.  These names are purely historical.  They do not have any particular meaning, but they are still widely
used, so you will need to know them.

The *microcanonical ensemble* refers to an isolated system whose energy is constant.  It has equal probability of being
in any microstate with the specified energy, and of course no chance at all of being in any microstate with a different
energy.

The *canonical ensemble* refers to a system that can exchange energy with a heat bath at a specified temperature.  The
corresponding thermodynamic potential is :math:`E` for microstates, or :math:`E-TS` for macrostates.

The *grand canonical ensemble* refers to a system that can exchange both energy and particles with a heat bath of
specified temperature and chemical potential.  The corresponding thermodynamic potential is :math:`E-\mu N` for
microstates, or :math:`E-\mu N-TS` for macrostates.


.. _averages:

Averages
========

The average (or *mean*) of a quantity :math:`x` is defined as

.. math::
    \langle x \rangle \equiv \sum_i x_i p_i
    :label: define-average

where :math:`x_i` is its value in the i'th state, and :math:`p_i` is the probability of that state.  The sum can be over
either microstates or (if :math:`x` is a macroscopic variable) macrostates.  This is an ensemble average.  Its value
depends on the probabilities of the system being in different states; or to say that another way, it depends on what
ensemble we are calculating the average for.  If :math:`\Phi` is the thermodynamic potential for the ensemble, it equals

.. math::
    \langle x \rangle = \frac{\sum_i x_i e^{-\Phi_i/kT}}{\sum_i e^{-\Phi_i/kT}}
    :label: ensemble-average

Two important identities follow directly from the above definition:

.. math::
    \langle x+y \rangle = \sum_i (x_i+y_i) p_i = \sum_i x_i p_i + \sum_i y_i p_i = \langle x \rangle + \langle y \rangle
    :label: average-of-sum

and, if :math:`C` is a constant,

.. math::
    \langle Cx \rangle = \sum_i Cx_i p_i = C \sum_i x_i p_i = C \langle x \rangle
    :label: average-times-constant

Just because :math:`x` has a particular average value, that does not mean it is always exactly equal to that.  Sometimes
it is more and sometimes it is less.  It can be very useful to know how much a quantity tends to vary about its average.
Does it stay within a narrow range, or does it vary widely?  A useful measure of this is its *variance*, defined as

.. math::
    Var(x) \equiv \langle \left(x-\langle x \rangle \right)^2 \rangle
    :label: define-variance

Remembering that :math:`\langle x \rangle` is a constant, we can derive a useful identity for the variance:

.. math::
    Var(x) &= \langle x^2 - 2x \langle x \rangle + \langle x \rangle ^2 \rangle \\
    &= \langle x^2 \rangle - 2 \langle x \rangle \langle x \rangle + \langle x \rangle^2 \\
    &= \langle x^2 \rangle - \langle x \rangle^2
    :label: variance-alternate-form

Another common measure of how much a value tends to vary is its *standard deviation*, which is simply the square root
of the variance.  It is represented by the symbol :math:`\sigma`.  A good rule of thumb is that about 2/3 of the time,
the value will be between :math:`\langle x \rangle-\sigma` and :math:`\langle x \rangle+\sigma`.  The exact fraction
depends on the probability distribution, of course.  We will examine this further in the next chapter.

I mentioned before that the partition function has some interesting and useful properties.  One of them is that
derivatives of :math:`\mathrm{log}(Z)` tend to give averages.  Remember that the partition function is defined as

.. math::
    Z = \sum e^{-\beta \Phi} = \sum e^{-\Phi/kT}

For example,

.. math::
    -\frac{\partial \mathrm{log}(Z)}{\partial \beta} &= -\frac{1}{Z} \frac{\partial Z}{\partial \beta} \\
    &= -\frac{1}{Z} \sum \frac{\partial e^{-\beta \Phi}}{\partial \beta} \\
    &= \frac{1}{Z} \sum \Phi e^{-\beta \Phi} \\
    &= \langle \Phi \rangle
    :label: derive-logZ-beta

Another useful case is to take the derivative with respect to a state variable (either a microscopic or a macroscopic
one).

.. math::
    -kT \frac{\partial \mathrm{log}(Z)}{\partial x} &= -\frac{kT}{Z} \frac{\partial Z}{\partial x} \\
    &= -\frac{kT}{Z} \sum \frac{\partial e^{-\Phi/kT}}{\partial x} \\
    &= \frac{1}{Z} \sum \frac{\partial \Phi}{\partial x} e^{-\Phi/kT} \\
    &= \left\langle \frac{\partial \Phi}{\partial x} \right\rangle
    :label: derive-logZ-state-variable


Quantum Statistical Mechanics
=============================

For simplicity, I will mostly rely on classical mechanics in this book.  But nearly everything I say applies equally
well to quantum mechanics.

For a quantum system, a microstate simply means a value of the wave function (or, if we need to discretize a continuum
of states, a tiny volume of Hilbert space).  Of course you can describe the wave function using any set of basis
functions you want.  The "microscopic variables" of the system are just the amplitudes of the basis functions.  If they
happen to be position eigenstates, then the microscopic variables are the values of the wave function at each point in
space.  But you can just as easily use momentum eigenstates, energy eigenstates, or any other basis you choose.

A "macroscopic variable", on the other hand, is defined as the expectation value of an operator.  If :math:`Y` is the
operator corresponding to some measurable quantity :math:`y` and the system is in microstate
:math:`\left| \Psi \right\rangle`, then

.. math::
    y \equiv \left\langle \Psi \right| Y \left| \Psi \right\rangle
    :label: quantum-macroscopic-variable

This always has a well defined value, even if :math:`\left| \Psi \right\rangle` is not an eigenstate of the operator
:math:`Y`.  A particularly important case is energy, which is the expectation value of the Hamiltonian:

.. math::
    E \equiv \left\langle \Psi \right| H \left| \Psi \right\rangle
    :label: quantum-energy

As long as the system remains isolated, its energy is constant.  Conservation of energy applies just as well to quantum
mechanics as to classical mechanics.

When dealing with quantum systems, we need to be careful to distinguish between different types of probability.  In
statistical mechanics, probabilities always refer to either ensemble averages or time averages.  The "probability" of a
variable having a particular value refers to either a fraction of the members of an ensemble, or to a fraction of time.
But quantum mechanics also has its own probabilities that apply even when a system is in a single known state.  They
describe the probability that a measurement will produce a certain result, *given* that the system is in a particular
state.

The probabilistic features of quantum mechanics *only* come up when you perform a measurement, which is to say, when you
let the system interact with an external measuring device.  As long as the system stays isolated, quantum mechanics is
fully deterministic.  The system is always in a well defined state, and every microscopic and macroscopic variable has a
single well defined value at every moment in time.

It is even possible that the probabilistic features of quantum mechanics are *also* statistical in nature.  When you
allow a system to interact with an external measuring device, that will necessarily introduce noise into the system.
The state of the system is no longer definitely known, because it is subject to unknown forces.  Is it surprising, then,
that we cannot predict the result with complete certainty?

This is a large subject of its own, and a very controversial one.  It can be proven that *if* quantum mechanics is
statistical in nature, it must necessarily possess one or more unintuitive properties such as nonlocality or
retrocausality.  But quantum mechanics is already one of the most unintuitive physical theories ever developed, so that
is hardly an argument one way or the other!  Some physicists would even argue that we already have good evidence for
both nonlocality *and* retrocausality coming from completely unrelated directions.  If so, then statistical
interpretations of quantum mechanics might well be among the very simplest and most intuitive ones.

In any case, when applying statistical mechanics to quantum systems, be sure to distinguish the "probabilities" due to
statistical ensembles from the "probabilities" due to quantum mechanics itself.  At any time other than when you are
actually in the middle of making a measurement, the former ones are the only kind that apply.
