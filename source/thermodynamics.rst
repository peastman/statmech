Thermodynamics
##############

Statistical mechanics grew out of an earlier field called thermodynamics.  It grew up around it, and then subsumed it.
What we now call "classical thermodynamics" was developed over a period of several hundred years, but much of the most
important work was done in just a few decades from the 1820s through the 1850s.  It was concerned with the thermal
properties of liquids and gasses.  It was largely developed by people who wanted to learn how to make better steam
engines.

Statistical mechanics has come a long way from these humble beginnings, but thermodynamics is still an important field
in its own right.  In this chapter, I will discuss some of the most important results of classical thermodynamics as
seen from a modern statistical viewpoint.


Thermodynamic Processes
=======================

In everything that has come so far, we have considered only systems that were in equilibrium.  We will now take a first
step toward removing this restriction.

Consider some physical system, and assume it is initially in equilibrium.  We will now change the system in some way.
There are many types of changes we might make.  Here are some examples.

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

2. A system in contact with a heat bath.  The properties of the system are now determined by the properties of the heat
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

This law is needed to justify that one can define temperature in terms of values measured on a thermometer.  Remember
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

The next law can be stated in several forms which appear different, but are actually equivalent.

.. admonition:: The Second Law of Thermodynamics
    
    In any thermodynamic process, the total entropy either increases or remains constant, but never decreases.
    
    *or*
    
    Heat will never spontaneously flow from a colder body to a warmer one.
    
    *or*
    
    It is impossible to build a perfect heat engine.

(Do not worry about what a perfect heat engine is.  I will get to that later in this chapter.)

This law reflects a deep truth about the nature of the universe we live it.  It deserves a whole section of its own, so
before I get to that let me first finish off the list of laws.

.. admonition:: The Third Law of Thermodynamics

    As the temperature of any system approaches zero, its entropy approaches a minimum value.

This is another law that was needed to allow empirical definitions of temperature and entropy.  From a statistical
viewpoint, it is a statement of the fact that for nearly all physical systems, the density of states increases with
energy.


The Second Law of Thermodynamics
================================

The second law is not a trivial consequence of statistics or mechanics, but at first glance it is easy to *think* it
is.  The entropy of a system is simply the logarithm of its density of states, which is essentially a measure of how
probable each macrostate is.  The second law could therefore be summarized as, "Systems tend to move from less probable
states to more probable ones."  That sounds obvious.  If a system is initially in a less probable state, we should
hardly be surprised to later find it has moved to a more probable one.  If it went the other way and moved to a less
probable state, *that* would be surprising.

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
noticed it.  Then in 1866, Josef Loschmidt published his "reversibility objection" to the H-theorem.  He reasoned as
follows.