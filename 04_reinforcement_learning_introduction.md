
__Markov decision process__
*added $$A$$ and $$r$$ based on Markov Process*

$$M=\{S,A,T,r\}$$ 
$$S$$ - state space, $$A$$ - action space, $$T$$ - transition operator (now a tensor!), $$r$$ - reward function
let:
-- $$\mu_{t,j}=p(s_t=j)$$
-- $$\xi_{t,k}=p(a_t=k)$$
-- $$T_{i,j,k}=p(s_{t+1}=i|s_t=j,a_t=k)$$
then:
-- $$\mu_{t,i}=\sum\limits_{j,k}T_{i,j,k}\mu_{t,j}\xi_{t,k}$$

reward
-- $$r:S\times A\rightarrow R$$
-- $$r(s_t,a_t)$$ - reward


# The goal of reinforcement learning
About the **policy**, in the course, there's no explicit definitions. However, the tutor provides an examples for it that is: **policy** is something from the state $$s$$ to the action $$a$$, it could be either explicitly neural network or some implicit way via value functions etc. **policy** is denoted as $$\pi_\theta(a|s)$$. We need train the objective function and finally get the $$\theta$$.

a __trajectory__ is a sequence over actions
__finite length trajectory__ : $$p_\theta(s_1,a_1,...,s_T,a_T)=p(s_1)\prod \limits_{t=1}^{T}\pi_\theta(a_t|s_t)p(s_{t+1}|s_t,a_t)$$
The left part is abbrevated as $$p_\theta(\tau)=p_\theta(s_1,a_1,...,s_T,a_T)$$

$$\theta^*=arg\max\limits_{\theta}E_{r \sim p_\theta(\tau)}[\sum\limits_{t}r(s_t,a_t)]$$
