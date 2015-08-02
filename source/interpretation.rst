.. _interpretation-of-statistical-quantities:

The Interpretation of Statistical Quantities
############################################

In Chapter :ref:`statistical-description-of-physical-systems` I defined lots of quantities, but said very little about
what they really mean.  Now it is time to return to them.  We will study them in more detail and try to build up an
intuitive understanding of what they represent.


.. _interpretation-of-temperature:

Temperature
===========

Temperature is a quantity we are all familiar with.  You have probably been told that it measures the microscopic
jiggling of atoms: the faster they are moving, the hotter an object feels.  So when I defined it in terms of a
derivative of the density of states, a seemingly unrelated concept, you were probably a little surprised.  To resolve
this seeming paradox, I am going to prove a very important theorem called the *equipartition theorem*.  Once you reach
the end, the significance of temperature will become clear.

In general, the energy of a system can depend in an arbitrary way on all of its microscopic variables, which we will
call :math:`x_1`, :math:`x_2`, etc.  That is, the energy is a function :math:`E(x_1, x_2, \dots)`.  But there are some
very important special cases where it takes particular forms.  Let us make three assumptions:

1. The energy of the system can be written

   .. math::
       E(x_1, x_2, x_3, \dots) = E_1(x_1) + E_2(x_2, x_3, \dots)
   
   That is, the energy separates into two terms.  The first term depends *only* on :math:`x_1`, while the second term
   does not depend on :math:`x_1` at all.

2. :math:`x_1` can be treated as a continuous variable, and can take on any value from :math:`-\infty` to
   :math:`\infty`.

3. The energy is quadratic in :math:`x_1`:

   .. math::
       E_1(x_1) = Cx_1^2
   
   where :math:`C` is a constant.

A particularly important example of this situation is the momentum of a classical particle.  Each momentum variable
:math:`p_i` contributes :math:`p_i^2/2m` to the kinetic energy.

Now we want to answer the question, "What is the average value of :math:`E_1`?"  As we learned in section
:ref:`averages`, that is given by

.. math::
    \langle E_1 \rangle = \frac{\sum E_1 e^{-\beta E}}{\sum e^{-\beta E}}

(For simplicity I am assuming that :math:`E` is the relevant thermodynamic potential; we are working in the canonical
ensemble.  This theorem applies just as well to other ensembles, though.  Just replace :math:`E` by :math:`\Phi` in
all the equations above.)

Now take advantage of assumption 1.  This allows us to factor the above expression:

.. math::
    \langle E_1 \rangle = \frac{\sum e^{-\beta E_2} \sum E_1 e^{-\beta E_1}}{\sum e^{-\beta E_2} \sum e^{-\beta E_1}}

The first sum is identical in both the numerator and denominator, so we can cancel them out:

.. math::
    \langle E_1 \rangle &= \frac{\sum E_1 e^{-\beta E_1}}{\sum e^{-\beta E_1}} \\
    &= -\frac{\partial \mathrm{log} \left(\sum e^{-\beta E_1} \right)}{\partial \beta}

Assumption 2 allows us to replace the sum by an integral:

.. math::
    \langle E_1 \rangle = -\frac{\partial \mathrm{log} \left(\int_{-\infty}^{\infty} e^{-\beta E_1} dx_1 \right)}{\partial \beta}

Finally, we make use of assumption 3 and introduce the change of variables :math:`y \equiv \sqrt{\beta} x_1`:

.. math::
    \langle E_1 \rangle &= -\frac{\partial \mathrm{log} \left(\int_{-\infty}^{\infty} e^{-\beta Cx_1^2} dx_1 \right)}{\partial \beta} \\
    &= -\frac{\partial \mathrm{log} \left(\beta^{-1/2} \int_{-\infty}^{\infty} e^{-Cy^2} dy \right)}{\partial \beta} \\
    &= -\frac{\partial \left(\mathrm{log} \left(\beta^{-1/2} \right) + \mathrm{log} \left(\int_{-\infty}^{\infty} e^{-Cy^2} dy \right) \right)}{\partial \beta} \\
    &= \frac{1}{2 \beta} \\
    &= \frac{kT}{2}
    :label: equipartition

We now see how the statistical definition of temperature matches up with the informal one you are familiar with.
Temperature is a measure of average kinetic energy.  To put it precisely:

.. admonition:: Interpretation of Temperature

    If a system is in equilibrium with a heat bath at temperature :math:`T`, then its average kinetic energy is
    :math:`kT/2` per degree of freedom.

Of course, the equipartition theorem applies equally well to any variable that satisfies the three requirements, not
just to momentum variables.  In a collection of uncoupled harmonic oscillators, the average *potential* energy will also
be :math:`kT/2` per degree of freedom.

Even more generally, when a system is in equilibrium, its total energy (not just kinetic energy) tends to be evenly
distributed among its degrees of freedom.  This is just a rule of thumb, not a rigorous result like the equipartition
theorem.  Still, it is a useful guideline for how to think about systems in equilibrium.

.. admonition:: Example

    What is the average kinetic energy of a gas of :math:`N` rigid diatomic molecules at temperature :math:`T`?
    
    Each molecule is composed of two atoms, so it would normally have 6 degrees of freedom.  But because they are rigid
    (the distance between the two atoms cannot change), that removes one degree of freedom.  The average kinetic energy
    is therefore
    
    .. math::
        \langle E_{kinetic} \rangle = 5N \cdot \frac{kT}{2}


Thermodynamic Potentials as a Measure of Probability
====================================================

Thermodynamic potentials are confusing.  Not only are they an unfamiliar concept, but as soon as you start trying to do
calculations with them, it is very easy to get all tangled up in a net of subtle mistakes.  In the following sections,
I will approach thermodynamic potentials from several different directions.  I will point out some of the particular
issues that make them confusing, and try to help you form a clear understanding of the essential concepts.

The first thing that makes them confusing is that they mix together quantities related to two different systems.  Recall
that we started with a single isolated system, then split it into two pieces called A and B.  A is the system of
interest, the thing we really care about.  B is the heat bath.  Consider the Gibbs free energy as an example.  Let me
restate the definition, including a subscript on every variable to indicate which one it refers to:

.. math::
    G_A = E_A + P_B V_A - T_B S_A

It is very easy to get confused about which system each variable relates to.  For example, it is easy to see the term
:math:`TS` and remember that :math:`T` and :math:`S` are each defined in terms of :math:`\mathrm{log}(\Omega)`, but
forget that their definitions refer to completely different :math:`\Omega`\ s.  :math:`T` is related to the density of
states of the heat bath, while :math:`S` measures the density of states of the system of interest.

A thermodynamic potential is, first and foremost, a measure of how probable it is for a system to be in a particular
state.  It appears in the exponent of the Maxwell-Boltzmann distribution.  Lower values of the potential indicate more
likely states, while higher values indicate less likely states.

Let's go through each term in the Gibbs free energy, and consider why each one should influence the probability.

The first term is simply the energy of the system of interest.  All else being equal, states with lower energy are more
likely to occur.  Why?  Because the energy of the complete system A+B is conserved.  Less energy in A means more
energy in the heat bath, and that means its density of states is larger.  (This was one of our assumptions in deriving
the Maxwell-Boltzmann distribution.  Remember?  We assumed :math:`\mathrm{log}(\Omega_B)` was linear in energy.)

The second term is :math:`P_B V_A`.  This term can be interpreted in exactly the same way, only in terms of volume
instead of energy.  The total volume of A+B is fixed.  Less volume for A means more volume for B, and we assumed the
density of states of B increased with volume.  Microstates of A with lower volume are therefore consistent with more
microstates of B, so they are more likely to occur.

That is all fine as far as microstates are concerned, but the Gibbs free energy describes the probability of
macrostates. Lower energy and volume for A correspond to more probable microstates, but there also are likely to be
fewer of them. :math:`\Omega_A` also increases with energy and volume just like :math:`\Omega_B`. That is what the final
term :math:`T_B S_A` represents. It decreases the potential for macrostates whose entropy (and therefore density of
states) is larger, thus making those macrostates more probable. The actual probability of a given macrostate is
determined by a balance between all three terms. Increasing the energy and volume of system A increases the first two
terms while decreasing the third term. It decreases the probability of each microstate while increasing the total number
of microstates.

If we were working with the grand potential instead of the Gibbs free energy, we would have a different term:
:math:`-\mu_B N_A`.  The interpretation of this term is exactly like the other ones.  The total number of particles in
A+B is fixed.  Fewer particles in A means more in B, which increases its density of states.  (Do not be confused by the
negative sign in front of this term.  That is just to cancel out the extra negative sign that, for purely historical
reasons, appears in the definition of :math:`\mu`.)


Independent and Dependent Variables
===================================

There is a second way that thermodynamic potentials can be interpreted.  It assigns a completely different meaning to
them, while still being similar enough to be confusing.  It has to do with which macroscopic variables we treat as
independent and which ones we treat as dependent.

So far, we have always used macroscopic variables such as energy, volume, and particle number.  These have the important
property that they are also microscopic variables.  Every microstate has a well defined energy, a well defined volume,
a well defined number of particles.  A macrostate simply consists of all the microstates with the specified values for
its variables.

Contrast that with variables such as temperature, pressure, and chemical potential.  These are *not* microscopic
variables.  They are defined in terms of the density of states.  It makes no sense to speak of the temperature or
pressure of a single microstate.  They relate to the distribution of microstates, not to the properties of any single
state.

On the other hand, from a physical perspective it makes perfect sense to think of these quantities as independent
macroscopic variables.  Consider these examples:

* You can keep a system isolated so that its energy remains constant, *or* you can put it in contact with a heat bath
  of fixed temperature.  In the former case, energy is the independent variable.  It is the quantity you control, and it
  has a well defined value.  In the latter case, it makes more sense to view temperature as the independent variable.
  That is now the quantity you control.  The energy no longer has a single fixed value.  It fluctuates continuously as
  the system exchanges energy with the heat bath.  You can, however, calculate an *average* energy
  :math:`\langle E \rangle`.  Furthermore, as we saw in the last chapter, for macroscopic systems the fluctuations about
  the average will be completely negligible.  In that case, it is reasonable to treat energy as if its value were fixed.
  But it has now become a *dependent* variable :math:`E(T)`.

* You can fix the volume of a system, *or* you can put it in contact with a heat bath of fixed pressure.  In the former
  case, volume is the independent variable.  In the latter case, pressure is the independent variable.  The volume now
  fluctuates as it interacts with the heat bath.  For a sufficiently large system, these fluctuations will be
  negligible.  We can therefore treat the volume as a dependent variable with a well defined value :math:`V(P)`.

* Finally, you can fix the number of particles in the system, or you can let it exchange particles with a heat bath of
  fixed chemical potential.  In the former case, :math:`N` is an independent variable.  In the latter case, it is a
  dependent variable :math:`N(\mu)`.

Just to make matters more confusing, the *mathematical* choice of what variables to treat as independent need not match
the *physical* choice of what quantities to control.  Consider a system in contact with a heat bath of specified
temperature and pressure, so that Gibbs free energy is the relevant thermodynamic potential.  Physically speaking,
:math:`T` and :math:`P` are the quantities you control, while :math:`E` and :math:`V` vary in response to them.

Nonetheless, you can still take :math:`E` and :math:`V` as the macroscopic variables defining a macrostate.  In that
case, every macrostate has a strictly fixed energy and volume.  It is defined to consist of all microstates with those
values of :math:`E` and :math:`V`.  On the other hand, the system is no longer in a single, well defined macrostate.  It
continuously fluctuates through a (usually tiny) range of macrostates as it exchanges energy and volume with the heat
bath.

Alternatively, you can choose to treat :math:`T` and :math:`P` as the macroscopic variables.  In that case, the system
is in a single, fixed macrostate.  On the other hand, that macrostate no longer has fixed values for :math:`E` and
:math:`V`.  Only their averages :math:`\langle E \rangle` and :math:`\langle V \rangle` are well defined.  Furthermore,
there is no longer a direct mapping from microstates to macrostates!  Each macrostate represents a *probability
distribution* over microstates, and each microstate has a probability of occurring while the system is in a range of
different macrostates.

These two choices of macroscopic variables lead directly to two different interpretations of the thermodynamic
potential:

1. If each macrostate has a well defined value for each macroscopic variable and consists of a fixed set of microstates,
   then the thermodynamic potential also has a well defined value.  It describes the probability for the system to be
   in that macrostate.

2. If we instead treat each macrostate as a probability distribution over microstates, then the thermodynamic potential
   no longer has a strictly fixed value.  Instead we must view it as an average quantity.  For example,
   
   .. math::
       G = \langle E \rangle + P \langle V \rangle - T \langle S \rangle

Both of these interpretations are widely used.  Furthermore, people often shift fluidly back and forth between them
without giving any indication they have just changed their definitions.  When in doubt, look carefully to see which
macroscopic quantities are being treated as independent variables.


.. _thermodynamic-potentials-and-thermodynamic-forces:

Thermodynamic Potentials and Thermodynamic Forces
=================================================

According to classical mechanics, if the potential energy :math:`U` of a system depends on a variable :math:`x`, the
system experiences a *generalized force*

.. math::
    Q = -\frac{\partial U}{\partial x}
    :label: define-generalized-force

When the value of :math:`x` changes by an amount :math:`\Delta x`, the system performs *work* equal to

.. math::
    W = Q \Delta x
    :label: define-work

Since we have defined quantities called "thermodynamic potentials" and "thermodynamic forces", you may be wondering how
closely they are related to potentials and forces of the conventional, non-thermodynamic kind.  Does the derivative
of a thermodynamic potential give a thermodynamic force?  Does a thermodynamic force perform work?

I need to be very careful how I answer these questions.  All our results so far assume the system is in equilibrium,
and if large changes are happening in the macroscopic variables, it clearly is *not* in equilibrium.  Until we learn
how to deal with situations of this sort, I need to restrict myself to only saying things about systems in equilibrium.

Still, we can at least partly answer these questions now.  When a system is in equilibrium, its dependent macroscopic
variables take on the values that minimize the thermodynamic potential (and hence maximize the probability).  So if we
take a derivative of :math:`\Phi` and set it equal to zero, that will provide information about what happens in
equilibrium.  For example, consider a system in contact with a heat bath of constant temperature and pressure, then
take a derivative with respect to volume:

.. math::
    \frac{\partial G_A}{\partial V_A} &= 0 \\
    &= \frac{\partial E_A}{\partial V_A} + P_B - T_B \frac{\partial S_A}{\partial V_A} \\
    &= \frac{\partial E_A}{\partial V_A} + P_B - kT_B \frac{\partial \mathrm{log}(\Omega_A)}{\partial V_A} \\
    &= \frac{\partial E_A}{\partial V_A} + P_B - P_A

From which we conclude:

.. math::
    -\frac{\partial E_A}{\partial V_A} = P_B - P_A
    :label: force-equals-pressure

This is a remarkable equation.  The left side is an ordinary force of the conventional sort.  It is just a derivative
of the energy, with nothing statistical about it.  Everything we know about forces from classical mechanics can be
directly applied to it.  The right side, on the other hand, is a thermodynamic force (or rather, the difference between
two thermodynamic forces).  And this equation says that, when the system is in equilibrium, the two sides must be
equal to each other.

If the internal pressure :math:`P_A` and external pressure :math:`P_B` are equal, then the equilibrium condition
simplifies to just :math:`\frac{\partial E_A}{\partial V_A}=0`: there must be no net mechanical force.  If there were,
it would cause the volume to change (that being what mechanical forces do).  Clearly the pressure is at least *acting*
like a mechanical force.  For the system to be in equilibrium, the internal pressure, external pressure, and mechanical
force must exactly cancel each other out.

So thermodynamic forces *act* like ordinary forces, but does that mean they *are* ordinary forces?  Can they produce
motion and do work?  To answer that, we must examine them more carefully and understand just what is going on when a
"thermodynamic force" is applied to a system.


The Mechanics of Thermodynamic Forces
=====================================

Consider a balloon filled with gas.  It is subject to three different forces: the outward pressure of the gas inside
the balloon, the inward pressure of the surrounding air, and the elastic tension of the balloon itself that resists
expansion.  As seen from equation :eq:`force-equals-pressure`, at equilibrium these three forces exactly balance each
other out.  If they do not balance, the balloon will expand or contract until they do.  But what is actually happening
at a microscopic level?

Molecules of gas are constantly striking the surface of the balloon.  How do we know that?  Because the density of
states of the gas increases with increasing volume.  If its volume were greater, there would be more microstates
available to it.  The balloon is restricting it from visiting those microstates, and if the balloon were not there, it
would not remain contained in such a restricted volume.

That is what pressure really is: the mechanical force exerted by the gas molecules as they strike against the balloon
(or any other object that restricts their motion).  So pressure is not merely "like" a force.  It *is* a force.  It can
do all the same things other forces can do, including producing accelerations and performing work.

Chemical potential can be understood in exactly the same way.  Imagine a box with a small hole in it, so that
air molecules can diffuse in and out.  The chemical potential is essentially a measure of the density of air molecules.
In equilibrium, we expect the density to be the same inside and outside.  If that is not the case, we expect to find a
net flow of molecules one way or the other until equilibrium is achieved.  On the other hand, if there is another force
involved (such as one that repels molecules away from the interior of the box), then we expect to find different
densities inside and outside.  We can find the equilibrium distribution by looking for the values that minimize the
thermodynamic potential.

Here is one more critical observation about thermodynamic forces: as we saw in section :ref:`thermodynaic-forces`, they
are always proportional to the temperature.  Given the microscopic description above, this is now easier to understand.
For example, pressure is the force of particles randomly striking the walls of a container.  The faster they are moving,
the harder they strike it.  And as we saw in section :ref:`interpretation-of-temperature`, the average velocity of each
particle is proportional to the temperature.  If the temperature were exactly zero so the particles were not moving at
all, there would be no pressure.  All thermodynamic forces would disappear, and all thermodynamic potentials would
simply become equal to the energy.


.. _thermal-equilibrium:

Thermal Equilibrium
===================

In section :ref:`thermodynamic-potentials-and-thermodynamic-forces` we took the derivative of :math:`G` with respect
to volume, and derived a condition for the system to be in equilibrium.  Let's repeat the same calculation, only instead
taking the derivative with respect to energy:

.. math::
    \frac{\partial G_A}{\partial E_A} &= 0 \\
    &= 1 - T_B \frac{\partial S_A}{\partial E_A} \\
    &= 1 - kT_B \frac{\partial \mathrm{log}(\Omega_A)}{\partial E_A} \\
    &= 1 - \frac{T_B}{T_A}

From which we conclude:

.. math::
    T_A = T_B
    :label: equilibrium-temperatures-equal

Unsurprisingly, the requirement is that both subsystems must have the same temperature.  Two systems whose temperatures
are equal are said to be in *thermal equilibrium*.  If you bring them into contact with each other, no energy will flow
between them.  On the other hand, if the systems have different temperatures, there will be a net flow of energy until
their temperatures become equal.

This energy transfer is different from the ones seen in the previous sections, in that it does not involve any
mechanical work.  There is no change to any independent macroscopic variable *other* than energy.  It is simply the
result of random collisions between molecules that transfer kinetic energy from one subsystem to the other.  This type
of energy transfer is known as *heat*.


Intensive and Extensive Variables
=================================

Here is a useful bit of terminology.

Macroscopic variables that are independent of the size of the system are called *intensive variables*.  Temperature,
pressure, and chemical potential are all intensive variables.  For example, the temperature of a system has nothing to
do with how large that system is.

Macroscopic variables that are proportional to the size of the system are called *extensive variables*.  Energy,
volume, number of particles, and entropy are all extensive variables.

If you take two independent systems and then view them as a single combined system, all intensive variables will have
values that are averages of those for the independent systems, whereas all extensive variables will have values that are
the sums of the values for the independent systems.  If you combine two identical systems, the resulting system will
have twice the volume, twice the energy, and twice the entropy of either of the component systems on its own.  But its
temperature, pressure, and chemical potential will be identical to those for the component systems.

If you multiply an intensive variable by an extensive one, the result is an extensive variable.  Thermodynamic
potentials contain many such products.  :math:`PV`, :math:`TS`, and :math:`\mu N` each multiply an intensive variable
by an extensive one to produce an extensive variable.  Thermodynamic forces are always intensive.  Thermodynamic
potentials are always extensive.

The ratio of two extensive variables is an intensive variable.  For example, dividing the number of particles by the
volume produces the *particle density*: :math:`\rho=N/V`.

Nearly all macroscopic variables fall into one of these two categories.  There is nothing especially profound about
this.  It is just a piece of terminology you will need to know.


A Brief Rant: Internal Energy
=============================

If you read most other books on statistical mechanics, you will find that everywhere I have written :math:`E` for
energy, they instead write :math:`U` for "internal energy".  I have intentionally avoided doing that.  At best, internal
energy is a useless distinction, and at worst it can be actively misleading.  I hesitate even to mention it now.  But
since you are likely to encounter it sooner or later, I should at least introduce the concept.

The idea is that the total energy of a system can be divided into three parts: the kinetic energy of the system as a
whole, the potential energy of the system as a whole, and the "internal energy".  Only the last of these affects the
internal dynamics of the system.  For example, if you put your experimental apparatus on an airplane flying at 1000
km/hour, that greatly increases its kinetic energy, but has no effect on your results.  Likewise if you take the
apparatus to the top of Mt. Everest, that greatly increases its potential energy but again does not affect your results.

The problem with this idea is that it is simply wrong.  Every time the airplane encounters turbulence, the bouncing will
add heat to the system, thus affecting your results.  The same thing happens to a lesser extent every time it speeds up,
slows down, turns, or accelerates in any other way.  The only case where the internal energy is fully decoupled from the
overall motion of the system is when it moves at a constant speed in a straight line with no acceleration at all.  But
in that case, the only difference between internal energy and total energy is what reference frame you calculate it in.
Relativity tells us that all your results must be independent of what reference frame you use, so the choice of whether
to use internal energy or total energy is irrelevant.

Similarly, the gravity at the top of Mt. Everest is slightly weaker than at sea level, and that does have the potential
to change your results.  In many (but not all!) cases, the difference is negligible, and in that event the only
difference between internal energy and total energy is that they are offset by a constant.  But the zero point of energy
is always arbitrary; adding a constant never affects behavior.  So once again, it is irrelevant which one you use.

In summary, the choice to use internal energy instead of total energy *by definition* is only correct if it does not
affect any of your results.  If it does affect them, that proves you have defined the internal energy incorrectly. But
it is very easy to define it incorrectly, such as by neglecting a contribution that actually does matter.  And the only
way to make sure is to repeat your calculation using the total energy and verify that the results do not change!  So why
make the distinction in the first place?
