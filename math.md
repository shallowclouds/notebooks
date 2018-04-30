$$ p_{i}^{'} = Rp_i + T $$

SSD: sum of square distance

$$ \sum ^2 = \sum\limits_{i=1}^n \Vert p_i^{'} - (Rp_i + T) \Vert   $$

需要找到R和T使得SSD最小。
$$
p^{'} = p^{''} \\
p_i^{''} \triangleq \widehat{R}p_i = \widehat{T} \\
\\
p^{'} \triangleq \frac {1} {N} \sum \limits_{i=1}^Np_i^{'} \\
p^{''} \triangleq \frac {1}{N} \sum\limits_{i=1}^N p_i^{''} = \widehat {R}p + \widehat{T} \\
p \triangleq \frac {1}{N} \sum \limits_{i=1}^N p_i \\
q_i \triangleq p_i - p \\
q_i^{'} \triangleq p_i^{'} - p^{'} \\
\sum {^2}= \sum \limits _{i=1}^N \Vert q_i^{'} -Rq_i \Vert ^2 \\
$$
找到 $\widehat{R}$ 使得 $\sum ^2 = \sum \limits _{i=1}^N \Vert q_i^{'} -Rq_i \Vert ^2$ 最小。

* 1. 计算 $p$ 和 $p^{'}$ ，以及 $ q_i $ 和 $ q_i^{'} $ 
  2. 计算 $ H \triangleq \sum \limits _{i=1}^N q_i q_i^{'t} $ 
  3. 对H进行奇异值分解（SVD）$ H = U\Lambda V^t $
  4. 计算 $ X = VU^t $ ，若x行列式值为+1，则 $ \widehat {R} = X $ 

 

