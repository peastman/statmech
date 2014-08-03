Phase Transitions
#################

As you change the macroscopic variables of a system, sometimes its properties will abruptly change, often in a dramatic
way.  For example, it might change from a solid to a liquid, or from a liquid to a gas.  These are examples of *phase
transitions*.  The goal of this chapter is to understand why phase transitions happen and to explore their properties.


A Qualitative Description of Phase Transitions
==============================================

As a familiar example, consider the behavior of water as you change the temperature.  It can exist in liquid, solid
(ice), and gas (steam) phases.  Figure ??? shows what each of these phases looks like at the molecular level.  Let's
consider each of them in turn.

In the solid phase, the molecules form a crystal.  They are arranged in a regular pattern that repeats over and over again.
Each molecule is tightly held in place by hydrogen bonds to its neighboring molecules.  This makes it a very low energy
state.  To move a molecule from its place in the crystal, you need to break those hydrogen bonds.  On the other hand, it
also is a very low entropy state.  The molecules are almost completely immobile, unable to do anything but vibrate
around their fixed positions.

In the liquid phase, the molecules no longer form any repeating pattern.  They are still densely packed together, and
still form lots of hydrogen bonds (though not as many as in the solid phase).  But they are in constant motion, breaking
bonds and forming new ones as they move around.  Consequently, the liquid phase has higher energy than the solid phase,
but also higher entropy.

In the gas phase, the molecules are no longer packed together.  They spread apart to fill whatever space is available
to them.  This means there are very few hydrogens bonds, so the energy is much higher.  But because each molecules has
so much more freedom of movement, the entropy is also much higher.

(This description is a bit of a simplification.  For example, water actually has at least 15(!) different solid phases,
each characterized by a different arrangment of the atoms into a crystal.  But for our purposes, we can ignore those
complications and just think of "ice" as a single phase.)

So which of these phases would you expect to find it in?  Whichever one has the lowest free energy, of course!  And that
depends on temperature.  At very low temperature, :math:`E-TS` is dominated by energy, so the solid phase is most
stable.  As the temperature increases, entropy becomes more important, causing it to transition to the liquid and then
the gas phase.

Suppose you start at very low temperature, so the water is in solid form, and then gradually add heat to it.  As you do
so, the temperature increases.  The molecules remain at their fixed positions within the crystal lattice, but their
vibrations become faster and more energetic.  As the temperature increases, the difference in free energy between the
solid and liquid phases steadily becomes smaller.

This continues until the water reaches a temperature where the free energies of the solid and liquid phases are exactly
equal.  At this point, the two phases have equal equilibrium probabilities.  But that does not mean the ice
immediately starts to melt!  To do that, it needs more energy.  Remember, the liquid phase has higher energy than the
solid phase.  So now you must add a little more heat.  But this time, the temperature does not increase.  Instead, the
heat goes into converting water from solid to liquid form, while the temperature remains constant.

(Actually, the temperature probably does increase momentarily, at least in part of the system.  That causes the liquid
phase to have lower free energy than the solid phase, so a little water melts.  As it melts, kinetic energy is converted
to potential energy as hydrogen bonds are broken, so the temperature decreases again.  Once you allow the system to
fully equilibrate, the upshot is that some ice has melted and the temperature is the same as it was before.)

This continues until all the ice has melted.  The temperature can now begin increasing again.  The energy difference
between the two phases is called the *latent heat* of the transition.  It is the amount of "extra heat" you must add to
the system to convert one phase to the other, heat that does not contribute to changing the temperature.  Any time you
observe a latent heat, that's a sure sign a phase transition has happened.


Phase Diagrams
==============

In the previous section, we considered how the phase of a system can change with temperature.  Of course, the same is
true for every other macroscopic variable.  The stable phase is the one whose free energy is lowest, so any variable
that affects the free energy can also affect the phase.

A diagram showing the stable phase of a system for every combination of macroscopic variables is called its *phase
diagram*.  Figure ??? shows a schematic phase diagram for water as a function of temperature and pressure.  The real
phase diagram is much more complicated, of course; as I said before, water actually has a huge number of different
phases.  But this simplified diagram gives the essential features for the current discussion.

Notice that the line dividing the solid and liquid phases is close to a straight vertical line; changing the pressure
has very little effect on the transition temperature.  The solid and liquid phases are both dense and mostly
incompressible, so pressure changes have little effect on them.  In contrast, the gas phase is very compressible.  If
you increase the pressure, its volume (and hence entropy) decreases, so this has a large effect on the transition
temperature.

We can be more quantitative about this.  For a point on the *phase coexistence curve* (the line separating two phases),
the phases have equal free energy.  Consider two phases labeled 1 and 2, and assume the relevant macroscopic variables
are pressure and temperature.  For an arbitrary point :math:`(P,T)` on the coexistence curve, we can write:

.. math::
    E_1 + PV_1 - TS_1 = E_2 + PV_2 - TS_2
    :label: equal-gibbs-free-energy

Now suppose we move an infinitesimal distance :math:`(dP,dT)` along the curve.  Since the new point is also on the
coexistence curve, the free energies must be equal there too:

.. math::
    E_1 + (P+dP)V_1 - (T+dT)S_1 = E_2 + (P+dP)V_2 - (T+dT)S_2
    :label: displacement-along-coexistence-curve

Subtracting equation :eq:`equal-gibbs-free-energy` from equation :eq:`displacement-along-coexistence-curve` gives

.. math::
    dP \cdot V_1 - dT \cdot S_1 = dP \cdot V_2 - dT \cdot S_2

Rearranging the terms gives:

.. math::
    \frac{dP}{dT} = \frac{S_1-S_2}{V_1-V_2}
    :label: clausius-clapeyron-equation

This is called the *Clausius-Clapeyron equation*.  It says that the slope of the coexistence curve at any point is
simply given by the differences in volume and entropy between the two phases.

The solid and liquid phases of water have very little difference in volume, so the slope is large in magnitude.  It also
is negative: the coexistence curve slopes up to the left.  Water is quite unusual in that its volume actually increases
slightly when it freezes, so :math:`S_1-S_2` and :math:`V_1-V_2` have opposite signs.  In contrast, the gas phase has
much larger volume than the liquid phase, so the slope of the liquid-gas coexistence curve is smaller in magnitude, and
positive.

Because the two curves have different slopes, they draw closer together as the pressure decreases and eventually meet.
The intersection point is called the *triple point*.  It is the unique pressure and temperature at which the solid,
liquid, and gas phases all have identical free energies, so all three phases can exist at the same time.  For even lower
pressures, there is no longer any liquid phase at all.  The system goes directly from solid to gas (a process called
*sublimation*) without any intermediate form.  No matter what temperature you choose, either the solid or gas phase will
always have lower free energy than the liquid phase.

The Clausius-Clapeyron equation can also be written in another form.  Suppose the system is on the phase coexistence
curve, and is entirely in phase 1.  Now consider the thermodynamic process in which we add heat until it has been
entirely converted to phase 2 but the temperature has not changed.  Recall that for an *infinitesimal* change in energy,
:math:`dE=T dS`.  In this case we are adding a finite amount of energy, so we need to integrate over the process.
Fortunately, that is trivial to do.  The temperature is held constant throughout the process, so we can just pull
:math:`T` out of the integral!

.. math::
    \int_{E_1}^{E_2} dE = \int_{S_1}^{S_2} T dS = T \int_{S_1}^{S_2} dS
    
    E_2-E_1 = T(S_2-S_1)

Equation :eq:`clausius-clapeyron-equation` can therefore be written

.. math::
    \frac{dP}{dT} = \frac{E_2-E_1}{T(V_1-V_2)}
    :label: clausius-clapeyron-equation-2

This tells us the slope of the curve is proportional to the latent heat :math:`E_2-E_1` of the transition.


Critical Points
===============

Take another look at Figure ???.  There is an arrow at the top of the solid-liquid coexistence curve to indicate it goes
on forever.  No matter how high you make the pressure, there will always be two distinct phases and a transition
between them.  But the liquid-gas transition is another matter.  The coexistence curve only goes so far, then comes to
an end.  The point at which it ends is called a *critical point*.  Beyond that point, there are no longer separate
liquid and gas phases, just a single phase called a *supercritical fluid*.

To understand why this happens, consider how the liquid and gas phases change as you increase the pressure.  The liquid
phase is difficult to compress, so pressure changes have little effect on it.  The gas phase, on the other hand, is very
compressible.  As you increase the pressure, its volume decreases steadily.  That, of course, means that its entropy
decreases too: less volume means fewer possible positions for each molecule.  At the same time, its energy also
decreases.  As the molecules are forced closer together, it becomes easier for them to form hydrogen bonds, so the
average number of hydrogen bonds steadily increases.

The upshot is that as you increase the pressure, the free energy difference between the two phases decreases.
Eventually it reaches zero, and there is no longer any free energy difference at all.  That is what happens at the
critical point.

To be clear, it is not just that there is no longer a free energy difference.  *There is no longer any difference at all
between the phases*.  The difference between the two phases can be described entirely by two numbers: the average
distance between molecules, and the average number of hydrogen bonds per molecule.  In the liquid phase the molecules
stay close to each other, held together by hydrogen bonds.  In the gas phase, they spread out to fill all available
volume.  But what if they have no extra volume to fill?  If the pressure is high enough, the system no longer has any
ability to increase its entropy by spreading out.  In that case, there is no longer any distinction between the two
phases.  That happens at the critical point.  Beyond it, there is no longer a phase transition, just a single phase.


Metastable Phases and Ergodicity Breaking
=========================================


