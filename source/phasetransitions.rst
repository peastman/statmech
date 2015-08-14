Phase Transitions
#################

As you change the macroscopic variables of a system, sometimes its properties will abruptly change, often in a dramatic
way.  For example, it might change from a solid to a liquid, or from a liquid to a gas.  These are examples of *phase
transitions*.  The goal of this chapter is to understand why phase transitions happen and to explore their properties.


A Qualitative Description of Phase Transitions
==============================================

As a familiar example, consider the behavior of water as you change the temperature.  It can exist in liquid, solid
(ice), and gas (steam) phases.  :autonumref:`Figure,water` shows what each of these phases looks like at the molecular level.  Let's
consider each of them in turn.


.. figure:: images/water.*
    :align: center

    :autonumber:`Figure,water`. Water molecules arranged into solid, liquid, and gas phases

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
to them.  This means there are very few hydrogens bonds, so the energy is much higher.  But because each molecule has
so much more freedom of movement, the entropy is also much higher.

(This description is a bit of a simplification.  For example, water actually has at least 15(!) different solid phases,
each characterized by a different arrangement of the atoms into a crystal.  But for our purposes, we can ignore those
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
diagram*.  :autonumref:`Figure,water phase diagram` shows a schematic phase diagram for water as a function of temperature
and pressure.  The real phase diagram is much more complicated, of course; as I said before, water actually has a huge
number of different phases.  But this simplified diagram gives the essential features for the current discussion.

.. figure:: images/water_phase_diagram.*
    :align: center
    :scale: 80

    :autonumber:`Figure,water phase diagram`. Schematic phase diagram for water

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

Take another look at :autonumref:`Figure,water phase diagram`.  There is an arrow at the top of the solid-liquid coexistence
curve to indicate it goes on forever.  No matter how high you make the pressure, there will always be two distinct
phases and a transition between them.  But the liquid-gas transition is another matter.  The coexistence curve only goes
so far, then comes to an end.  The point at which it ends is called a *critical point*.  Beyond that point, there are no
longer separate liquid and gas phases, just a single phase called a *supercritical fluid*.

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
between the phases*.  The essential difference between the solid and liquid can be described by two numbers: the average
distance between molecules, and the average number of hydrogen bonds per molecule.  In the liquid phase the molecules
stay close to each other, held together by hydrogen bonds.  In the gas phase, they spread out to fill all available
volume.  But what if they have no extra volume to fill?  If the pressure is high enough, the system no longer has any
ability to increase its entropy by spreading out.  In that case, there is no longer any distinction between the two
phases.  That happens at the critical point.  Beyond it, there is no longer a phase transition, just a single phase.

Why does the solid-liquid coexistence curve go on forever, while the liquid-gas curve ends at a critical point?  What
is different about these two transitions to produce such different behavior?  The answer, it turns out, is a matter of
symmetry.

In physics, a *symmetry* of a system is a way you can transform the system that leaves it unchanged.  Think of a square,
for example.  If you rotate it by 90 degrees around its center, it is unchanged.  The same is true if you rotate it by
180 or 270 degrees.  In each case, the rotation maps the square back onto itself, so you are left with an identical
square.  You also can mirror the square about a horizontal, vertical, or diagonal line passing through its center.  Each
of these is a symmetry of the square.  The set of all symmetries of a system is called its *symmetry group*.

The liquid and gas phases of water have no symmetries.  They consist of molecules arranged at random, not following any
regular pattern, so there is no transformation that leaves them unchanged.  The solid phase, on the other hand, *does*
have symmetries.  For example, if you translate the entire crystal by exactly one lattice spacing, that maps the lattice
back onto itself.  There also are ways you can rotate or mirror the crystal that leave it unchanged.

The solid phase always has these symmetries, independent of pressure and temperature.  There is no point in the phase
diagram at which it does not have them.  Likewise, there is no point in the phase diagram at which the liquid phase
*does* have these symmetries.  That is why the change from one to the other must always involve an abrupt transition in
which the symmetry is formed or destroyed.  In contrast, since the liquid and gas phases have identical symmetry groups,
you can follow a path through the phase diagram that continuously changes one into the other.

This idea is called the *Landau symmetry principle*.  It states that if two phases have different symmetry groups, they
must always be separated by a phase transition.  No matter what path you take between them, there must be some point at
which the system abruptly changes from one phase to the other.


Metastable Phases and Ergodicity Breaking
=========================================

It takes time for ice to form.  It begins with just a few molecules forming the seed of a crystal.  It then grows as
more molecules bind to it one at a time, each one finding its proper place in the growing lattice.

Suppose you take some liquid water and then lower its temperature very quickly.  If you do it fast enough, the water
will not have time to form an ice crystal.  Instead it forms a different state of matter called *amorphous ice*.  It is
a solid where each molecule is rigidly held in place by hydrogen bonds, just like regular ice.  But it does not have
a regular repeating crystal structure, and its energy is higher than that of regular ice.

Amorphous ice is an example of a *metastable phase*.  It represents a local minimum of the free energy, but not the
global minimum.  Given enough time, it will eventually convert to crystalline ice as the system equilibrates and finds
the global free energy minimum.  But "enough time" could be a very, very long time, far longer than any experiment you
care to do.  The molecules must break their existing hydrogen bonds then rearrange themselves.  That takes energy.  The
lower the temperature, the less energy is available for doing it, so the longer it takes.  On Earth, amorphous ice is
very rare, but in the cold of interstellar space it is believed to be the most common form of ice.

Metastable phases are an example of *ergodicity breaking*.  Recall that an ergodic system is one for which time averages
and ensemble averages are equal.  This is a matter of time scale, of course.  Given enough time, all systems are
ergodic.  A system starting from one state will eventually reach every other possible state.  Even if there is not
enough energy to cross a barrier, quantum tunneling will eventually take it through.  But you might have to wait a
*very* long time, possibly much longer than the age of the universe.  In that case, the system's probability
distribution is, for all practical purposes, unchanging.  The system is in equilibrium, but it is not ergodic.  Time
averaged properties do not equal the corresponding ensemble averages.


The Ising Model
===============

Now that you have a qualitative understanding of how phase transitions happen, I want to take one example and work
through it in some detail.  The example, called the *Ising model*, is a popular model for magnetic solids.  Imagine a
collection of atoms arranged in a rectangular grid, as shown in :autonumref:`Figure,ising model`.  Each atom has an
intrinsic magnetic moment called its *spin*.  The spin of an atom can take on two possible values, called "up" and
"down", as indicated by arrows in the figure.

.. figure:: images/ising_model.*
    :align: center
    :scale: 80
    
    :autonumber:`Figure,ising model`. An Ising model

The energy of the system is given by

.. math::
    E = -H \sum_{i=0}^N \sigma_i - J \sum_{<i,j>} \sigma_i \sigma_j
    :label: ising-hamiltonian

:math:`\sigma_i` is the spin of the i'th atom.  It equals either 1 (spin up) or -1 (spin down).  The first sum describes the
interaction of the spins with an external magnetic field :math:`H`.  The energy is minimum when a spin points parallel
to the external magnetic field.  The second sum is taken only over pairs (i,j) that are nearest neighbors in the grid,
and it describes the interaction of the spins with each other.  The interaction energy of a pair of adjacent spins is
minimum when they point in the same direction if :math:`J>0`, or when they point in opposite directions if :math:`J<0`.

:autonumref:`Figure,ising model` shows a two dimensional grid of atoms, but you can just as easily define one dimensional or
three dimensional Ising models.  In fact, you can even define Ising models in more than three dimensions, though of
course that no longer corresponds to any physical arrangement of atoms.  The dimensionality determines how many terms
appear in the second sum of equation :eq:`ising-hamiltonian`.  In :math:`d` dimensions, every spin has :math:`2d`
nearest neighbors.

An important macroscopic property of the Ising model is the *magnetization* defined by

.. math::
    M \equiv \langle \sigma_i \rangle = \frac{\sum_i \sigma_i}{N}
    :label: define-magnetization

We want to understand how :math:`M` varies as you change other macroscopic variables like :math:`H` and :math:`T`, and
to determine whether the system ever undergoes a phase transition.  To do this, we need to consider the balance between
two competing factors: energy and entropy.

The entropy is the easier one to deal with.  In fact, we already solved this problem in section
:ref:`the-binomial-distribution`!  In that section we considered a collection of :math:`N` oxygen molecules that could
each be in the left or right half of a room, whereas now we have a collection of :math:`N` spins that can each be up or
down.  Physically these are completely different situations, but mathematically they are identical: :math:`N`
independent variables that can each take on two possible values.  We found there that the density of states was given by

.. math::
    \Omega(m) = \frac{N!}{m!(N-m)!}
    :label: ising-density-of-states

where :math:`m` is now the number of spins that point up.  The entropy is then given by
:math:`S = k \mathrm{log}(\Omega)`, and the magnetization is given by

.. math::
    M = \frac{(+1)(m) + (-1)(N-m)}{N} = \frac{2m}{N}-1
    :label: magnetization-from-number-of-spins

The energy is more complicated to deal with.  The Ising model can exhibit a variety of behaviors depending on the values
of :math:`H` and :math:`J`.  To get a sense of the range of possibilities, let's consider some specific cases.

:math:`H=0, J>0`: In this case, the energy is minimized when every spin has the same value so :math:`\sigma_i \sigma_j = 1` for
every pair of interacting spins.  The most likely microstates therefore correspond to :math:`M=1` and :math:`M=-1`.
It doesn't matter *which* value it has.  All spins up or all spins down have
identical energies, so their equilibrium probabilities are equal.  On the other hand, it might be very difficult for the
system to transition between them.  Initially, every spin you flip increases the energy of the system.  At low
temperature, it might take a prohibitively long time to get over the barrier, so the system is effectively frozen in one
state or the other.

This is another type of ergodicity breaking.  It is more specifically known as *spontaneous symmetry breaking*.  The
system has an intrinsic symmetry, that flipping the direction of every spin has no effect on the energy.  For every
possible microstate, there is another microstate with identical energy and opposite spin.  According to the ensemble
average, we should therefore find :math:`\langle M \rangle=0`.  But in practice, the symmetry is broken.  The system is
always found near *one* of the two energy minima at :math:`\langle M \rangle=1` or :math:`\langle M \rangle=-1`, but it
is unable to transition between the two.  Which one we find it in is determined entirely by initial conditions.  The
time averaged magnetization is non-zero, in contrast to the ensemble average.

At high temperature, the case is completely different.  Entropy is maximum when half the spins point up and half point
down: right at the peak of the energy barrier!  For sufficiently high temperature, entropy will dominate over energy,
the numbers of up and down spins will be roughly equal, and the average magnetization will be 0.

This certainly sounds like it *could* be two phases: a low temperature phase where symmetry is broken and
:math:`\langle M \rangle \ne 0`; and a high temperature phase where entropy dominates and :math:`\langle M \rangle=0`.
But does this change happen gradually with increasing temperature?  Or is there some temperature at which a phase
transition takes place and the magnetization abruptly goes to 0?  That remains to be seen.

:math:`H=0, J<0`: In this case, the energy is minimized when :math:`\sigma_i \sigma_j = -1` for every pair of interacting spins.
Each spin needs to point in the opposite direction to all its neighbors.  Think of a chess board, where the black
squares have spin up and the white squares have spin down.  That is the minimum energy configuration.

This case also involves spontaneous symmetry breaking.  If instead the white squares have spin up and the black squares
have spin down, the energy is equally low.  And just as in the :math:`J>0` case, there is a large energy barrier between
the two minimum energy states, so at low temperature it will be impossible for the system to transition between them.

There is an important difference, though.  In this case, the low temperature phase *also* has
:math:`\langle M \rangle=0`, so even if a phase transition happens, we will not be able to detect it by monitoring the
magnetization.  Nonetheless, the two phases are very different from each other.  For example, the low temperature phase
still has *long range order*.  If you know the value of one particular spin, that provides information about the likely
value of every other spin in the system, even ones that are arbitrarily far away!  If you observe a black square to have
spin up, you can guess that every other black square also has spin up, and every white square has spin down.  (You don't
*definitely* know the states of other spins, of course.  Perhaps the one you measured had been flipped by a thermal
fluctuation.  But you still have better than even odds of getting it right, and that is true no matter how far apart two
spins are.)  The high temperature phase does not have long range order.  If you know the value of one spin you can make
a good guess about the values of its nearest neighbors (they are most likely to point in the opposite direction), but
the amount of information rapidly decreases with increasing distance.

:math:`H \ne 0, J=0`: In this case, the spins do not interact with each other at all.  We are effectively dealing with
:math:`N` independent spins, and the energy is minimized when all of them point in the same direction as the external
magnetic field.  It is hard to see how this could possibly give rise to a phase transition.  At low temperature, all
spins will tend to align with :math:`H`.  At high temperature, entropy will dominate and we expect the spin directions
to be random.  But since each spin is independent of all the others, the collective behavior should be identical to the
average behavior of any single spin taken on its own.  The average magnetization should change smoothly with
temperature as predicted by the Maxwell-Boltzmann distribution for an isolated spin.

This case does have one very odd feature.  The energy is minimum when every spin is parallel to :math:`H`.  As you flip
spins one at a time, the energy and entropy both increase steadily.  This continues until half the spins are up and half
are down, at which point the entropy is maximum.  As you continue to flip more spins, the energy continues to increase,
but the entropy begins to *decrease*.  This continues until all the spins point opposite to :math:`H`, at which point
the energy is maximum and the entropy has returned to its minimum value.

So the entropy can decrease with energy.  Is that really so strange?  Well, remember that the temperature is defined by
:math:`\frac{1}{T} = \frac{\partial S}{\partial E}`.  If :math:`S` decreases with :math:`E`, that means the temperature
is negative!

How can temperature be negative?  What does that even mean?  We found in section :ref:`interpretation-of-temperature`
that temperature measures the average kinetic energy per degree of freedom.  How can the kinetic energy possibly be
negative?  But of course, I have just given the key to the mystery: there is no kinetic energy in the Ising model!  It
is a highly simplified model that completely omits any motion of the atoms that make up the grid.  In any real system,
of course, the atoms *would* be able to move, they would have kinetic energy, and the entropy of those degrees of
freedom would increase monotonically with energy.

Negative temperature *is* still a well defined concept, but it is also an esoteric one.  It is rare for a real
physical system to have negative temperature, and it is quite possible you will never encounter one.


Non-Interacting Spins
=====================

Let's start with the :math:`J=0` case, since it is the simplest one to deal with.  Consider just a single isolated spin.
It has only two microstates, :math:`\sigma=1` and :math:`\sigma=-1`, so we can immediately write down the partition
function:

.. math::
    Z = e^{H/kT} + e^{-H/kT}
    :label: single-spin-partition-function

The average value of the spin is

.. math::
    \langle \sigma \rangle &= (1)p(\sigma=1) + (-1)p(\sigma=-1) \\
    &= \frac{e^{H/kT} - e^{-H/kT}}{e^{H/kT} + e^{-H/kT}} \\
    &= \mathrm{tanh}(H/kT)
    :label: single-spin-average

Notice that the magnetization only depends on :math:`H` and :math:`T` through their ratio :math:`H/T`.  If you change
the external magnetic field, that rescales the temperature dependence but otherwise does not affect the behavior.

In the limit of low temperature (or equivalently, of high magnetic field), one of the two exponentials goes to zero.
If :math:`H>0`, :math:`e^{-H/kT} \to 0` and :math:`\langle \sigma \rangle \to 1`.  Alternatively if :math:`H<0`, then
:math:`e^{H/kT} \to 0` and :math:`\langle \sigma \rangle \to -1`.  The spin simply aligns with the magnetic field.

In the limit of high temperature (or low magnetic field), both exponentials go to 1 and
:math:`\langle \sigma \rangle \to 0`.  In this case, the spin is equally likely to be found in either state, so the
average magnetization is zero.

Now consider the full Ising model.  Because the spins do not interact with each other, each one simply behaves as
described above.  The average over spins is identical to the ensemble average for a single spin, and the magnetization
is given by

.. math::
    M = \mathrm{tanh}(H/kT)
    :label: noninteracting-ising-magnetization


Mean Field Theory
=================

Now consider the case where :math:`J \ne 0`.  In principle we just need to write down the free energy and find the state
that minimizes it for every value of :math:`H` and :math:`T`.  That's easier said than done!  In one dimension, the
calculation is reasonably straightforward.  In two dimensions it is extremely difficult.  In three dimensions, it has
never been successfully solved.  Sadly, this is typical of most real world physics problems: they are too complicated to
solve exactly.  We need to use a different approach: either make simplifying assumptions that let us solve them
approximately, or use a computer to solve them numerically.

A very common technique for studying phase transitions is called *Mean Field Theory*.  This isn't so much a specific
approximation as a general idea that can be applied in many ways to many kinds of problems.  It always involves
averaging over fluctuations, replacing details with a simpler calculation that (hopefully) matches them in an average
sense.

To motivate the particular approximation we will use, notice that the energy of the Ising model can be rewritten as

.. math::
    E &= -\sum_{i=0}^N \sigma_i \left(H+J \sum_{<j>} \sigma_j \right) \\
    &= -\sum_{i=0}^N \sigma_i \left(H+2dJ \langle \sigma_j \rangle^\prime \right)
    :label: ising-hamiltonian-version-2

where the notation :math:`\langle \dots \rangle^\prime` indicates that we are averaging only over the :math:`2d` nearest neighbors
of spin :math:`i`.  You can think of this as measuring the average magnetic field spin :math:`i` experiences from the
other spins it interacts with.  We now make the following approximation: replace :math:`\langle \sigma_j \rangle^\prime`
with :math:`\langle \sigma_i \rangle`.  That is, we assume the average over each spin's nearest neighbors simply equals
the average over the entire system.  This allows us to write

.. math::
    E \approx -(H+2dJM)\sum_{i=0}^N \sigma_i
    :label: mean-field-ising-hamiltonian

But this has precisely the same form as the non-interacting Ising model we studied in the previous section!  The
external magnetic field has just been replaced with an effective "mean field" :math:`H+2dJM` that combines the external
field with the average field produced by the nearest neighbors of each spin.  We can therefore use equation
:eq:`noninteracting-ising-magnetization` to write

.. math::
    M = \mathrm{tanh}\left(\frac{H+2dJM}{kT}\right)
    :label: mean-field-ising-magnetization

Notice that the magnetization :math:`M` appears on both sides of this equation.  We need to solve it to find which
values of :math:`M` produce self-consistent solutions in the mean field approximation.  If there is more than one
solution, we can evaluate the free energy of each one to determine which is most stable.

.. figure:: images/mean_field.*
    :align: center
    
    :autonumber:`Figure,mean field`. :math:`y=M` and :math:`y=\mathrm{tanh}\left(\frac{H+2dJM}{kT}\right)` plotted
    against each other for various values of :math:`H` and :math:`J`.  The points where they intersect are solutions
    to equation :eq:`mean-field-ising-magnetization`.  (a) :math:`H=0`, :math:`\frac{2dJ}{kT}=\frac{1}{2}`.
    (b) :math:`H=\frac{kT}{2}`, :math:`\frac{2dJ}{kT}=\frac{1}{2}`.  (c) :math:`H=0`, :math:`\frac{2dJ}{kT}=2`.
    (d) :math:`H=kT`, :math:`\frac{2dJ}{kT}=2`.
    
We can easily do this numerically for any values of :math:`H`, :math:`J`, and :math:`T`.  :autonumref:`Figure,mean field`
shows the left and right sides of equation :eq:`mean-field-ising-magnetization` plotted against each other for various
values.  For simplicity, I will only consider the case :math:`J>0`.  There are a few main possibilities:

* If :math:`2dJ/kT \le 1`, there is exactly one solution.  It corresponds to :math:`M=0` if :math:`H=0`
  (:autonumref:`Figure,mean field`\ (a)).  Otherwise, :math:`M` has the same sign as :math:`H`
  (:autonumref:`Figure,mean field`\ (b)).  The system is magnetized by the applied field.

* If :math:`2dJ/kT>1`, there may be up to three solutions (:autonumref:`Figure,mean field`\ (c)).  Whichever one has the
  lowest free energy will be the stable one.  As long as the temperature is low enough for energy to dominate over
  entropy, that will always be the one in which the system is most strongly magnetized in the direction of :math:`H`.
  If :math:`H=0`, both the magnetized solutions have equal energy and are equally stable.  (The solution near
  :math:`M=0` is still unstable, being a state of high energy.)

* If :math:`H` is sufficiently large there is only one solution (:autonumref:`Figure,mean field`\ (d)).  The only
  possibility is that the system is magnetized by the applied field.

.. figure:: images/ising_phase_diagram.*
    :align: center
    :scale: 80
    
    :autonumber:`Figure,ising phase diagram`. Ising model phase diagram

Combining these observations yields the phase diagram shown in :autonumref:`Figure,ising phase diagram`.  At low temperature
the phase diagram is divided into two phases corresponding to :math:`M>0` and :math:`M<0`.  The stable phase is the one
for which :math:`M` has the same sign as :math:`H`, but the magnetization remains nonzero even in the limit
:math:`H \to 0`.  The system therefore undergoes a phase transition in which :math:`M` changes discontinuously as it
crosses over the coexistence curve at :math:`H=0`.  These phases are said to be *ferromagnetic*, in reference to the way
iron (*ferrum* in Latin) can be magnetized by an external field, and then remains magnetized even when the external
field is removed.

The size of the discontinuity decreases with increasing temperature, and it reaches zero at the critical temperature
:math:`T_C=2dJ/k`.  That is, the coexistence curve ends in a critical point.  Beyond :math:`T_C`, there is only a single
phase in which :math:`M` changes continuously and is always parallel to :math:`H`.  Unlike the ferromagnetic phases,
:math:`M=0` whenever :math:`H=0`.  This phase is said to be *paramagnetic*.

All of this sounds reasonable, but is it correct?  Mean field theory is an approximation.  How good an approximation is
it?  How accurate are its results?

Our simplification was to replace an average over the nearest neighbors of one spin by an average over all spins in the
entire system.  Intuitively, we might expect that the more neighbors each spin has, the better an approximation this
will be.  Indeed, this expectation turns out to be correct.

In one dimension where each spin has only two neighbors, mean field theory fails rather badly.  The accurate calculation
shows that the ferromagnetic phase is only stable at :math:`T=0`.  For any nonzero temperature, the system is
paramagnetic.  This is qualitatively very different from the predictions of mean field theory.

In two dimensions where each spin has four neighbors, it does much better.  Mean field theory gives a qualitatively
correct description of the phase diagram.  Its quantitative predictions are not exactly right, but they are still in
the correct general range.  In three dimensions where each spin has six neighbors, they are even closer.
