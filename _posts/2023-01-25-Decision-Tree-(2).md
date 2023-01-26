
rand

______
#### Gist:
1. Prune
2. Algorithms and Pros & Cons:
    - ID3
    - C4.5
    - CART


___
### ID3 - Information Gain

1. ID3 uses greedy algorithm and picks the feature associated with the max information gain as the root node. 
2. In a top-down approach, it dives deeper by working on a subsample space of each branch resulted from the orignial split; again uses greedy algorithm to pick the features as subsequent internal nodes.
3. Repeat until there is an unique label in the subset, will be leaf node

$$H(D) = \sum_k \frac{|C_k|}{|D|} \cdot log_2\left(\frac{|C_k|}{|D|}\right)$$

where $$|D|$$ is the size of full sample 
and $$|C_k|$$ is the size of sample with label $$k$$

For any feature $$A$$, the conditional information entropy is,

\begin{eqnarray*}
H(D|A) &&= \sum_i(\frac{|D_i|}{|D|}) \cdot H(D_i|A) \\
&&= \sum_i(\frac{|D_i|}{|D|}) \left( \sum_k \frac{|D_{ik}|}{|D_i|} \cdot log_2\left(\frac{|D_{ik}|}{|D_i|} \right) \right) 
\end{eqnarray*}


where $$\frac{|D_i|}{|D|}$$ is also the prior of 
attribute $$X$$
#### Cons:
1. No prune, overfitting
2. ID3 can only deal with discrete features but not continuous.
3. ID3 favors features that take more values (eg. ID) since impurity tends to be smaller for those features and thus information gain greater.
4. ID3 no preprocessing of nan
