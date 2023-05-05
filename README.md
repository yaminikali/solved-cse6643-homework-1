Download Link: https://assignmentchef.com/product/solved-cse6643-homework-1
<br>
<h1>Problem 1</h1>

Suppose <em>A </em>is a lower triangular matrix. Let <em>I </em>be the identity matrix. We wish to show that <em>A</em><sup>−1 </sup>is also lower triangular. Notice that <em>I </em>= <em>AA</em><sup>−1</sup>. Let <em>a<sub>ij </sub></em>and <em>b<sub>ij </sub></em>be the elements of <em>A </em>and <em>A</em><sup>−1 </sup>respectively. Then we can establish the following relationship:



<sub></sub><sub></sub><sup></sup><em>a</em>11<em>b</em>1<em>j </em>= <em>δ</em>1<em>j</em>

<sup></sup><sub></sub><em>a</em>21<em>b</em>1<em>j </em>+ <em>a</em>22<em>b</em><sub>2</sub><em>j </em>= <em>δ</em><sub>2</sub><em>j</em>

…<em>a</em><em>n</em>1<em>b</em>1<em>j </em>+ <em>… </em>+ <em>a</em><em>nnb</em><em>nj </em>= <em>δ</em><em>nj</em>

where <em>δ<sub>ij </sub></em>is the Kronecker Delta. This may be rewritten as follows:

Thus it can be seen that whenever the column index exceeds the row index for <em>b<sub>ij</sub></em>, <em>b<sub>ij </sub></em>= 0, so <em>A</em><sup>−1 </sup>is lower triangular.




<h1>Problem 2</h1>

Let ||<em>A</em>|| be an induced matrix on some <em>A </em>∈ C<em><sup>m</sup></em><sup>∗<em>m</em></sup>. By definition, <em>ρ</em>(<em>A</em>) = <em>λ</em><sub>max</sub>. Consider the eigenvector for <em>λ</em><sub>max</sub>, <em>x</em>. By definition, <em>Ax </em>= <em>λ</em><sub>max</sub><em>x</em>. Taking their norms gives ||<em>Ax</em>|| = ||<em>λ</em><sub>max</sub><em>x</em>|| = |<em>λ</em><sub>max</sub>||<em>x</em>|. This can be rewritten as ||<em>A</em>|||<em>x</em>| ≥ |<em>λ</em><sub>max</sub>|<em>x</em>|, then removing |<em>x</em>| gives ||<em>A</em>|| ≥ |<em>λ</em><sub>max </sub>= <em>ρ</em>(<em>A</em>) as desired.

<h1>Problem 3</h1>

Suppose <em>A </em>∈ C<sup>202∗202 </sup>with ||<em>A</em>||<sub>2 </sub>= 100 and ||<em>A</em>||<em><sub>F </sub></em>= 101. From the text, we know ||<em>A</em>||<sub>2 </sub>= <em>σ</em><sub>1 </sub>and ||<em>A</em>||<em><sub>F </sub></em>=

.          Thus, 101 =  after plugging in values.              Rearranging, this becomes 201 =

. Since the smallest value <em>σ</em><sub>202 </sub>can obtain is 1, we arrive at <em>σ</em><sub>1</sub><em>/σ</em><sub>202 </sub>≥ 100.

<h1>Problem 4</h1>

For this problem, I implemented a code “Problem4” in MATLAB that generated random matrices of size <em>m </em>∗ <em>m</em>

√

with a mean value of 0 and a standard deviation of <em>m</em>. Using MATLAB’s built-in norm functions, I obtained the p-norm for p= 1<em>,</em>2<em>,</em>∞ for the random matrices. As my GTID is odd, I computed the ratio between the 2-norm and infinity-norm as well. Additionally, I computed the average condition number for the matrices. My results are shown below:

Page 1

#10<sup>4                                                                                       </sup><strong>Average One Norm Values</strong>

These results follow intuition, I believe. Both the one norm and inf norm can be defined as the maximum of the sum of columns and rows, respectively. So as <em>m </em>→ ∞, it follows that ||<em>A</em>||<sub>1 </sub>→ ∞ and ||<em>A</em>||<sub>∞ </sub>→ ∞. The ||<em>A</em>||<sub>2 </sub>results behave in a more linear manner, which is makes sense given ||<em>A</em>||<sub>2 </sub>|<em>λ<sub>max</sub></em>|. Because the two norm behaves linearly and the inf norm behaves super linearly, the ratio between the two should cover to 0 as the inf norm increases at a faster rate. The condition number for the random matrix overall increases as the size of the matrix increases, though there are dips and spikes in the results. Overall, this still makes sense as a random matrix will tend to being ill-conditioned as it’s size increases.

<h1>Problem 5</h1>

For this problem, we had to approximate solutions to  using Gaussian elimination with and

without partial pivoting. My MATLAB code for this is called “Problem5”. My results may be seen in the following graphs:

(a) Gaussian elimination for <em>λ </em>= 0                                                        (b) Gaussian elimination for <em>λ </em>= 2

(c) True solution for <em>λ </em>= 0                                                                     (d) True solution for <em>λ </em>= 2

0

0

-0.2

-0.2

-0.4

-0.4

-0.6-0.6

-0.8-0.8

-1-1

-1.2-1.2

-1.4-1.4

-1.6

-1.6

-1.8

-1.8

-2

-20                                                                                                                                                                                                       0.2                            0.4                           0.6                           0.8                              1

0                             0.2                            0.4                            0.6                            0.8                              1

When comparing the true solutions to the differential equation with the approximation, for <em>λ </em>= 0 the average relative error was on the scale of 10<sup>−10 </sup>while for <em>λ </em>= 2 the average relative error was on the scale of 10<sup>−16</sup>. These are extremely good results, but not surprising as small step sizes were used, which lead to refined answers. For the various computations, the CPU runtimes are presented below:

Table 1: CPU Runtimes in seconds

<table width="601">

 <tbody>

  <tr>

   <td width="43">Size</td>

   <td width="149"><em>λ </em>= 0 without pivoting</td>

   <td width="130"><em>λ </em>= 0 with pivoting</td>

   <td width="149"><em>λ </em>= 2 without pivoting</td>

   <td width="130"><em>λ </em>= 2 with pivoting</td>

  </tr>

  <tr>

   <td width="43">200</td>

   <td width="149">0.096323</td>

   <td width="130">0.264187</td>

   <td width="149">0.142005</td>

   <td width="130">0.156812</td>

  </tr>

  <tr>

   <td width="43">400</td>

   <td width="149">0.300473</td>

   <td width="130">0.552547</td>

   <td width="149">0.527399</td>

   <td width="130">0.421511</td>

  </tr>

  <tr>

   <td width="43">800</td>

   <td width="149">2.041219</td>

   <td width="130">3.074913</td>

   <td width="149">4.295169</td>

   <td width="130">2.745189</td>

  </tr>

  <tr>

   <td width="43">1000</td>

   <td width="149">3.963348</td>

   <td width="130">5.379148</td>

   <td width="149">8.774305</td>

   <td width="130">6.098762</td>

  </tr>

  <tr>

   <td width="43">2000</td>

   <td width="149">34.324527</td>

   <td width="130">40.059037</td>

   <td width="149">107.276456</td>

   <td width="130">85.589778</td>

  </tr>

  <tr>

   <td width="43">4000</td>

   <td width="149">398.864609</td>

   <td width="130">313.789217</td>

   <td width="149">906.203220</td>

   <td width="130">859.576564</td>

  </tr>

 </tbody>

</table>

These CPU times make sense, as both algorithms theoretically flops.