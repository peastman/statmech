.. _interpretation-of-statistical-quantities:

The Interpretation of Statistical Quantities
############################################

In Chapter :ref:`statistical-description-of-physical-systems` I defined lots of quantities, but said very little about
what they really mean.  Now it is time to return to them.  We will study them in more detail and try to build up an
intuitive understanding of what they represent.


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

    If a system is in equilibrium with a heat bath at temperature :math:`kT`, then its average kinetic energy is
    :math:`kT/2` per degree of freedom.


Thermodynamic Potentials as a Measure of Probability
====================================================

Thermodynamic potentials are confusing.  Not only are they an unfamiliar concept, but as soon as you start trying to do
calculations with them, it is very easy to get all tangled up in a net of subtle mistakes.  In the following sections,
I will approach thermodynamic potentials from three different directions.  I will point out some of the particular
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

Let us go through each term in the Gibbs free energy, and consider why each one should influence the probability.

The first term is simply the energy of the system of interest.  All else being equal, states with lower energy are more
likely to occur.  Why?  Because the energy of the complete system A+B is conserved.  Less energy in A means more
energy in the heat bath, and that means its density of states is larger.  (This was one of our assumptions in deriving
the Maxwell-Boltzmann distribution.  Remember?  We assumed :math:`\mathrm{log}(\Omega_B)` was linear in energy.)

The second term is :math:`P_B V_A`.  This term can be interpeted in exactly the same way, only in terms of volume
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


Thermodynamic Potentials and Thermodynamic Forces
=================================================

According to classical mechanics, if the potential energy :math:`U` of a system depends on a variable :math:`x`, the
system experiences a *generalized force*

.. math::
    Q = -\frac{\partial U}{\partial x}

When the value of :math:`x` changes by an amount :math:`\Delta x`, the system performs *work* equal to

.. math::
    W = Q \Delta x

Since we have defined quantities called "thermodynamic potentials" and "thermodynamic forces", you may be wondering how
closely they are related to potentials and forces of the the conventional, non-thermodynamic kind.  Does the derivative
of a thermodynamic potential give a thermodynamic force?  Does a thermodynamic force perform work?

As soon as we try to answer these questions, we immediately run into the second issue that makes thermodynamic
potentials very confusing: some potentials, as we defined them in section, :ref:`thermodynaic-potentials` *cannot be
differentiated*\ !
