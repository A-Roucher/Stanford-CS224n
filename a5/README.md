## My answers to the questions:

1.a) For the output vector to copy one of the value vectors, you would need all other keys pairs to be roughly orthogonal to the query q, so that their dot product is small.

b) One could set $q = k_{a} + k_{b}$.

c)
i) Here, one can use $q = \micro_{a} + \micro_{b}$.
With the same argument as before, with vanishingly small $\alpha$, all vectors willl be roughly equal to their means (= the desired result) + the covariates (0 according to the diagonal covariance matrix) + a result that is proportional to the square of $\alpha$, so quickly disappearing as $\alpha$ shrinks.

ii) Now the equation is the following: $\alpha_{a} = \frac{exp(1 + \delta_{a}^{T}\micro_{a} + O(\alpha)}{exp(1 + \delta_{a}^{T}\micro_{a} + O(\alpha) + exp(1 + O(\alpha))}$, with $\delta_{a} = k_{a} - \micro_{a}$ being uncontrolled by $\alpha$ this time. As we can't control coefficient $\delta_{a}$ precisely, vector $c$ may be unbalanced, i.e. have more or less $v_{a}$ compared to $v_{b}$: we don't $c$ as well as before.

d)
i) We can set $q_{1} = \micro_{a}$ and $q_{2} =  \micro_{b}$.

ii) This time the numerator term $exp(1 + O(\alpha))$ will be removed in the previous equation, solving the problem of uncontrolled coefficient.

e. i) Here we have $c_{2} = v_{2} = u_{a}$. And no it would not be possible to approximate $u_{b}$, because you can't remove the $u_{a}$ component.

ii) For the hint,  setting $V = u_{a}u_{a}^{T} / \beta + u_{b}u_{b}^{T} / \beta - u_{c}u_{c}^{T} / \beta$ does the job.


