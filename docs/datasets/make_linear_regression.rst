######################
make_linear_regression
######################

Generate data by formula.

****************
Data description
****************
Synthetic data generated by Generate data by formula:

 | ``Y' = X1 + X2 * T + E``
 | ``Y = Y', if Y' - int(Y') > eps,``
 | ``Y = 0,  otherwise.``

Statistics for default parameters and size equals 100,000:

+--------------------------+-------------+
|Features                  |           3 |
+--------------------------+-------------+
|Treatment                 |           2 |
+--------------------------+-------------+ 
|Samples total             |      `size` |
+--------------------------+-------------+ 
|Y not equals 0            |     0.49438 |
+--------------------------+-------------+ 
|Y values                  | 0 to 555.93 |
+--------------------------+-------------+


+-----------------+-----------------------------------------------------------------------------+
| **Parameters:** | | **size**: integer                                                         |
|                 | |   The number of observations.                                             |
|                 | | **x1_params** : tuple(mu, sigma), default: (0, 1)                         |
|                 | |   The feature with gaussian distribution and mean=mu, sd=sigma.           |
|                 | |   X1 ~ N(mu, sigma)                                                       |
|                 | | **x2_params** : tuple(mu, sigma), default: (0, 0.1)                       |
|                 | |   The feature with gaussian distribution and mean=mu, sd=sigma.           |
|                 | |   X2 ~ N(mu, sigma)                                                       |
|                 | | **x3_params** : tuple(mu, sigma), default: (0, 1)                         |
|                 | |   The feature with gaussian distribution and mean=mu, sd=sigma.           |
|                 | |   X3 ~ N(mu, sigma)                                                       |
|                 | | **t_params** : tuple(mu, sigma), default: (0, 1)                          |
|                 | |   The treatment with uniform distribution. Min value=min, Max value=max-1 |
|                 | |   T ~ R(min, max)                                                         |
|                 | | **e_params** : tuple(mu, sigma), default: (0, 1)                          |
|                 | |   The error with gaussian distribution and mean=mu, sd=sigma.             |
|                 | |   E ~ N(mu, sigma)                                                        |
|                 | | **eps** : tuple(mu, sigma), default: (0, 1)                               |
|                 | |   The border value.                                                       |
|                 | | **random_state** : integer, default=777                                   |
|                 | |   random_state is the seed used by the random number generator.           |
+-----------------+-----------------------------------------------------------------------------+
| **Returns:**    | | **dataset**: pandas DataFrame                                             |
|                 | |   Generated data.                                                         |
+-----------------+-----------------------------------------------------------------------------+

********
Examples
********

.. code-block:: python3

   from pyuplift.datasets import make_linear_regression
   df = make_linear_regression(10000)
   print(df)
