.. _very-large-numbers:

Mathematical Interlude: Very Large Numbers
##########################################

Problems in statistical mechanics tend to involve large numbers.  Very *very* large numbers.  For example, we often
need to average over all the atoms or molecules in a system.  For any macroscopic system, that will be on the order of
Avogadro's number: 10\ :sup:`23`, plus or minus a few orders of magnitude.  In other cases we average over microstates,
the number of which usually grows *exponentially* in the number of atoms.  These are really astronomically large
numbers.

This has an interesting result.  In many cases, we can simply treat averages as exact numbers.  Any variation about the
average value is so small, we can completely ignore it.  This is a great simplification, and is one of the reasons
statistical mechanics is so successful.

It also is the reason that, despite its name, statistical mechanics involves very little real statistics.  A large part
of the field of statistics deals with the variations about averages: computing the probability of a distribution
producing values in a certain range, determining whether a measured value might plausibly have come from a certain
distribution, etc.  But in statistical mechanics, we can usually ignore these questions.  The chance of measuring any
value *except* the average one is negligible.

The main goal of this chapter is to demonstrate this fact.  We will do that first through a simple example, and then
through a very general theorem.


.. _the-binomial-distribution:

The Binomial Distribution
=========================

Do you ever worry that all the oxygen molecules in the air around you might spontaneously migrate to the other side of
the room, leaving you unable to breathe?  It could happen.  Each molecule diffuses independently, so there is a small
but finite probability that just by chance, they will all end up in the same half of the room at the same time.

I hope I am not worrying you.  While this is theoretically possible, it is so absurdly improbable that you really can
ignore it.  We will first compute just how improbable it is, and then study the statistics of this problem in more
detail.

Let :math:`N` be the number of oxygen molecules in the room.  We will describe the position of each one simply by
whether it is in the left or right half of the room.  That gives :math:`2^N` possible arrangements of molecules, every
one of which is equally probable.  Of all those arrangements, only one has all the oxygen in the opposite half of the
room from you, so the probability is :math:`1/2^N`.

Depending on the size of the room you are in, it probably has somewhere in the vicinity of 10\ :sup:`26` oxygen
molecules in it.  So the probability of all the oxygen being on the same side of the room at any given moment is

.. math::
    \frac{1}{2^{10^{26}}} \approx \frac{1}{10^{10000000000000000000000000}}

That is a very, very large denominator.  For comparison here are some much smaller numbers:

* The age of the universe is on the order of 10\ :sup:`17` seconds.

* There are somewhere around 10\ :sup:`80` atoms in the visible universe.

In short, you really do not need to worry about this happening.  You would be much better off worrying about more likely
events.  For example, that you will be struck by lightning and then, as you try to pick yourself back up, hit by
a meteor falling from space.  And then immediately be struck by lightning a second time just for good measure.  That is
the sort of thing that is far more likely to happen to you.

Perhaps you are still not reassured.  You may have realized that even if only 90% of the oxygen moved to the other side
of the room, that would still leave you in a rather awkward position.  We really want to work out the entire probability
distribution.  Let :math:`m` be the number of oxygen molecules in the left half of the room and :math:`N-m` the number
in the right half.  Assuming the energy of each molecule is independent of which side of the room it is on, and that the
oxygen molecules are far enough apart that we can ignore their interactions (both reasonable assumptions), the
probability is simply proportional to :math:`\Omega(m)`.  Let us consider how that varies with :math:`m`.

* There is precisely one arrangement of molecules that has all of them on the left side of the room, so
  :math:`\Omega(0)=1`.

* There are :math:`N` possible ways to have exactly one molecule on the left side of the room (any of the :math:`N`
  molecules could be the one), so :math:`\Omega(1)=N`.

* To get two molecules on the left side of the room, we have :math:`N` choices for the first molecule and :math:`N-1`
  for the second molecule.  But now we have counted each state twice: for any pair of molecules, it does not matter which
  order we choose them in.  So :math:`\Omega(2)=N(N-1)/2`.

Continuing like this, we find the general form:

.. math::
    \Omega(m) = \frac{N!}{m!(N-m)!}
    :label: binomialomega

The probability is then

.. math::
    p(m) = \frac{1}{2^N} \frac{N!}{m!(N-m)!}
    :label: binomialprobability

This is a special case of the *binomial distribution*.  (In the general case, the probability for a particle to be on
the left side of the room could be different from its probability to be on the right side, but for this example we can
ignore that.)  It is shown in :autonumref:`Figure,binomial` for several values of :math:`N`.  Notice how, as :math:`N`
increases, the probability becomes steadily more concentrated around its midpoint.

.. figure:: images/binomial.*
    :align: center
    :scale: 80
    
    :autonumber:`Figure,binomial`. The binomial distribution for several values of :math:`N`.  To make them easier to
    compare, all the curves have been normalized to go from 0 to 1 along each axis.

The name comes from the fact that it has the same form as the terms in the *binomial series*:

.. math::
    (a+b)^N = \sum_{m=0}^N \frac{N!}{m!(N-m)!}a^Nb^{N-m}
    :label: binomialseries

If we let :math:`a=b=1/2`, this simplifies to

.. math::
    \left(\frac{1}{2}+\frac{1}{2}\right)^N = \sum_{m=0}^N \frac{N!}{m!(N-m)!} \frac{1}{2^N}

so that

.. math::
    \sum_{m=0}^N \frac{N!}{m!(N-m)!} = 2^N
    :label: binomialsum

Let us examine this probability distribution a bit further.  We can roughly characterize it by calculating its mean and
standard deviation.  The mean is easy: every particle has an equal chance to be on each side of the room, so
:math:`\langle m \rangle = N/2`.  Another way to think about this is that the distribution is symmetric: for any value
of :math:`m`, :math:`p(m)=p(N-m)`, from which it directly follows that the mean must be :math:`N/2`.

The standard deviation is a bit more complicated to derive.  As a first step, let us first calculate

.. math::
    \langle m(m-1) \rangle = \frac{1}{2^N} \sum_{m=0}^N m(m-1) \frac{N!}{m!(N-m)!}

Notice that the first two terms of the sum are both zero, so we can increase the lower bound to begin from 2.  This
allows us to then cancel out the factors of :math:`m(m-1)` that appear in both numerator and denominator:

.. math::
    \langle m(m-1) \rangle &= \frac{1}{2^N} \sum_{m=2}^N \frac{N!}{(m-2)!(N-m)!} \\
    &= \frac{N(N-1)}{2^N} \sum_{m=2}^N \frac{(N-2)!}{(m-2)!(N-m)!}

Now make two substitutions: define :math:`X=N-2` and :math:`y=m-2`.  This simplifies it to:

.. math::
    \langle m(m-1) \rangle = \frac{N(N-1)}{2^N} \sum_{y=0}^X \frac{X!}{y!(X-y)!}

We immediately recognize the sum as being the same one that appeared in equation :eq:`binomialsum`.  Replacing it by
:math:`2^X=2^{N-2}`,

.. math::
    \langle m(m-1) \rangle = \frac{N(N-1)2^{N-2}}{2^N} = \frac{N(N-1)}{4}

We now have all the pieces we need.  Recall that

.. math::
    Var(m) &= \langle m^2 \rangle - \langle m \rangle^2 \\
    &= \langle m(m-1) \rangle + \langle m \rangle- \langle m \rangle^2 \\
    &= \frac{N(N-1)}{4} + \frac{N}{2} - \frac{N^2}{4} \\
    &= \frac{N}{4}
    :label: binomialvariance

The standard deviation is then

.. math::
    \sigma \equiv \sqrt{Var(m)} = \frac{\sqrt{N}}{2}
    :label: binomialstddev

Let us take a moment to consider these results.  The average value is proportional to :math:`N`, while the standard
deviation is proportional to :math:`\sqrt{N}`.  In most cases, what we really care about is the ratio of the two.  You
want to know what *fraction* of the oxygen is likely to be on one side of the room, not the specific number of
molecules.  A number that would be huge in a broom closet would be negligible in an auditorium.  Taking the ratio gives

.. math::
    \frac{\sigma}{\langle m \rangle} = \frac{1}{\sqrt{N}}
    :label: binomialfractionaldeviation

For an average sized room with 10\ :sup:`26` oxygen molecules, that equals 10\ :sup:`-13`.  This is the
magnitude of the typical fluctuations, measured as a fraction of the total number of molecules.  There are very few
physical quantities that can actually be measured to a precision of 13 significant digits, and this is not one of them.
The random fluctuations in the number of molecules on each side of the room are simply too small to measure.


The Central Limit Theorem
=========================

Having worked through one example in detail, you might wonder how general our conclusions are.  Do other types of
statistical problems behave roughly the same way?  The answer is yes.  There is a very general theorem which guarantees
that a wide range of quantities will scale in essentially the same way.

Before presenting that theorem, I first need to introduce one other very important probability distribution, known as
the *Gaussian* or *normal* distribution:

.. math::
    p(x) = \frac{1}{\sigma \sqrt{2 \pi}} e^{\frac{-(x-\mu)^2}{2 \sigma^2}}
    :label: gaussianprobability

It is shown in :autonumref:`Figure,gaussian`.  It is not really as complicated as it looks.  The basic form is just :math:`e^{-x^2}`.
Replacing :math:`x` by :math:`x-\mu` shifts the mean of the distribution to :math:`\mu`, and then the exponent is scaled
to make the standard deviation equal :math:`\sigma`.  The factor in front is just a normalization, to ensure that

.. math::
    \int_{-\infty}^{\infty} p(x) dx = 1

.. figure:: images/gaussian.*
    :align: center
    :scale: 80
    
    :autonumber:`Figure,gaussian`. A normal distribution with mean of 0 and standard deviation of 1.

The name "normal distribution" gives a sense of just how important this distribution is in statistics.  It comes up
constantly.  We will see the reason for this in just a moment.

In the last section, we considered the number of oxygen molecules :math:`m` in the left half of the room.  You can think
of this quantity as a sum of random values:

.. math::
    m = \sum_{i=1}^{N} x_i

Each value :math:`x_i` is either 0 or 1 (depending on which half of the room the molecule is in) with equal probability.
Now we will generalize this to let the values be drawn from an arbitrary distribution.  That distribution could be
either discrete or continuous.  The only thing we will assume about it is that it has a known mean and standard
deviation.  There is a remarkable result called the *Central Limit Theorem*:

.. admonition:: The Central Limit Theorem

    Consider the sum
    
    .. math::
        S = \sum_{i=1}^N x_i
    
    where the values :math:`x_i` are independently drawn from a distribution with mean :math:`\mu_x` and standard
    deviation :math:`\sigma_x`.  In the limit :math:`N \to \infty`, the sum :math:`S` is distributed according to a
    normal distribution with mean :math:`\mu = N \mu_x` and standard deviation :math:`\sigma = \sqrt{N} \sigma_x`.

This theorem dates back to 1718, when Abraham de Moivre presented a proof of a special case of it in his book
*The Doctrine of Chances*.  This book was not, as you might guess, an academic treatise for mathematicians.  It was a
book for gamblers, discussing how to win at various games of chance.  Don't ever let anyone tell you that mathematics
is not useful!

This is the reason that normal distributions are so important.  No matter what distribution you start out with, once
you add enough values together the result will always be normally distributed.  How large :math:`N` needs to be varies,
of course, depending on the initial distribution, but it often does not need to be very large.  In many cases, summing
over 10 values is already enough to give quite a good approximation to a normal distribution.

Notice that our main conclusions from the previous section apply just as well to the general case as they did for our
specific example.  The standard deviation is proportional to :math:`\sqrt{N}`, the mean is proportional to :math:`N`,
and their ratio scales as :math:`1/\sqrt{N}`.  No matter what distribution the individual values come from, once you add
up a macroscopic number of them the fluctuations will be negligibly small.
