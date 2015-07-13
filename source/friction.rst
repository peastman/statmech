Friction and Fluctuations
#########################

In 1827, Robert Brown was looking through a microscope at pollen grains in water.  He observed that the smallest
particles were in constant motion, jiggling around in a seemingly random way.  This came to be known as *Brownian
motion*.  For many years, the cause of it remained an unsolved mystery.

Finally in 1905, Albert Einstein published a paper with the catchy title, "On the Movement of Small Particles Suspended
in a Stationary Liquid Demanded by the Molecular-Kinetic Theory of Heat," which showed that Brownian motion could be
explained by the random collisions of water molecules with the grains as they underwent thermal motion.  This paper was
important for two reasons.  First, it served as the final conclusive proof for the existence of atoms.  It is remarkable
to realize that as recently as 1905, the very existence of atoms was a controversial subject.  Most chemists had long
since accepted the reality of atoms, but some physicists continued to deny that matter was in any way discrete.

Second, it derived a result that is now known as the *fluctuation-dissipation theorem*.  The main goal of this chapter
is to derive this result and understand what it means.


Friction and Dissipation
========================

Friction is a familiar fact of life.  Rub two objects together and you feel a force resisting the motion.  Place an
object on the floor and give it a push; it will slide a short distance and then stop.  Again, there is a force
resisting its motion: friction.  And something else happens too: the objects moving against each other become warmer,
as when you rub your hands to warm them up or when you strike a match.  The same thing happens in other contexts too.
For example, electrical resistance is really just another type of friction.  If you run a current through a conductor,
a force resists the motion of the electrons, and the conductor becomes warmer.

Friction is such a universal part of our experience, it seems like it must be a fundamental part of the laws of nature.
Yet if you look at the basic equations of classical or quantum mechanics, there is no sign of friction.  A single
isolated particle will continue forever moving in a straight line without slowing down.  If two particles collide, they
bounce away from each other with just as much energy as they started with.  Friction, it appears, only happens to
macroscopic objects.  And there are even situations where macroscopic systems are free from it, such as
superconductivity and superfluidity.  What exactly is friction, and where does it come from?

The answer, of course, is statistical mechanics.  We saw in section :ref:`interpretation-of-temperature` that when a
system is in equilibrium, its kinetic energy is uniformly distributed among all its degrees of freedom.  A macroscopic
object in motion clearly is *not* in equilibrium.  It has one degree of freedom (the center of mass motion) with far
more energy than any other.  If that degree of freedom interacts with others, the system will tend to move toward
equilibrium.  Energy will be transfered out of that one degree of freedom (so the object will slow down) and into all
the others (so the object will become warmer).

That is all friction really is: the tendency of systems to move toward equilibrium when different degrees of freedom
are allowed to interact with each other.

In the process, its energy becomes less useful.  The kinetic energy of a moving macroscopic object is useful energy.  It
can easily be used to do mechanical work.  Thermal energy is less useful.  You need a heat engine with a separate cold
bath to do work with it, and Carnot's theorem sets a strict upper limit on how much work it can do.  This conversion of
useful mechanical energy to less useful thermal energy is called *dissipation*.  We say that friction "dissipates
energy".  That is, it converts mechanical energy to thermal energy without doing any work in the process.


Linear Response Theory
======================

We are now ready to take another step away from equilibrium and examine what happens to a system experiencing friction.
But where do we begin?  All our results so far have applied only to systems in equilibrium.  Even when we studied
thermodynamic processes in Chapter :ref:`thermodynamics`, we only considered transitions between two equilibrium states.
We assumed that if we waited long enough, the system would eventually return to equilibrium, but we said nothing about
how that process took place.  Friction *is* that process.  A system experiencing friction is, by definition, a system
out of equilibrium.

We saw in section :ref:`thermodynamic-potentials-and-thermodynamic-forces` that when a system is in equilibrium, all
mechanical and thermodynamic forces exactly cancel out.  Its macroscopic variables tend to remain fixed.  The converse
is also true: if a system is *not* in equilibrium, the mechanical and thermodynamic forces will in general *not* cancel
out, and the system will experience a net force pushing it back toward equilibrium.  Intuitively, we expect that the
further the system is from equilibrium, the stronger the force will be.  But how exactly does it vary?  We are simply
going to make an assumption:

.. admonition:: Assumption (Linear Response)

    If a macroscopic variable is displaced away from equilibrium by a distance :math:`\Delta x`, the system will
    experience a net restoring force that is linearly proportional to the displacement: :math:`F = -C\Delta x`, where
    :math:`C` is a constant.

This assumption is the basis of *Linear Response Theory*.  The macroscopic variable could be the velocity of a pollen
grain immersed in water, the volume of an inflated balloon, or the electric current traveling through a circuit.  All
that matters is that it interacts with many microscopic degrees of freedom that can act as a heat bath.

How do we justify this assumption?  If the system is not in equlibrium, the net force will almost certainly tend to push
it back toward equilibrium.  For example, the pollen grain will collide with water molecules that slow it down.  Or the
balloon will be bombarded by air molecules that apply pressure to it.  But there is no fundamental reason the force must
be linear in the displacement.

We will justify it in two ways.  First, suppose the force is *not* linear in the displacement.  In that case, we can
expand it in a power series about the equilibrium value.  If :math:`\Delta x` is sufficiently small, all terms after the
linear one will be negligible.  So even though the assumption is not strictly correct, it is still a good approximation
as long as the displacements are small enough.

The second justification is simply an experimental observation: linear response turns out to be a very good description
of many important systems.  Our assumption is not always true, but it is true of many situations; and our conclusions
will only apply to those situations.


Fluctuations
============

Friction is caused by the interaction with a heat bath.  Let us be very clear about that.  A moving object slows down
because it is colliding with molecules in its environment.  In the process, energy is dissipated: the object's kinetic
energy is redistributed among a huge number of microscopic degrees of freedom.  These two phenomena, friction and
dissipation, are really exactly the same thing.

But that is not the *only* effect of being in contact with a heat bath.  Suppose a pollen grain is initially not moving
at all.  In that case, collisions with water molecules will cause it to *start* moving.  In equilibrium, after all,
every degree of freedom should have :math:`kT/2` kinetic energy.  If it starts with less than that, the effect of the
heat bath will be to increase its kinetic energy.

So in equilibrium, the pollen grain will be in constant motion.  Its speed and direction of motion will be constantly
changing, as it is jostled by the surrounding water molecules.  But on average, its kinetic energy will equal the value
given by the equipartition theorem.

We refer to this effect as *equilibrium fluctuations*.  Any variable in equilibrium with a heat bath will be constantly
changing.  The changes will appear random, but they will obey statistical rules determined by the nature of the heat
bath.

These two effects, fluctuations and dissipation, are inseparable from each other.  They are both caused by exactly the
same mechanism: the interaction of the macroscopic variable with a heat bath.  That is the central message of this
chapter.  And because they have the same cause, they are guaranteed to obey certain relationships.  All that remains is
to derive what those relationships are.
