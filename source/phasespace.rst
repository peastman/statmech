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

Suppose the system has a probability :math:`P` of being inside this particular volume.  We can the define the
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
ellipse in phase space as shown in Figure ???.  When it is in the top half of the figure, its momentum is positive and
so its position is increasing (moving to the right).  When it is in the bottom half of the figure, its momentum is
negative so it moves to the left.  Likewise, in the right half of the figure the force on the particle is negative so
momentum is decreasing, and in the left half the force on the particle is positive so momentum is increasing.  The
system moves clockwise along the trajectory, tracing out the same ellipse again and again forever.

Every point in phase space traces out an ellipse.  Larger ellipses correspond to oscillators moving with larger
amplitude.  Two points on the same ellipse correspond to oscillators moving with the same amplitude but different phase.

Now consider an ensemble of identical harmonic oscillators moving with different amplitudes and phases.  Together, they
define a probability density in phase space.  Each one traces out an ellipse as it moves.  The frequency of a harmonic
oscillator is independent of its amplitude, so all of them take exactly the same amount of time to trace out one full
rotation.  Therefore the entire probability distribution simply rotates in phase space, returning to its starting point
after one full period of oscillation.
