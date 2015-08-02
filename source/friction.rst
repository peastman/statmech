.. _friction-and-fluctuations:

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

Second, it helped to form the foundation for the study of friction and equilibrium fluctuations based on statistical
mechanics.  The goal of this chapter is to learn how to describe Brownian motion, and to understand the deep connection
between the seemingly unrelated phenomena of friction and fluctuations.


Friction and Dissipation
========================

Friction is a familiar fact of life.  Rub two objects together and you feel a force resisting the motion.  Place an
object on the floor and give it a push; it will slide a short distance and then stop.  Again, there is a force
resisting its motion: friction.  And something else happens too: the objects moving against each other become warmer,
as when you rub your hands to warm them up or when you strike a match.  The same thing happens in other contexts too.
For example, electrical resistance is really just another type of friction.  If you run a current through a conductor,
a force resists the motion of the electrons, and the conductor becomes warmer.

Friction is such a universal part of our experience, it seems like it must reflect something fundamental in the laws of nature.
Yet if you look at the basic equations of classical or quantum mechanics, there is no sign of friction.  A single
isolated particle will continue forever moving in a straight line without slowing down.  If two particles collide, they
bounce away from each other with just as much energy as they started with.  Friction, it appears, only happens to
macroscopic objects.  And there are even situations where macroscopic systems are free from it, such as
superconductivity and superfluidity.  What exactly is friction, and where does it come from?

The answer, of course, is statistical mechanics.  We saw in section :ref:`interpretation-of-temperature` that when a
system is in equilibrium, its kinetic energy is uniformly distributed among all its degrees of freedom.  A macroscopic
object in motion clearly is *not* in equilibrium.  It has one degree of freedom (the center of mass motion) with far
more energy than any other.  If that degree of freedom interacts with others, the system will tend to move toward
equilibrium.  Energy will be transferred out of that one degree of freedom (so the object will slow down) and into all
the others (so the object will become warmer).

That is all friction really is: the tendency of systems to move toward equilibrium when different degrees of freedom
are allowed to interact with each other.

In the process, its energy becomes less useful.  The kinetic energy of a moving macroscopic object is useful energy.  It
can easily be used to do mechanical work.  Thermal energy is less useful.  You need a heat engine with a separate cold
bath to do work with it, and Carnot's theorem sets a strict upper limit on how much work it can do.  This conversion of
useful mechanical energy to less useful thermal energy is called *dissipation*.  We say that friction "dissipates
energy".  That is, it converts mechanical energy to thermal energy.


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

How do we justify this assumption?  If the system is not in equilibrium, the net force will almost certainly tend to push
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
same mechanism: the interaction of the variable with a heat bath.  That is the central message of this
chapter.  And because they have the same cause, they are guaranteed to obey certain relationships.  All that remains is
to derive what those relationships are.

.. _brownian-motion:

The Langevin Equation
=====================

Let's write Newton's Second Law for a particle undergoing Brownian motion in water: :math:`F = m \ddot{x}`.  (For
simplicity we will work in one dimension, but the generalization to more dimensions is trivial.  Just turn :math:`x`
and :math:`F` into vectors.)  In this
equation, :math:`F` is the force exerted on the particle by the surrounding water molecules.  The details of those
interactions are enormously complicated and constantly changing, so we need to look for an approximate description of
it.  What would be a reasonable approximation?

The first thing we might try is using the assumption of linear response, so the force at any moment is proportional to
the velocity: :math:`m \ddot{x} = -\gamma \dot{x}`.  The parameter :math:`\gamma` is called the *friction coefficient*.
The solution to this differential equation is given by:

.. math::
    \dot{x}(t) = \dot{x}(0) \cdot e^{-\frac{\gamma}{m}t}
    :label: decaying-velocity

For a truly macroscopic system, this description might be sufficient.  Whatever velocity the object starts with, it
exponentially decays toward zero.  But Brownian motion is not precisely a macroscopic phenomenon.  It applies to
particles that are much larger than a water molecule, but still small enough that you need a microscope to see them.
And the whole point is that their velocity does *not* decay to zero.  They remain in motion due to the constant
collisions with water molecules.  By ignoring the forces applied by those random collisions, we have simplified things
too far.

We can still assume linear response, but now we will only take it as a statement about the *average* force on the
particle.  At any given instant, the force could be different.  This leads to the following equation, known as the
*Langevin equation*:

.. math::
    m \ddot{x} = -\gamma \dot{x} + R
    :label: langevin-equation

:math:`R` is a "random" force describing the rapidly fluctuating interactions between the particle and water
molecules.  We cannot hope to write an exact function for it, but we can still describe it statistically.  We will make
the following assumptions about it:

1. :math:`\langle R \rangle = 0`.  We already separated out the average force into its own term, so :math:`R` must have
   a mean of 0.
   
2. It is independent of :math:`x`.  The interaction between the particle and the water is the same no matter where in
   the water bath the particle is located.

3. Because it varies so rapidly and chaotically, we assume it is uncorrelated with itself except over very short time
   spans.  More precisely, we assume there is some maximum time :math:`\tau` over which it has any correlations, so that

   .. math::
       \langle R(t) R(t+\delta t) \rangle = 0 \text{ if } \delta t > \tau
       :label: langevin-noise-uncorrelated

4. We also assume the *rate* at which correlations decay is independent of time, so that
   :math:`\langle R(t) R(t+\delta t) \rangle` is independent of :math:`t`.  It depends only on :math:`\delta t`.  The
   overall statistical properties of the random force are the same at all times.

These assumptions have an important consequence.  In most situations, we do not care about the instantaneous value of
:math:`R`, only its integral over some time period that is long compared to :math:`\tau`.  We can break up that integral
into many pieces, each covering a span of length :math:`\tau`:

.. math::
    \int_0^t R(t') dt' = \int_0^\tau R(t') dt' + \int_\tau^{2 \tau} R(t') dt' + \int_{2 \tau}^{3 \tau} R(t') dt' + \dots
    :label: integrated-noise-as-sum

So the integral is a sum of independent terms, each drawn from the same distribution.  That is exactly the sort of
case we studied in Chapter :ref:`very-large-numbers`, so we can immediately apply the central limit theorem and conclude
that the integral obeys a normal distribution with mean 0 (because :math:`\langle R \rangle = 0`), and whose standard
deviation scales with :math:`\sqrt{t}`.  All that, without evaluating a single integral or knowing anything about the
details of :math:`R(t)`!

Before we dive into the math, let's take a moment to look at the Langevin equation and try to understand it intuitively.
There are two terms on the right side.  The first one always points opposite to the velocity, so it tends to
slow the particle down.  If it were the only term, it would lead to exponentially decaying velocity as in equation
:eq:`decaying-velocity`.  The second term prevents that from happening by constantly applying random kicks to the
particle.  Essentially, there is one term that removes energy and one term that adds energy.  When the system is in
equilibrium, the two terms will exactly balance out so the average energy remains constant.  The magnitude of the random
force will of course depend on temperature: the hotter the system, the faster the water molecules will be moving, and
the harder they will hit the particle.  We therefore expect there should be some relationship between the temperature,
the friction coefficient, and the magnitude of the random force.  As we will see soon, that is indeed the case.


Diffusion of a Brownian Particle
================================

Now that we have the pieces in place, it is time to see what we can calculate.  To start with, multiply both sides of
equation :eq:`langevin-equation` by :math:`x`, then take the ensemble average:

.. math::
    m \langle x \ddot{x} \rangle = -\gamma \langle x \dot{x} \rangle + \langle x R \rangle
    :label: brownian-diffusion-step-1

Because :math:`R` is independent of :math:`x`, the last term vanishes:
:math:`\langle x R \rangle = \langle x \rangle \langle R \rangle = 0`.  To unify the other two terms, we can use the
identity

.. math::
    \frac{d}{dt} \langle x \dot{x} \rangle = \langle x \ddot{x} \rangle + \langle \dot{x}^2 \rangle
    :label: brownian-diffusion-step-2

(This identity makes use of the fact that the operations of taking a derivative and taking an ensemble average commute
with each other.  After all, an ensemble average is just a weighted sum of terms that can each be differentiated
independently.)  Substituting this into equation :eq:`brownian-diffusion-step-1` gives

.. math::
    m \left( \frac{d}{dt} \langle x \dot{x} \rangle - \langle \dot{x}^2 \rangle \right) = -\gamma \langle x \dot{x} \rangle
    :label: brownian-diffusion-step-3

Next we can use the equipartition theorem.  A single particle in one dimension has one degree of freedom so, in
equilibrium, its average kinetic energy is :math:`m \langle \dot{x}^2 \rangle/2 = kT/2`.  Therefore

.. math::
    m \frac{d}{dt} \langle x \dot{x} \rangle = kT -\gamma \langle x \dot{x} \rangle
    :label: brownian-diffusion-step-4

Now make a change of variables.  Define

.. math::
    z = \frac{d}{dt} \langle x^2 \rangle = 2 \langle x \dot{x} \rangle
    :label: brownian-diffusion-step-5

so the equation becomes

.. math::
    \frac{dz}{dt} = \frac{2kT}{m} -\frac{\gamma}{m} z
    :label: brownian-diffusion-step-6

This is a standard differential equation whose solution is given by

.. math::
    z = Ce^{-\frac{\gamma}{m}t} + \frac{2kT}{\gamma}
    :label: brownian-diffusion-step-7

You can easily verify that by substituting it back into equation :eq:`brownian-diffusion-step-6`.  :math:`C` is an
arbitrary constant.

We are almost done!  The first term in equation :eq:`brownian-diffusion-step-7` decays rapidly with time.  Taking the
limit of large :math:`t`, we get

.. math::
    z = \frac{d}{dt} \langle x^2 \rangle = \frac{2kT}{\gamma}
    :label: brownian-diffusion-step-8

or integrating with respect to time and defining :math:`x(0)=0`,

.. math::
    \langle x^2 \rangle = \frac{2kT}{\gamma}t
    :label: brownian-diffusion-step-9

So as time passes, the mean squared distance traveled by the particle increases at a constant rate.  This was one of the
main conclusions of Einstein's 1905 paper on Brownian motion, although he derived it by a somewhat different method.
The approach used here was published a few years later, in 1908, by Paul Langevin.

This result is not really very surprising.  In fact, it is exactly what we probably would have predicted if we had
thought about it in advance.  The particle moves irregularly as its velocity is continuously damped away by friction and
replaced by the random force.  The motion can be thought of as a series of independent displacements taken at random,
one after another.  By the central limit theorem, they should therefore add up to a normal distribution whose standard
deviation grows as :math:`\sqrt{t}`.  This kind of motion is called *diffusion*.  It also is sometimes referred to as a
*random walk*, because of the way it is built up from many independent random displacements.

The way it scales with temperature is similarly unsurprising.  If we had been forced to predict in advance, we probably
would have guessed the average displacement would be proportional to the average velocity, and by the equipartition
theorem that scales as :math:`\sqrt{T}`.  We also would probably have guessed that a larger friction coefficient would
lead to a smaller average displacement.

On the other hand, there is one strange thing about equation :eq:`brownian-diffusion-step-9`.  It appears to be
completely independent of the random force.  In fact, :math:`R` dropped out of the derivation after the very first step
and never appeared again.  But the random force is what causes the particle to diffuse!  Surely the average displacement
ought to depend on the magnitude of :math:`R`?

In fact, this result does depend on :math:`R`, but it does it indirectly.  By using the equipartition theorem, we
assumed the system was in equilibrium at temperature :math:`T`.  That equilibrium is brought about by the interaction
between the friction force and the random force, and :math:`R` depends on :math:`T`.  To derive equation
:eq:`brownian-diffusion-step-9`, it was sufficient to assume equilibrium had been achieved without knowing precisely how
it came about.  So now we will turn to that question: how do the forces interact to produce equilibrium?


The Fluctuation-Dissipation Theorem
===================================

Equation :eq:`langevin-equation` can be viewed as a first order differential equation for the velocity :math:`\dot{x}`.
Its solution is given by

.. math::
    \dot{x}(t) = \dot{x}(0) \cdot e^{-\frac{\gamma}{m}t} + \frac{1}{m} \int_0^t e^{-\frac{\gamma}{m}(t-t')} R(t') dt'
    :label: fluctuation-dissipation-step-1

The first term is identical to equation :eq:`decaying-velocity`.  It represents the initial velocity decaying
exponentially to zero.  But this time, we also have a second term representing the effect of the random force.  It can
be viewed as a series of infinitesimal kicks, each of which then decays with time.  The integral sums over all those
kicks, weighting each one by an exponential factor based on the time :math:`t-t'` that has passed since it occurred.

We are interested in the behavior at large values of :math:`t`, once the system has had plenty of time to come to
equilibrium.  In this limit equation :eq:`fluctuation-dissipation-step-1` becomes simpler:

.. math::
    lim_{t \to \infty} \dot{x}(t) = \frac{1}{m} \int_0^{\infty} e^{-\frac{\gamma}{m}(t-t')} R(t') dt'
    :label: fluctuation-dissipation-step-2

Notice that :math:`t` still appears in the exponential.  You might be tempted to replace it with :math:`\infty`, but
that would be incorrect.  As :math:`t` increases, the upper limit of the domain of integration increases as well.  The
exponent only depends on the difference :math:`t-t'`, and no matter how large :math:`t` gets, there is always a portion
of the domain of integration for which the exponent is small.

We want to compute the average kinetic energy in equilibrium, so square each side and take an ensemble average.

.. math::
    lim_{t \to \infty} \langle \dot{x}^2(t) \rangle = \frac{1}{m^2} \int_0^{\infty} \int_0^{\infty} e^{-\frac{\gamma}{m}(2t-t'-t'')} \langle R(t')R(t'') \rangle dt' dt''
    :label: fluctuation-dissipation-step-3

In section :ref:`brownian-motion` we assumed that :math:`\langle R(t')R(t'') \rangle` was independent of :math:`t'` and
depended only on the difference :math:`t''-t'`.  We can therefore replace it by :math:`\langle R(0)R(t''-t') \rangle`.
Also make a change of variables by defining :math:`r=t-t''` and :math:`s=t''-t'`.  With these substitutions, the
equation becomes

.. math::
    \begin{array}{rcl}
    lim_{t \to \infty} \langle \dot{x}^2(t) \rangle &=& \frac{1}{m^2} \int_{r=0}^{\infty} \int_{s=-\infty}^{\infty} e^{-\frac{\gamma}{m}(2r+s)} \langle R(0)R(s) \rangle dr ds \\
    &=& \frac{1}{m^2} \left( \int_0^{\infty} e^{-\frac{\gamma}{m}2r} dr \right) \left( \int_{-\infty}^{\infty} e^{-\frac{\gamma}{m}s} \langle R(0)R(s) \rangle ds \right) \\
    &=& \frac{1}{2 \gamma m} \int_{-\infty}^{\infty} e^{-\frac{\gamma}{m}s} \langle R(0)R(s) \rangle ds
    \end{array}
    :label: fluctuation-dissipation-step-4

Now we can invoke the equipartition theorem once again to set :math:`\langle \dot{x}^2(t) \rangle = kT/m`.  Therefore,

.. math::
    2 \gamma kT = \int_{-\infty}^{\infty} e^{-\frac{\gamma}{m}s} \langle R(0)R(s) \rangle ds
    :label: fluctuation-dissipation-step-5

In section :ref:`brownian-motion` we assumed the random force was uncorrelated with itself except over some "very short"
time :math:`\tau`.  Let's make that assumption more precise.  From equation :eq:`fluctuation-dissipation-step-1`, we
see that :math:`m/\gamma` sets the timescale on which friction operates.  After a time :math:`m/\gamma` has passed, the
initial velocity has decayed by a factor of :math:`e`.  We will assume that :math:`\tau \ll m/\gamma`.  The timescale
over which the random force is correlated with itself is very small compared to the timescale over which friction
operates.

This assumption means that whenever the integrand is non-zero, the exponent is negligible in magnitude.  This leads to a
further simplification:

.. math::
    2 \gamma kT = \int_{-\infty}^{\infty} \langle R(0)R(s) \rangle ds
    :label: fluctuation-dissipation-theorem

This very important result is called the *fluctuation-dissipation theorem*.  It gives the relationship between
:math:`T`, :math:`\gamma`, and :math:`R`.  Any system in contact with a heat bath will experience both friction and
fluctuations, and the magnitudes of the two effects are directly linked to each other.  You cannot get one without the
other.

The right side of equation :eq:`fluctuation-dissipation-theorem` is the integral of the autocorrelation function of the
random force.  It depends both on the magnitude of :math:`R` and on the time :math:`\tau` over which it remains
correlated.  The stronger the force is, the larger its effect on the particle.  And the longer the time interval over
which the particle accelerates in a single direction before the force changes, the faster it will get moving.
