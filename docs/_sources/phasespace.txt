Evolution of Phase Space Probabilities
######################################

Way back in Chapter :ref:`statistical-description-of-physical-systems`, I glossed over a subtle but very important
issue.  I swept it under the carpet and then ignored it.  The time has come to ease my guilty conscience by dealing with
it properly.

In section :ref:`microstates-and-macrostates`, I began by assuming that microstates were discrete.  I then said we could
still study classical mechanics, in which states are continuous rather than discrete, by dividing phase space up into
tiny volumes of width :math:`\delta x` for each position and :math:`\delta p` for each momentum.  Does this really work?
And is there anything special about this particular way of dividing it up?  There are infinitely many ways you might
divide the continuum of states into discrete bins.  Does it matter which one you choose?

In fact, when Boltzmann introduced the concept of microstates, he first tried defining them in terms of uniform
increments of energy, and showed this led to the wrong probability distribution.  He then defined them by uniform
increments of position and momentum, and showed that gave the correct distribution.  Why is one choice "right" and the
other "wrong"?

The goal of this chapter is to answer this question.  It will then lead us to a fuller understanding of what happens to
a system as it comes to equilibrium.


Phase Space Probability Density
===============================

Consider a tiny volume of phase space, defined by position :math:`i` being between :math:`x_i` and
:math:`x_i+\delta x_i`, and momentum :math:`i` being between :math:`p_i` and :math:`p_i+\delta p_i`.  If there are a
total of :math:`N` positions and momenta, then this is a :math:`2N` dimensional phase space.

Suppose the system has a probability :math:`P` of being inside this particular volume.  We can then define the
*probability density* as the ratio of probability to volume:

.. math::
   \rho = \frac{P}{\prod_i \delta x_i \delta p_i}
   :label: probability-density

As we have seen, the exact values of :math:`\delta x` and :math:`\delta p` are mostly irrelevant.  Changing them just
scales the density of states by a constant factor that disappears as soon as we do any calculations with it.  Therefore
we might as well take the limit that both of them go to zero.  The volume then becomes infinitesimally small, and the
probability density becomes a continuous function :math:`\rho(\mathbf{x}, \mathbf{p})`, where I have combined all
:math:`N` positions into the vector :math:`\mathbf{x}` and all :math:`N` momenta into the vector :math:`\mathbf{p}`.

When I speak of probabilities here, I mean them in the sense of ensemble averages.  Imagine preparing a huge number of
systems that are all macroscopically indistinguishable from each other.  The "probability" of a microstate means the
fraction of those systems that are in that particular microstate.  I am not assuming anything about what that
probability distribution is, though.  In particular, it need not correspond to equilibrium.  As all the systems evolve
with time, following the laws of classical mechanics, the probability density will also evolve.

As a simple example, consider a one dimensional harmonic oscillator.  As it moves back and forth, it traces out an
ellipse in phase space as shown in :autonumref:`Figure,oscillator trajectory`.  When it is in the top half of the
figure, its momentum is positive and so its position is increasing (moving to the right).  When it is in the bottom half
of the figure, its momentum is negative so it moves to the left.  Likewise, in the right half of the figure the force on
the particle is negative so momentum is decreasing, and in the left half the force on the particle is positive so
momentum is increasing.  The system moves clockwise along the trajectory, tracing out the same ellipse again and again
forever.

.. figure:: images/oscillator_trajectory.*
    :align: center
    :scale: 80
    
    :autonumber:`Figure,oscillator trajectory`. The trajectory in phase space of a harmonic oscillator.

Every point in phase space traces out an ellipse.  Larger ellipses correspond to oscillators moving with larger
amplitude.  Two points on the same ellipse correspond to oscillators moving with the same amplitude but different phase.

Now consider an ensemble of identical harmonic oscillators moving with different amplitudes and phases.  Together, they
define a probability density in phase space.  Each one traces out an ellipse as it moves.  The frequency of a harmonic
oscillator is independent of its amplitude, so all of them take exactly the same amount of time to trace out one full
rotation.  Therefore the entire probability distribution simply rotates in phase space, returning to its starting point
after one full period of oscillation.


Liouville's Theorem
===================

Now consider all of the probability density contained inside a tiny region of phase space.  That probability density
consists of a subset of the systems in the ensemble.  What happens to it as those systems change with time?  For
simplicity I will stick to a single particle in one dimension, so the phase space has only two dimensions, but the
generalization to more dimensions is trivial.  The region consists of all the systems with positions between :math:`x`
and :math:`x+\delta x` and momentum between :math:`p` and :math:`p+\delta p`, so its volume is
:math:`V=\delta x \delta p`.  We can then write

.. math::
   \begin{array}{rcl}
   \frac{dV}{dt} &=& \frac{d}{dt}(\delta x \delta p) \\
   &=& \delta x \frac{d(\delta p)}{dt} + \delta p \frac{d(\delta x)}{dt} \\
   &=& \delta x \left( \frac{d(p+\delta p)}{dt}-\frac{dp}{dt} \right) + \delta p \left( \frac{d(x+\delta x)}{dt}-\frac{dx}{dt} \right)
   \end{array}
   :label: liouville-step-1

Assume that :math:`\frac{dx}{dt}` and :math:`\frac{dp}{dt}` are linear in :math:`x` and :math:`p` respectively.  This is
an approximation for any finite sized region, but it becomes exact in the limit that :math:`\delta x` and
:math:`\delta p` go to zero.  That is,

.. math::
   \frac{d(x+\delta x)}{dt} = \frac{dx}{dt}+\delta x \frac{\partial}{\partial x} \left(\frac{dx}{dt}\right)
   :label: liouville-step-2

.. math::
   \frac{d(p+\delta p)}{dt} = \frac{dp}{dt}+\delta p \frac{\partial}{\partial p} \left(\frac{dp}{dt}\right)
   :label: liouville-step-3

Substituting these into equation :eq:`liouville-step-1` gives

.. math::
   \frac{dV}{dt} = \delta x \delta p \left[ \frac{\partial}{\partial p} \left(\frac{dp}{dt}\right) + \frac{\partial}{\partial x} \left(\frac{dx}{dt}\right) \right]
   :label: liouville-step-4

Now we will make use of the fact that :math:`x` and :math:`p` do not change in arbitrary ways.  Rather, they evolve in
one very specific way: by following the laws of classical mechanics!  Let :math:`H` be the Hamiltonian of the system.
Hamilton's equations of motion are then

.. math::
   \frac{dx}{dt} = \frac{\partial H}{\partial p}
   :label: liouville-step-5

.. math::
   \frac{dp}{dt} = -\frac{\partial H}{\partial x}
   :label: liouville-step-6

Substituting these into equation :eq:`liouville-step-4` gives

.. math::
   \begin{array}{rcl}
   \frac{dV}{dt} &=& \delta x \delta p \left[ -\frac{\partial}{\partial p} \left(\frac{\partial H}{\partial x}\right) + \frac{\partial}{\partial x} \left(\frac{\partial H}{\partial p}\right) \right] \\
   &=& \delta x \delta p \left[ -\frac{\partial^2 H}{\partial x \partial p} + \frac{\partial^2 H}{\partial x \partial p} \right] \\
   &=& 0
   \end{array}
   :label: liouvilles-theorem

This result is known as *Liouville's theorem*.  It says that as the systems contained in a tiny region of phase space
evolve according to classical mechanics, the volume they occupy remains constant.  And because the volume is constant,
the probability density remains constant as well.

It is hard to overstate the importance of Liouville's theorem.  It is, quite simply, the reason that statistical
mechanics works when applied to classical systems.  It is the reason we can divide up the continuous phase space into
tiny cells, call each cell a microstate, and then treat them as if they were discrete.

To understand why, imagine what would happen if it were *not* true.  Suppose the volume of each cell changed with time.
In section :ref:`the-density-of-states`, we identified the density of states :math:`\Omega` with volume in phase space.
Consider a region of volume :math:`V`.  That volume corresponds to a particular number of microstates.  Now suppose that
as the region evolved, its volume increased.  That would mean it then corresponded to a larger number of states than it
originally did.  New microstates would have been spontaneously created!  What does that even mean?

Now consider the total probability :math:`P` for the system to be inside that region.  The probability density in the
region is initially :math:`P/V`.  As it grows, the probability density decreases.  Meanwhile, other regions of phase
space are shrinking with time, so their probability density is growing.

What is so bad about that?  Well, remember that one of our fundamental assumptions back in Chapter
:ref:`statistical-description-of-physical-systems` was the postulate of equal *a priori* probabilities.  It says that
for a system in equilibrium, every microstate consistent with the current macrostate has an equal probability.  That is,
all regions of phase space consistent with the current macrostate have equal probability density.  If that is initially
true, then Liouville's theorem tells us it will remain true.  If that were not the case, if probability density
increased in some regions and decreased in others, then it would be impossible to make this assumption.  Even if it were
true at one time, it would not be true a moment later.

In deriving Liouville's theorem, we made use of two central elements: the particular way the "volume" of a microstate
is defined, and the equations of classical mechanics.  If either of those elements were different, the theorem need not
apply.  For example, if we defined microstates as uniform intervals of energy, rather than uniform intervals of position
and momentum, then it would not apply.  That is why, as Boltzmann discovered, statistical mechanics produces the wrong
results if you try to define microstates that way.

By the way, there is also a quantum mechanical version of Liouville's theorem.  That is why statistical mechanics can
also be applied to quantum systems, this time identifying volume in Hilbert space with the density of states.


The Approach to Equilibrium
===========================

I will now prove that it is impossible for any isolated system ever to come to equilibrium.

Consider a system that initially is not in equilibrium, so it has different probabilities of being in different
microstates.  At some later time, every initial microstate will have evolved into a unique later microstate.  (We know
they must be unique because mechanics is time reversible, as discussed in section
:ref:`the-second-law-of-thermodynamics`.  If you reverse all velocities, the system will retrace its path and return to
the original state.  One final state cannot return to two different original states, so every final state must have come
from a different original state.)  States that initially have a low probability will evolve into final states with the
same low probability.  States that initially have a high probability will evolve into final states with high
probabilities.  The states change, but the distribution of probabilities does not.  Nothing in this process can lead to
a situation where all states have the same probability.

You can also see this from Liouville's theorem.  As a region of phase space evolves, its probability density remains
constant.  Regions with low probability will move to new locations, but continue to have low probability density, and
likewise for regions with high probability density.

This argument sounds rigorous, but it directly conflicts with our experience that systems do, in fact, come to
equilibrium.  What is going on?  How do we resolve this paradox?  Why do systems come to equilibrium if we have just
proven that it is impossible?

There are two reasons.  The first is the simple fact that no system is ever completely isolated.  You may surround it
with insulation to shield it from light, heat, vibrations, magnetic fields, but no insulation is ever perfect.  You
could launch it out into interstellar space, but even there it would be constantly bombarded by starlight.  On short
time scales, it may be a reasonable approximation to view a system as isolated, but on sufficiently long time scales,
every system must be treated as interacting with an external heat bath.  And as we saw in Chapter
:ref:`friction-and-fluctuations`, a system in contact with a heat bath is not deterministic.  Its motion has a random
component, and it diffuses with time.

The second reason is more subtle, but often more important.  Equations :eq:`liouville-step-2` and :eq:`liouville-step-3`
are only exact in the limit that :math:`\delta x` and :math:`\delta p` go to zero.  That means Liouville's theorem is
only strictly true for an infinitesimal region of phase space.  For a very small but finite region, it may still give a
good approximation to the instantaneous change in volume, but over extended time periods the small errors can build up
into large deviations.

For a harmonic oscillator, we saw that the probability distribution just rotates in phase space, coming back to its
starting point after one full oscillation.  If two points start out close together in phase space, they will remain
close together forever.  In this respect, the harmonic oscillator is very unusual.  Most systems with more than a
handful of degrees of freedom are *chaotic*.  That means they are arbitrarily sensitive to initial conditions.  Consider
two points that are very close together in phase space.  At first they will move in almost the same direction, and
therefore remain close together, but with time they will gradually move apart.  The further apart they become, the less
correlated their motions will be, until eventually they are following completely independent trajectories.

Chaotic systems are not merely sensitive to initial conditions, but *arbitrarily* sensitive.  Any finite difference
between the starting states, no matter how small, will eventually lead to the trajectories diverging.  If you make the
initial distance smaller, they will take slightly longer to diverge but that is all.  They will still eventually
diverge.

Consider the states contained in a tiny but still finite region of phase space.  Initially those states will move in
almost (but not exactly) the same direction, and the volume they occupy will remain almost (but not exactly) the same.
But gradually they will spread out, and mix with other states that started in different parts of phase space.
Eventually they will become widely distributed.  If you then look at any finite region of phase space, you will
find it contains states that started in many different places.  Infinitesimal regions of phase space remain intact and
maintain the same probability density.  But for any finite values of :math:`\delta x` and :math:`\delta p`, the
"microstates" eventually become mixed up and their probability density converges to a uniform average value.  That is
what happens when a system comes to equilibrium.
