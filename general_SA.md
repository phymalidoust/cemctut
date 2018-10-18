## Generic terms and algorithm of simulated annealing method

Among the optimization algorithms, simulated annealing (SA) possesses outstanding aspects such as finding global extermum of highly complicated functions without getting caught at local extremums. For small and less complicated systems other algorithms such as *hill climbing* or *random walk* might be sufficient. However, they always have their own risks: The former can stuck in a local minimum and the latter may never converge. Nonetheless, when a large and highly complicated and large problems are in question, SA algorithms shows great successes and provide good estimations (not the very best, of course). The history of SA potimization technique goes back to 1980s [1-3]. 



The algorithm of SA to find, for example, the global mimimum of a function $E(x)$ is as follows ($E(x)$ can be the energy of a system as a function a variable $x$). 

It considers an interval for the variable $x\in [x_{min}:x_{max}]$. Next, starts with two intial guesses for the variable $x=x_{r}^{1,2}$ that are chosen at random within the given interval for a fake 'temperature' $T\in [T_{max}:T_{min}]$ and calculates $E(x_{r}^{1,2})$. Finds their difference $\Delta E = E(x_r^2)-E(x_r^1)$. Since it is going to find minimum, if $\Delta E<0$, then keeps solution $x_r^1$. Otherwise, if $\exp({{\Delta E}/T})> X_r$ then keeps $x_r^2$. In the Next step, it generates a new value for $E(x_r^N)$ and compares with the previous solution $E(x_r^P)$, namely constructs  $\Delta E = E(x_r^N)-E(x_r^P)$. This loop should be repeated for several times per each temperature value $T$ and continues until $T = T_{min}$.
$$
\begin{align}
&\color{blue} {\text{FOR}}\;\{\;T=T_{max}:T_{min}\;\}\;\; \\
&x_r^P = x_r^1 = \text{random}()\,\rightarrow E^P = E(x_r^P)\\
&x_r^N = x_r^2 = \text{random}()\, \rightarrow E^N = E(x_r^N)\\
&\Delta E = E^N - E^P\\
&\color{red}{\text{IF}}\;\{\;\Delta E <0\;\} \;\;\;(\text{hill climbing})\\
&x_r^P =x_r^N\\
&\color{red}{\text{ELSEIF}}\;\{\;\exp({{\Delta E}/T})\;> \text{random}()\;\} \;\;\;&(\text{random walk})\\
&x_r^P =x_r^N\\
&\color{red}{\text{ENDIF}}\\
&\color{blue}{\text{ENDFOR}}
&\end{align}
$$
Below are two movies that show how SA algorithm tries to find a good solution.



* SA tries to find the global maximum without stopping at a local maximum. By decreasing $T$, SA approaches the global maximum.



![Hill_Climbing_with_Simulated_Annealing](/figures/Hill_Climbing_with_Simulated_Annealing.gif)



* SA tries to solve the famous travelling salesman problem among 125 points, i.e., finding a path that has the minimum length and connects all 125 points. 


![Travelling_salesman_problem_solved_with_simulated_annealing](/figures/Travelling_salesman_problem_solved_with_simulated_annealing.gif)











----------------------------------------------------------------

[1] S. Kirkpatrick, C. D. Gelatt Jr., M. P. Vecchi, *Optimization by Simulated Annealing*, [Science 220, 671 (1983)](http://science.sciencemag.org/content/220/4598/671/tab-article-info).

[2] S. Kirkpatrick, *Optimization by simulated annealing: Quantitative studies*, [Journal of Statistical Physics 34, 975 (1984)](https://link.springer.com/article/10.1007/BF01009452).

[3] P. J. M. van Laarhoven and E. H. L. Aarts, *Simulated Annealing: Theory and Applications*, [Springer, 1988](https://www.springer.com/gp/book/9789027725134).

