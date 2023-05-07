Download Link: https://assignmentchef.com/product/solved-ift6390-assignment1-probabilistic-intuition
<br>
<h2>Small exercise on probabilities</h2>

A few years ago, a study was carried out with doctors in the United States, in order to measure their “probabilistic intuition”. It included the following question:

A percentage of 1<em>.</em>5% of women in their 40s who take a routine test (mammogram) have breast cancer. Among women that have breast cancer, there is a 87% chance that the test is positive. In women that do not have breast cancer, there is a probability of 9<em>.</em>6% that the test is positive.

A woman in her forties who has passed this routine test receives a positive test result. What is the probability that it is actually breast cancer?

<ol>

 <li>A) more than 90% B) between 70% and 90%</li>

 <li>between 50% and 70%</li>

 <li>between 30% and 50%</li>

 <li>between 10% and 30%</li>

 <li>less than 10%</li>

</ol>

95% of doctors surveyed responded B). What do you think? Formalize the question and calculate the exact probability. Hint: use Bayes rule …

<h2>2 Curse of dimensionality and geometric intuition in higher dimensions</h2>

<ol>

 <li>We consider a hyper-cube in dimension <em>d </em>(this is a generalization of the 2<em>D </em>square and the 3<em>D </em>cube) with side length <em>c </em>(which can be expressed in cm for example). What is the volume <em>V </em>of this hypercube?</li>

 <li>We define a random vector <em>X </em>of dimension <em>d </em>(<em>x ∈ </em>R<em><sup>d</sup></em>) distributed uniformly within the hypercube (the probability density <em>p</em>(<em>x</em>) = 0 for all <em>x </em>outside the cube). What is the probability density function <em>p</em>(<em>x</em>) for <em>x </em>inside the cube? Indicate which property(ies) of probability densities functions allow you to calculate this result.</li>

 <li>Consider the outter shell (border) of the hypercube of width 3% of <em>c </em>(covering the part of the hypercube extending from the faces of the cube and 0<em>.</em>03<em>c </em>inwards). For example, if <em>c </em>= 100cm, the border will be 3cm (left, right, top, etc …) and will delimit this way a second (inner) hypercube of side 100<em>−</em>3<em>−</em>3 = 94cm. If we generate a point <em>x </em>according to the previously defined probability distribution (by sampling), what is the probability that it falls in the border area? What is the probability that it falls in the smaller hypercube?</li>

 <li>Numerically calculate the probability that <em>x </em>will fall in the narrow border for the following values of <em>d</em>: 1<em>,</em>2<em>,</em>3<em>,</em>5<em>,</em>10<em>,</em>100<em>,</em></li>

 <li>What do you conclude about the distribution of points in higher dimensions, which is contrary to our intuition in smaller dimensions?</li>

</ol>

<h2>3 Parametric Gaussian density estimation, v.s. Parzen window density estimation</h2>

In this question we consider a dataset <em>D </em>= <em>{x</em><sup>(1)</sup><em>,…,x</em><sup>(<em>n</em>)</sup><em>} </em>with <em>x ∈</em>R<em><sup>d</sup></em>.

<ol>

 <li>Suppose we have trained the parameters of an <strong>isotropic </strong>Gaussian density function on D (by maximizing the likelihood) in order to estimate the probability density function.

  <ul>

   <li>Name these parameters and indicate their dimension.</li>

   <li>If we learn these parameters using the principle of maximum likelihood estimation, express the formula which will give us the value of the optimal parameters as a function of the data points in <em>D </em>— indicate only the formula that calculates the result, you are not asked to rederive it (the formulas for the maximum likelihood estimator can be found at the end of slide set number 5 on the</li>

  </ul></li>

</ol>

Gaussian distribution).

<ul>

 <li>What is the algorithmic complexity of this training method, i.e. of the method calculating these parameters?</li>

 <li>For a test point <em>x</em>, write the function that will give the probability density predicted at point <em>x</em>: <em>p</em>ˆ<em><sub>gauss</sub></em><em>−<sub>isotrop</sub></em>(<em>x</em>) =?</li>

 <li>What is the algorithmic complexity for calculating this prediction at each new point <em>x</em>?</li>

</ul>

<ol start="2">

 <li>Now consider that one uses Parzen windows with an isotropic Gaussian kernel of width (standard deviation) <em>σ </em>instead, and that these Parzen windows were trained on <em>D</em>.

  <ul>

   <li>Suppose that the user has fixed <em>σ</em>. What does the “training/learning” phase of these Parzen windows consist of?</li>

   <li>For a test point <em>x</em>, write in a single detailed formula (i.e. with exponentials), the function that will give the probability density predicted at point <em>x</em>: <em>p</em>ˆ<em><sub>Parzen</sub></em>(<em>x</em>) =?</li>

   <li>What is the algorithmic complexity for calculating this prediction at each new point <em>x</em>?</li>

  </ul></li>

 <li>Capacity/Expressivity

  <ul>

   <li>Which one of these two approaches (parametric Gaussian v.s. Parzen Gaussian kernel) has the highest <em>capacity </em>(in other words, higher expressivity)? Explain.</li>

   <li>With which one of these approaches, and in which scenario, are we likely to be over-fitting (i.e. memorizing the noise in our data)?</li>

   <li>The value <em>σ </em>in Parzen windows is usually treated as a hyperparameter, whereas for parametric Gaussian density estimation it is usually treated as a parameter. Why?</li>

  </ul></li>

 <li>Now consider parametric density estimation with a diagonal Gaussian density function.

  <ul>

   <li>Express the equation of a diagonal Gaussian density in R<em><sup>d</sup></em>. Specify what are its parameters and their dimensions.</li>

   <li>Show that the components of a random vector following a diagonal Gaussian distribution are independent random variables.</li>

   <li>Using <em>−</em>log<em>p</em>(<em>x</em>) as the loss, write down the equation corresponding to the empirical risk minimization on the training set <em>D </em>(in order to learn the parameters).</li>

   <li>Solve this equation analytically in order to obtain the optimal parameters.</li>

  </ul></li>

</ol>

<h2>4             Practical part: density estimation</h2>

<ol>

 <li>Implement a diagonal Gaussian parametric density estimator. It will have to work for data of arbitrary dimension <em>d</em>. As seen in the labs, it should have a <strong>train() </strong>method to learn the parameters and a method <strong>predict() </strong>which calculates the log density.</li>

 <li>Implement a Parzen density estimator with an isotropic Gaussian kernel. It will have to work for data of arbitrary dimension <em>d</em>. Likewise it should have a <strong>train() </strong>method and a <strong>predict() </strong>method that computes the log density.</li>

 <li>1D densities: From the Iris dataset examples, choose a subset corresponding to one of the classes (of your choice), and one of the characteristic features, so that we will be in dimension <em>d </em>= 1 and produce a single graph (using the plot function) including:

  <ul>

   <li>the data points of the subset (displayed on the <em>x </em>axis).</li>

   <li>a plot of the density estimated by your parametric Gaussian estimator.</li>

   <li>a plot of the density estimated by the Parzen estimator with a hyper-parameter <em>σ </em>(standard deviation) too small.</li>

   <li>a plot of the density estimated by the Parzen estimator with the hyper-parameter <em>σ </em>being a little too big.</li>

   <li>a plot of the density estimated by the Parzen estimator with the hyper-parameter <em>σ </em>that you consider more appropriate. Use a different color for each plot, and provide your graph with a clear legend.</li>

   <li>Explain how you chose your hyper-parameter <em>σ</em>.</li>

  </ul></li>

 <li>2D densities: Now add a second characteristic feature of Iris, in order to have entries in <em>d </em>= 2 and produce 4 plots, each displaying the points of the subset of the data (with the plot function ), and the contour lines of the density estimated (using the contour function):

  <ul>

   <li>by the diagonal Gaussian parametric estimator.</li>

   <li>by the Parzen estimator with the hyper-parameter <em>σ </em>(standard deviation ) being too small.</li>

   <li>by the Parzen estimator with the hyper-parameter <em>σ </em>being a little too big.</li>

   <li>by the Parzen estimator with the hyper-parameter <em>σ </em>that you consider more appropriate.</li>

   <li>Explain how you chose your hyper-parameter <em>σ</em></li>

  </ul></li>

</ol>