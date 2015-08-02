.. _thermodynamics:

Thermodynamics
##############

Statistical mechanics grew out of an earlier field called thermodynamics, which was concerned with the thermal
properties of liquids and gasses.  It grew up around it, and then subsumed it.  What we now call "classical
thermodynamics" was developed over a period of several hundred years, but much of the most important work was done in
just a few decades from the 1820s through the 1850s.  It is not at all a coincidence, of course, that this burst of
activity coincided with the industrial revolution and the development of the locomotive.  Classical thermodynamics was
largely developed by people who wanted to learn how to make better steam engines.

Statistical mechanics has come a long way from these humble beginnings, but thermodynamics is still an important field
in its own right.  In this chapter, I will discuss some of the most important results of classical thermodynamics as
seen from a modern statistical viewpoint.


Thermodynamic Processes
=======================

In everything that has come so far, we have considered only systems that were in equilibrium.  We will now take a first
step toward removing this restriction.

Consider some physical system, and assume it is initially in equilibrium.  We now change the system in some way. There
are many types of changes we might make.  Here are some examples.

* We could directly add energy to the system, for example by shaking it or by placing it over a fire.

* We could bring it into contact with a new heat bath.  This might be done by moving it, or by opening a door that
  previously insulated it and prevented heat from flowing between it and the heat bath.

* We could change the volume of the system.  For example, it might be contained in a chamber, one wall of which is
  attached to a piston allowing it to be moved in or out.

* We could change the potential energy function for the system.  For example, we could apply an electric or magnetic
  field.  This will change the energy of each microstate.

Once we make any of these changes, the system will no longer be in equilibrium.  If we let it sit long enough, however,
it will eventually come back into equilibrium.  How long that takes will depend entirely on the system.  It could
easily be anything from microseconds to millions of years.  Assume we do that, so we once again are dealing with a
system in equilibrium.  This whole process of changing the system and allowing it to equilibrate is known as a
*thermodynamic process*.  We can now compare the two different states of the system, one before the process was
performed and one after.

Notice that we have fundamentally changed our definition of what can constitute a physical system.  Up to now we have
dealt with two types of systems:

1. An isolated system whose macroscopic properties, like energy and volume, are fixed and unchanging.

2. A system in contact with a heat bath.  The properties of the system are determined by the properties of the heat
   bath.  They are free to change, but they do so at random and mostly only within a narrow range.  Also, if we view
   the system of interest plus the heat bath as a single composite system, that composite system is still isolated.

We now have a third option: a system whose properties we can directly control.  They change when we choose to change
them in exactly the way we choose.  We are no longer in any way dealing with an isolated system.  We are explicitly
making an external change, reaching in from outside to alter the system.  On the other hand, we only do that during a
restricted time period.  Before we make the change, the system (possibly including a heat bath) is isolated.  After we
are done making the change it is again isolated.  But while we make the change, it is not isolated.


The Laws of Thermodynamics
==========================

Classical thermodynamics is based on four laws that are very sensibly numbered starting at zero.  When viewed from a
modern perspective, three of them are trivial.  The remaining one is extremely profound, and even today is often
misunderstood.

.. admonition:: The Zeroth Law of Thermodynamics

    If two bodies are each in thermal equilibrium with a third body, then they are also in thermal equilibrium with
    each other.

This law was needed to justify that one can define temperature in terms of values measured on a thermometer.  Remember
that when thermodynamics was first being developed, no one was certain exactly what "temperature" really was.  It was
strictly an empirical measurement.  This law asserts that if you let a thermometer come to equilibrium with two
different bodies, and they each produce the same measurement, then bringing those bodies together will produce no net
flow of heat.

Once we associate temperature with the average kinetic energy per degree of freedom, this law becomes trivial.  It is
merely the statement that if two numbers each equal a third number, then they also equal each other.

.. admonition:: The First Law of Thermodynamics

    The change in a system's energy during a thermodynamic process equals the heat added to the system, minus the work
    it performs on its environment.  In differential form, this is written
    
    .. math::
        dE=dQ-dW
        :label: first-law

    where :math:`Q` represents heat and :math:`W` represents work.

This is just a statement of conservation of energy.  But once again, remember that the founders of classical
thermodynamics did not know exactly what "heat" was.  The fact that it was a form of energy, and that it participated
in the conservation of energy, had to be discovered through experiment.

Also notice how the form in which it is stated reflects the sorts of problems they were trying to study: mechanical
engines that one adds heat to and that do work.  In many cases, it is hard to cleanly divide all energy conversions
into "heat" and "work", for example in processes that involve chemical reactions or in which matter is transferred
between the system and a heat bath.  But of course, energy conservation is a completely general law and applies to all
situations equally well.

The next law can be stated in several forms which appear different, but are actually equivalent.  Here are two of the
most common versions.

.. admonition:: The Second Law of Thermodynamics
    
    In any thermodynamic process, the total entropy either increases or remains constant, but never decreases.
    
    *or*
    
    Heat will never spontaneously flow from a colder body to a warmer one.

This law reflects a deep truth about the nature of the universe we live in.  It deserves a whole section of its own, so
before I get to that let me first finish off the list of laws.

.. admonition:: The Third Law of Thermodynamics

    As the temperature of any system approaches zero, its entropy approaches a minimum value.

This is another law that was needed to allow empirical definitions of temperature and entropy.  From a statistical
viewpoint, it is a statement of the fact that for nearly all physical systems, the density of states increases with
energy.


.. _the-second-law-of-thermodynamics:

The Second Law of Thermodynamics
================================

The second law is not a trivial consequence of statistics or mechanics, but at first glance it is easy to *think* it
is.  The entropy of a system is simply the logarithm of its density of states.  For an isolated system, that is a
measure of how probable each macrostate is.  The second law could therefore be summarized as, "Systems tend to move from
less probable states to more probable ones."  That sounds obvious.  If a system is initially in a less probable state,
we should hardly be surprised to later find it has moved to a more probable one.  If it went the other way and moved to
a less probable state, *that* would be surprising.

Suppose you have a box filled with gas molecules.  Now you remove the cover, so the molecules are free to leave the
box.  Clearly it is far more likely for the molecules to spread out through the room than to all remain inside the box.
There are far more possible arrangements of them when they are spread out through the room.  That is a higher entropy
state.  Once they have diffused out into the room, it is incredibly unlikely you will ever find that, simply by chance,
they are all inside the box at the same time again.  That is what the second law tells us.  Simple, right?

But there is a problem with this logic.  So far as we know, the laws of physics are symmetric with respect to time.  (Or
more accurately they obey CPT invariance, but that distinction is irrelevant for this discussion.)  If you reverse the
velocity of every particle, the entire system will exactly retrace its trajectory in reverse.  There is nothing in the
laws of physics that distinguishes between "forward" and "backward" in time.  Those are just arbitrary labels we assign
to two opposite directions.  If we reversed the labels, nothing about the laws of physics would change.  (For CPT
invariance, you also need to reverse the labels "left" and "right", as well as the labels "positive" and "negative"
charge.)

So we can repeat the same argument in reverse.  Consider a room containing gas molecules and an open box.  Now close the
box.  Assume that after you close it, all the molecules are inside the box.  At any earlier point in time when the box
was still open, it was incredibly unlikely that all the molecules just happened to be inside the box.  So this "proves"
that entropy tends to decrease.

Stated this way, the argument sounds like nonsense.  How can we assume that all the gas just happened to be inside the
box at the moment we closed it?  But in that case, why is it any more reasonable to assume the gas was initially
inside the box in the original version of the argument?  Just what is going on here?

Boltzmann himself spent years trying to prove the second law, and several times thought he had succeeded.  The most
famous of these attempts is known as the "H-theorem", published in 1872.  It appeared to be a completely rigorous proof
of the second law for a gas of classical particles.  Of course it contained an assumption that broke time symmetry, but
that assumption came into it in such a subtle way that for a few years neither Boltzmann nor any of his contemporaries
noticed it.  Then in 1876, Josef Loschmidt published his "reversibility objection" to the H-theorem.  He reasoned as
follows.

Start with a system in a low entropy (non-equilibrium) state. Given enough time, it will eventually move to a higher
entropy, equilibrium state. Now reverse the velocity of every particle. Since the equations of motion are time
symmetric, the system will retrace its trajectory and return to the original, low entropy state (except with velocities
reversed). Clearly the second law cannot be a universal law that applies in all cases, because we have just presented a
counter-example: a case where the entropy spontaneously decreases.

In response to this objection, Boltzmann slightly modified his position, arguing the second law was still true in a
probabilistic sense.  He acknowledged that one could carefully design states whose entropy would decrease.  But any
state that was not specifically designed in this way would almost certainly be one whose entropy increased rather than
decreasing.

Unfortunately, this claim is simply wrong.  The original low entropy state, the high entropy state it evolves into, and
the time reversed version of that high entropy state (which will spontaneously return to a lower entropy one) are all
equally probable.  There is no basis for accepting some while ignoring others.  For every trajectory whose entropy
increases, there is a reversed trajectory whose entropy decreases.  Both directions are equally probable.

Later in his career, Boltzmann finally came to a clearer understanding of the situation.  He recognized that the second
law *cannot* be proven.  No amount of statistics or probability can turn a symmetric theory into a non-symmetric one.
The second law of thermodynamics is not really a "law" at all.  It is a *definition*.  When we speak of "forward in
time," we really mean "the direction of increasing entropy."  All the phenomena that lead us to view time as asymmetric
follow directly from the change in entropy: that it is easy to break a window but hard to fix it; that friction makes
things slow down instead of speeding up; even that you can remember the past but not the future.  If the arrow of time
were reversed so that entropy increased in the opposite direction, you would not notice any difference at all.  You
would simply perceive the opposite direction as being "forward in time."

Boltzmann was unable to explain *why* entropy is changing in the first place.  If the universe were in equilibrium,
entropy should be constant and unchanging in all directions.  The best answer he could suggest was an anthropic
argument.  He observed that even in equilibrium, highly improbable states can still happen.  In fact, if you wait long
enough, *every* state will eventually be visited.  The entire Earth could be a random fluctuation that occurred just by
chance.  A fluctuation of that sort is incredibly improbable; most of the time, the atoms making up the Earth should be
arranged in a generally uniform, featureless way.  But in that situation, life could not exist.  Given that we *do*
exist, we should not be surprised to find the universe in one of the rare states that can support life.

This was a very clever idea, and in many ways a very modern one.  It was, however, wrong.  It leads to some very
specific predictions, and those predictions do not match the universe we actually see around us.

Today we have a better explanation: the change in entropy is an effect of the Big Bang.  We know that roughly 13.8
billion years ago, the universe was in a state of incredibly low entropy with all its matter and energy concentrated
in a tiny region of space.  Entropy has been steadily increasing ever since, and will continue increasing far into the
future.  That is why we find ourselves in a region of spacetime where there is an entropy gradient.  For practical
purposes, the phrase "forward in time" really means, "away from the Big Bang."

We still do not know *why* the Big Bang happened.  There are various ideas about that, but we do not yet have enough
evidence to say which one is correct.  There may be other regions of spacetime where entropy is flat and unchanging.
If so, those regions cannot support life, so it is not surprising we are not in one of them.  We do not know whether
the Big Bang marks the boundary of the universe, or whether there is more universe on the other side of it.  If the
latter, then entropy in that region presumably increases in the opposite direction.  Anyone living there would perceive
time as moving in the opposite direction to how we perceive it.  Perhaps there are many different Big Bangs and many
different universes surrounding them, each with its own arrow of time.  Based on our current evidence, we just cannot
say.


.. _heat-and-entropy:

Heat and Entropy
================

Consider a thermodynamic process in which an infinitesimal amount of heat :math:`dQ` is added to a system, while keeping
its volume and other macroscopic variables fixed (so that it does not do any mechanical work).  The first law of
thermodynamics then simplifies to :math:`dE=dQ`.  We can use the chain rule to rewrite this as

.. math::
    dQ &= dE = \left( \frac{\partial \mathrm{log}(\Omega)}{\partial E} \right)^{-1} d(\mathrm{log}(\Omega)) \\
    &= T dS
    :label: dQ=TdS

This shows a direct connection between heat and entropy.  If you add heat to a system, you raise its entropy.  If you
remove heat, you lower its entropy.  This is just our assumption that :math:`\Omega` increases with energy, coming back
in yet another form.

Suppose an amount of heat :math:`dQ` flows from subsystem A to subsystem B.  The entropy of A decreases and the entropy
of B increases.  The total change in entropy of the whole system is the sum of the two:

.. math::
    dS = dS_B+dS_A = \frac{dQ}{T_B} - \frac{dQ}{T_A}
    :label: change-in-entropy-from-heat

If :math:`T_A=T_B`, then :math:`dS` is zero and the total entropy of the system remains constant.  But if the
temperatures were equal, no heat would have flowed in the first place.  We saw this in section
:ref:`thermal-equilibrium`: if two systems have the same temperature, they are in thermal equilibrium and no heat flows
between them.

If :math:`T_A < T_B`, then :math:`dS` is negative and the total entropy decreases.  But this case is forbidden by the
second law of thermodynamics.  Heat will never spontaneously flow from a colder body to a warmer one.  The total change
in entropy cannot be negative.  (You see now how these two versions of the second law are equivalent to each
other.)

So the only possibility is that :math:`T_A > T_B`.  Heat is flowing from a warmer body to a colder one, and the overall
entropy of the system increases.  This leads us to the following very important conclusion: *whenever heat flows between
two bodies, the total entropy of the system increases*.  As we will see shortly, this has important consequences for
anyone trying to build a steam engine.


Heat Capacity
=============

If you add heat to a system, you increase its energy and therefore its temperature as well.  The proportionality
constant is called the *heat capacity*:

.. math::
    C \equiv \frac{dQ}{dT}
    :label: heat-capacity

If the heat capacity is large, that means you can add a lot of heat to the system while having only a small effect on
the temperature.  Heat capacity is an extensive property; if you double the size of the system, you also double its heat
capacity.

As in the previous section, assume the volume is held fixed so the system does no mechanical work.  In that case, we
can use equation :eq:`dQ=TdS` to write the heat capacity at constant volume:

.. math::
    C_V &= \frac{(T dS)}{dT} \\
    &= T \left(\frac{\partial S}{\partial T}\right)_V
    :label: heat-capacity-constant-V

The subscript V refers to the fact that we are keeping the volume fixed.  The expression
:math:`\left(\frac{\partial S}{\partial T}\right)_V` is an example of a notation that is common in thermodynamics, and
usually used without any explanation of what it really means.  In this case, :math:`S=k \mathrm{log}(\Omega(E,V))`.
That cannot in any way be considered a function of :math:`T`!  In fact, the temperature is defined by a *derivative* of
:math:`S`.  It describes the distribution of microstates with energy.  It makes no sense to speak of the "temperature"
of a single microstate, or the density of states with a given temperature!  So what do we mean by writing a derivative
of :math:`S` with respect to :math:`T`?

As the system interacts with the heat bath, its energy (and hence entropy) continuously fluctuate.  So :math:`S` is not
even well defined in this situation.  On the other hand, we can still compute the *average* entropy
:math:`\langle S \rangle`.  That *is* a well defined function of temperature, so we can reasonably compute its derivative
with respect to :math:`T`.  That is what the partial derivative in equation :eq:`heat-capacity-constant-V` really means:
the derivative of :math:`\langle S \rangle`, not of :math:`S` itself.  Of course, the average will vary depending on
what ensemble we use to calculate it.  We therefore add a subscript to specify the ensemble: in this case, that
:math:`V` is held fixed.

Of course, entropy was first known as an experimental quantity before it was later explained as a statistical quantity.
If you think about it in those terms, there is nothing confusing about any of this.  Just measure the entropy of a
system, and see how it varies with temperature.  You find that the result differs depending on whether you fix the
volume or the pressure during your experiment, so of course you add a subscript to indicate which one you measured.
Simple, right?  Just remember that your experiment is actually measuring the *average* entropy over a range of
macrostates, not the entropy of any one specific macrostate.

If you choose to fix pressure instead of volume, equation :eq:`dQ=TdS` changes to

.. math::
    dE = T dS = dQ-P dV

and the heat capacity becomes

.. math::
    C_P &= \frac{(T dS+P dV)}{dT} \\
    &= T \left(\frac{\partial S}{\partial T}\right)_P + P \left(\frac{\partial V}{\partial T}\right)_P
    :label: heat-capacity-constant-P

It can be shown that for nearly all realistic systems, :math:`C_P > C_V`.  This is easy to understand.  If you let the
system expand as you add heat, it performs work on its environment.  That reduces the energy of the system.  Energy used
to perform work is energy that doesn't go into raising the temperature, so :math:`T` increases more slowly.


The Ideal Gas Law
=================

An *ideal gas* is defined as a gas of free particles that do not interact with each other in any way.  It makes a very
useful model for studying how gasses behave during thermodynamic processes.

The density of states of an ideal gas takes a particularly simple form.  Each particle is equally likely to be anywhere
in the allowed volume, so for any single particle considered on its own, :math:`\Omega \propto V`.  Because the
particles do not interact with each other, the density of states for the whole gas is just the product of the ones for
the individual particles: :math:`\Omega \propto V^N`.  The definition of pressure therefore becomes

.. math::
    P &\equiv kT \frac{\partial \mathrm{log}(\Omega)}{\partial V} \\
    &= NkT \frac{\partial \mathrm{log}(V)}{\partial V} \\
    &= \frac{NkT}{V}

Rearranging this gives the *ideal gas law*, also known as the *ideal gas equation of state*:

.. math::
    PV = NkT
    :label: ideal-gas-law

A real gas is not an ideal gas, of course.  The particles do interact with each other.  Still, this turns out to be a
surprisingly good approximation for dilute gasses of non-polar, non-reactive molecules.  Air, for example.  Furthermore,
even when it is not accurate enough to make quantitative predictions, it still gives a good qualitative description of
how real gasses behave.  So let us take a minute to examine it and see what it can tell us.

Suppose you increase the temperature of a gas, such as by lighting a fire under it.  The ideal gas law immediately tells
us that the pressure, the volume, or both must increase as well.  If you hold the volume fixed, the pressure will
increase in direct proportion to the temperature.  If instead you hold the pressure fixed while allowing the volume to
change, then the gas will expand.

As it expands it does work on its environment: :math:`W=P \Delta V`, where :math:`\Delta V` is the change in volume.
That means the energy of the gas must decrease by the same amount to conserve energy, and that in turn means its
temperature will decrease.  This leads us to another important principle: *when a gas expands, its temperature tends to
decrease*.

Of course, it works the other way as well.  If you compress the gas by performing work on it, you increase its energy
and thus its temperature.

So you see, this simple gas of noninteracting particles actually has an amazing ability: it can convert thermal energy
into mechanical work, and vice versa!  That certainly sounds like it ought to be a useful ability.  Surely *someone*
must have come up with something to do with it!


Heat Engines
============

A device that transforms thermal energy into mechanical work is called a *heat engine*.  From what we saw in the last
section, it looks like a gas could be very useful in building one.  For example, you might have a chamber filled with
gas, and one wall of the chamber is a piston that can move in and out.  As the gas expands, the piston moves outward and
does work.

But what then?  Once it has gone all the way out, it cannot move any further.  Before you can extract any more work, you
first need to compress the gas again.  And to do that, you need to perform work *on* the gas, thus giving back all the
useful work you just got out of it.  Not so useful after all!

But with a little cleverness we can get around this problem.  As the gas expands it does work :math:`P \Delta V` on its
environment, and as we compress it we have to do work :math:`P \Delta V` on the gas.  But what if the pressures in these
two expressions were different?  We want the pressure to be high while the gas expands and low while we compress it.  In
that case, we will get more work out of the gas in the expansion stage than we have to put into it in the compression
stage.

The ideal gas law tells us how we can do this: by changing the temperature!  We need the gas to be hot while it expands
and cold while it contracts.  That is easily achieved.  In addition to the gas (also known as the *working body*), we
need two different heat baths: one called the "hot bath" or "source" at temperature :math:`T_H`, and one called the
"cold bath" or "sink" at temperature :math:`T_C`.  Here is a specific example of a sequence of steps you might use.

1. Put the working body in contact with the hot bath and let it expand.  As it expands it does useful work.  Normally
   this would cause its temperature to drop, but because it is in contact with a heat bath, it steadily absorbs energy
   and its temperature remains at :math:`T_H`.

2. Now disconnect the working body from the heat bath so it is isolated.  Let it continue to expand.  It continues to do
   useful work, and since it is now isolated, its temperature does drop.  Let this continue until its temperature
   reaches :math:`T_C`.

3. Put it in contact with the cold bath and start compressing it.  This would normally cause its temperature to rise,
   but since it is in contact with the cold bath, it instead expels energy to the bath and remains at :math:`T_C`.

4. Disconnect the working body from the bath so it is once again isolated.  Continue doing work to compress it.  This
   will now cause its temperature to rise.  Continue until it reaches :math:`T_H`.

This is an example of a *thermodynamic cycle*: a sequence of thermodynamic processes that end with the system (other
than the heat baths) in exactly the same state it began in, so we can repeat the cycle over and over.  In particular,
this is known as the *Carnot cycle* after Sadi Carnot, who proposed it in 1824.  A heat engine that uses this cycles is
called a *Carnot heat engine*.

Let us analyze what happens during this cycle.  Let :math:`Q_H` be the heat absorbed from the hot bath, :math:`Q_C` the
heat expelled to the cold bath, and :math:`W` the net amount of work performed during the whole cycle (that is, the
work performed *by* the working body during steps 1 and 2, minus the work performed *on* the working body in steps 3 and
4).  Conservation of energy requires that :math:`W=Q_H-Q_C`.

As we saw in section :ref:`heat-and-entropy`, whenever heat flows into or out of a system, its entropy changes as well.
Therefore the entropy of the two heat baths must change over the course of the cycle.  The entropy of the hot bath
decreases and the entropy of the cold bath increases.  From equation :eq:`dQ=TdS`, :math:`Q_H=T_H \Delta S_H` and
:math:`Q_C=T_C \Delta S_C`.

The *efficiency* of a heat engine, represented by the symbol :math:`\eta`, is defined as the ratio of the work done by
it to the energy absorbed from the hot bath:

.. math::
    \eta &\equiv \frac{W}{Q_H} \\
    &= \frac{Q_H-Q_C}{Q_H} \\
    &= 1-\frac{Q_C}{Q_H} \\
    &= 1-\frac{T_C \Delta S_C}{T_H \Delta S_H}
    :label: define-efficiency

The second law of thermodynamics requires that the total entropy of the whole system must increase or stay constant over
the cycle.  The working body ends up in exactly the same state it began in, so its entropy does not change.  The engine
also does work on its environment, but we cannot assume anything about what happens there.  Perhaps all the energy is
being stored into a single degree of freedom with no entropy at all.  The two heat baths are all we have to work with,
so the second law requires that :math:`\Delta S_C \geq \Delta S_H`.  We therefore conclude

.. math::
    \eta \leq 1-\frac{T_C}{T_H}
    :label: carnot-theorem

Notice how little we assumed in deriving this: merely that the heat engine absorbed heat from one bath, expelled heat to
another, and did work.  I described the Carnot cycle as an illustration, but no details of the cycle were required for
the derivation.  Therefore, equation :eq:`carnot-theorem` applies equally well to heat engines that use different
cycles.  I assumed nothing about the nature of the working body.  It could be a gas, a liquid, a solid, or even
something exotic like a supercritical fluid.  I assumed nothing about how the working body performed work.  It could
involve moving a piston, applying an electric field, or shooting ping-pong balls at a target.

Absolutely any heat engine, no matter what it is made of or how it works, must obey equation :eq:`carnot-theorem`, a
fact known as *Carnot's theorem*.  The second law of thermodynamics requires that we *must* have a second heat bath:
we decrease the entropy of the hot bath, so we need to make up for that somewhere else.  Conservation of energy requires
that any heat expelled to the cold bath is not available for doing work.  Those two facts place an absolute limit on
how efficient any heat engine can ever be.

There is no lower limit, of course.  You can make a heat engine as inefficient as you want. You could connect the two
heat baths and allow energy to flow directly from one to the other without doing any work at all, thus achieving a
spectacular efficiency of zero.  The key to making an efficient engine is to minimize all transfers of heat *except* the
ones that are absolutely required for the operation of the engine.

Another interesting fact about heat engines is that you can run them backward, which turns them into *heat pumps*.  Just
perform the same steps in reverse order and changing the direction of movement (so that expanding becomes compressing,
for example).  In this case, heat flows *out* of the cold bath and *into* the hot bath.  Heat is flowing opposite to its
normal direction!  It does not do this spontaneously, of course.  Instead of the engine *producing* work, we now have to
do work on it.  You are probably already very familiar with this fact: refrigerators and air conditioners have an
unfortunate habit of needing to be connected to an external source of energy.


Free Energy
===========

Consider an even simpler case: just a working body and a single heat bath.  Assume the working body has energy :math:`E`
and entropy :math:`S`, and that the heat bath has temperature :math:`T`.  We now want to answer a simple question: what
is the maximum amount of work we can extract from the body?

Ideally, we would like the answer to be :math:`E`.  We want to extract *all* the energy as work.  But the second law
makes that impossible.  As the body's energy decreases, its entropy does too.  We need to make up for that by adding
heat (and entropy) to the heat bath.

The third law of thermodynamics says that as the body's energy (and hence temperature) goes to zero, its entropy
approaches some minimum value.  Call that :math:`S_0`.  So its entropy decreases by :math:`S-S_0`, and we need to add
heat :math:`T(S-S_0)` to the heat bath.  Therefore, the maximum about of work we can hope to extract from the body is

.. math::
    W_{max} = E-T(S-S_0)
    :label: free-energy

If we assume :math:`S_0` is zero, this simplifies further to :math:`W_{max}=E-TS`, which we recognize as the Helmholtz
free energy.

In general, of course, :math:`S_0` is not zero, but that is a result of the statistical definition of entropy.  Before
statistical mechanics was developed, the zero point of entropy was considered arbitrary.  In thermodynamics, only
*differences* in entropy are usually important, so it was common to fix the zero point by defining :math:`S_0` to be
zero.

This is the origin of the term "free energy".  It means energy that is "free" in the sense of "available" or "not locked
up in an unusable form".  It is the maximum amount of energy you can hope to extract as work.  Notice that its value
depends on the temperature of the heat bath.  The colder the heat bath you have access to, the more work you can extract
from the working body.
