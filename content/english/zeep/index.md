---
title: Zeep
date: 2021-05-20
image : images/portfolio/GamePlay_WithRay.png
# image_webp : images/portfolio/generic.webp
# draft: true
hasMath: true # define this to be able to use math typesetting between $ $ or $$ $$
categories:
  - Games
AppleAppId: 1564623586  # banner to run this app
---

**Zeep** is a fast-paced, family-friendly multiplayer game that is easy to pick up and fun to play in a co-located group. You can pick it up for free at the Apple App Store.

The game has a mathematical foundation, based upon the simple idea that it is possible, from a set of symbols, to construct same-size subsets with one and only one symbol in common with any of the other subsets. These subsets are shown as cards for each player, and their goal is to find the matching symbol between the two top cards faster than any other player.

This guarantees that there is always one, and exactly one, symbol for each person to find. It is not obvious how to construct those sets so, unsurprisingly, it is a topic studied in mathematics, specifically in combinatorics.
The mechanism to construct the subsets is analogous to the construction of [Finite Projective Planes](https://en.wikipedia.org/wiki/Projective_plane) in [Projective Geometry](https://en.wikipedia.org/wiki/Projective_geometry).

The smallest finite projective plane is the [Fano Plane](https://en.wikipedia.org/wiki/Fano_plane), often represented by the picture below.

{{< figure src="/images/blog/fano-plane.png" title="Fano Plane" >}}

To see the analogy for Zeep, imagine that each point in the image above represents a symbol, and each line represents a card. In this case, there would be 7 cards and 7 different symbols, which is equivalent to the easiest difficulty in Zeep's Solo mode. As you can see, each line passes by exactly 3 points. This is analogous to each card having exactly those 3 symbols that would be on that card. Also, each line has exactly one point in common with every other line. Which is analogous to each card having exactly one symbol in common with every other card. Neat!

## Game Size

Now, the number of sets and how many total symbols are used are closely related. It turns out that proving that those combinations (a finite projective plane) exist or not for an arbitrary number is a really hard problem, still unsolved in mathematics today!

What we do know is that they exist for various small numbers, and in fact for any order $n = p^m$ where $p$ is any prime number and $m$ is any power. It is an [unproven conjecture](https://mathworld.wolfram.com/ProjectivePlane.html) that these are the *only* finite projective planes that do exist.

Anyway, for the finite projective planes that do exist, the total number of points *and* the total number of lines is

$$C(n)=n^2+n+1$$

where $n+1$ is the number of points per line, *and* the number of lines that meet at any one point.

For Zeep, $C(n)$ is the total number of subsets with exactly one common symbol, *and* the total number of cards *and* the total number of symbols. And $n+1$ is the number of symbols per card *and* the number of times a given symbol shows in the game (in different cards). Why are these two numbers $n+1$ and $C(n)$ everywhere? Because of the [duality principle](https://mathworld.wolfram.com/DualityPrinciple.html), but we digress.

The important stuff is summarized in this table, for all the game difficulties we support in Solo and Multiplayer game modes:

| symbols per card |  $n$ |      $C(n)$ | Notes            |
| -----------: | ---: | ----------: | ---------------- |
|            3 |    2 | 4+2+1  =  7 |
|            4 |    3 | 9+3+1  = 13 |
|            5 |    4 | 16+4+1 = 21 |
|            6 |    5 | 25+5+1 = 31 |
|            7 |    6 | <del>36+6+1 = 43</del> | (does not exist) |
|            8 |    7 | 49+7+1 = 57 |
|            9 |    8 | 64+8+1 = 73 |

## Scoring Details

As you play the game, you will see different players score amounts float briefly next to their avatar. That number is based on 3 things:
- how fast you found the match;
- if you also made the prior match, and the one before that;
- if that was the final, winning match.

The score is calculated as a function of *time* (between the prior match and this match):

$$S_n=m\times\min\left(\frac{\left(\frac{100}{\left(t_n-t_{n-1}\right)+0.13}\right)}{1.5},100\right), t_n \gt t_{n-1}$$

where $m \in \{1, 1.5, 2\}$ is the current streak multiplier, for 1, 2 or 3 or more sequential matches.
You also get a 150 bonus if you make the winning move, and thus run out of cards before anyone else.

{{< embed url="https://www.desmos.com/calculator/7le7xivcqt?embed" height=300 title="Scoring Function" >}}

## Maximum Score for Multiplayer Games

The max score depends on the size of the game. For a game of order $n$, we will have a total of $C(n)$ cards. One card goes into the discard pile, the remaining cards are evenly split among the players and any leftovers are discarded, so each player will receive $C_P(n)$ cards:
$$C_P(n) = \left\lfloor \frac {C(n)-1} 4 \right\rfloor, n \ge 4$$

The maximum score $S_{\max}(n)$ assuming an optimal winning performance is then

$$S_{\max}(n) = 200 \left(C_P(n)-2\right) + 150 + 100 + 150$$

which yields the numbers below:

|  $n$ | $C(n)$ | $C_P(n)$ | $S_{\max}(n)$ |
| ---: | -----: | -------: | ------------: |
|    2 |      7 |    *n/a* |         *n/a* |
|    3 |     13 |    *n/a* |         *n/a* |
|    4 |     21 |        5 |          1050 |
|    5 |     31 |        7 |          1450 |
|    7 |     57 |       14 |          2850 |
|    8 |     73 |       18 |          3450 |

Obviously, these scores are likely impossible to achieve in practice, especially for the larger values of $n$, because they require the player to match *all* the cards in the game in no more than 0.5 seconds each.


# Credits

*We stand on the shoulders of giants.* We use many open and closed source components to build our products.

Icon design by freepik.com

Original avatars by multiavatar.com
