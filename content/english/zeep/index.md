---
title: Zeep
date: 2021-05-20
image : images/portfolio/zeep.png
# image_webp : images/portfolio/generic.webp
# draft: true
hasMath: true # define this to be able to use math typesetting between $ $ or $$ $$
categories:
  - Games
---

The score is calculated based on the following as a function of *time* between the last match and this match:

$$S_n=m\times\min\left(\frac{\left(\frac{100}{x+0.13}\right)}{1.5},100\right), t_n \gt t_{n-1}$$

where $m \in \{1, 1.5, 2\}$ is the current streak multiplier, for 1, 2 or 3 or more sequential matches.

{{< embed url="https://www.desmos.com/calculator/7le7xivcqt?embed" height=300 >}}


## Game Size

The total number of cards in the game $C(n)$--which is the same as the total number of symbols in the game--is:

$$C(n)=n^2+n+1$$

| symbols/card |  $n$ |      $C(n)$ | Notes            |
| -----------: | ---: | ----------: | ---------------- |
|            3 |    2 | 4+2+1  =  7 |
|            4 |    3 | 9+3+1  = 13 |
|            5 |    4 | 16+4+1 = 21 |
|            6 |    5 | 25+5+1 = 31 |
|            7 |    6 | 36+6+1 = 43 | (does not exist) |
|            8 |    7 | 49+7+1 = 57 |
|            9 |    8 | 64+8+1 = 73 |

## Maximum Score

The max score depends on the size of the game. For a game of order $n$, we will have a total of $C(n)$ cards. The cards per player $C_P(n)$ is calculated as follows.
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

Obviously, these scores are likely impossible to achieve in practice, especially for the larger values of $n$, because they require the player to match *all* the cards in the game in no more than 0.5 seconds.