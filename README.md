# Mathematical-Modeling
## Compartmental Predictive Modeling
Below you will find two versions of the S.I.R. Model, one using the Euler Step method and the other using Runge Kutta's. Both are numerical solutions to predict the S (susceptible group), I (infected group), and R (recovered group). 
- $N$ = Total population
- $k$ = days to non-infectible
- $b$ = contacts per day that are sufficient to spread the disease
- $S = S(t)$ the number of susceptible persons
- $I = I(t)$ the number of infected persons
- $R = R(t)$ the number of recovered persons

- $s(t) = \dfrac{S(t)}{N}$
- $i(t) = \dfrac{I(t)}{N}$
- $r(t) = \dfrac{R(t)}{N}$

## Euler's Step:
Euler's Step makes use of that if we have a "rate formula" ($\dfrac{dx}{dy}$) then we can use said formula to generate a sequence of outputs. Essentially, we can do the following:
- Rate  of susceptible group: $\dfrac{ds}{dt} = (-b)s(t)i(t)$
- Rate of infected group: $\dfrac{dr}{dt} = (1/k)i(t)$
- Rate of recovered: $\dfrac{di}{dt} = (b)s(t)i(t) - (1/k)i(t)$
- $\dfrac{ds}{dt} => ds = (-b)s(t)i(t) * dt$ 

Where $ds$ is difference between $s_1$ and $s_0$, along with $dt$ being a suitably small step in time. 
- $s_1 = s_0 + ds$

## Runge Kutta:
Runge Kutta's method is fundamentally the same, however this method uses a mid-point trial step in order to increase the accuracy of the generated points. An Example in our situation: 
 - $di_{mid}= dt * ((b)i(t) - (1/k)i(t)) / 2 => r_1 = r_0 + (1/k) * di_{mid} * dt $
