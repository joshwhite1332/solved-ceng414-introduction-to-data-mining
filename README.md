Download Link: https://assignmentchef.com/product/solved-ceng414-introduction-to-data-mining
<br>
1      Overview

<strong>Algorithm 1: </strong>Agglomerative Hierachical Clustering PseudocodeIn this THE, you are going to implement <strong>Agglomerative Hiearchical Clustering </strong>algorithm in Python language. For this purpose, you will be provided a template file and a driver file: In the template file, you are expected to implement the methods which have missing definitions(bodies). The driver file is provided to you to test your code. After you implement the methods in the template file, you will be able to test your implementation with various parameters and given dataset using the driver file. The pseudocode of the <strong>Agglomerative Hiearchical Clustering </strong>algorithm that you are expected to implement is as follows:

<strong>Data: </strong>2-D data points

<strong>Result: </strong>Clusters of 2-D data points

<ul>

 <li>Initialize each data point as a cluster</li>

 <li>Calculate the initial proximity matrix between all data points</li>

</ul>

<h3>3 repeat</h3>

<ul>

 <li>Merge the two closest clusters considering the linkage</li>

 <li>Update the proximity matrix to reflect the proximity between the new cluster and the</li>

</ul>

original clusters

<ul>

 <li><strong>until </strong><em>The desired number of clusters obtained</em>;</li>

</ul>

<h2>2      Tasks</h2>

In this THE, sample driver file (”the3 main.py”) implementation and Agglomerative Hierarchical Clustering template file (”the3 agglomerative clustering.py”) are given to you. If you check ”the3 agglomerative clustering.py” file, you will see sections like ”# TODO: Implement here”. Your job is to complete code sections that needs implementation.

<h3>2.1       Reading Input File (20 Pts.)</h3>

In this task, you are expected to implement the code that reads the dataset from a given file which will be used as input to <strong>Agglomerative Hiearchical Clustering </strong>algorithm. The dataset in the given file consists of 2-D data points where every data point is represented as a (x,y) tuple which are x-coordinate and y-coordinate values, respectively. You are expected to implement the <strong>”read input file()” </strong>function inside ”the3 agglomerative clustering.py” file. The necessary information on what this function returns is provided in the template file. This function is used to read data and feed it to the Agglomerative Hiearchical Clustering model.

The format of the file will be as follows:

(point1 x, point1 y)

(point2 x, point2 y)

(point3 x, point3 y)

.

. .

In the input file, the (x,y) coordinate values will be provided as floating point values with 2 decimal digits.

<h3>2.2       Initialize Clustering (5 Pts.)</h3>

In this task, you are expected to implement <strong>initialize clustering() </strong>method in ”the3 agglomerative clustering. py”. This method represents the first step of the algorithm given in Algorithm1:

The necessary information on what this function returns is provided in the template file.

<h3>2.3        Assign data points to clusters (75 Pts.)</h3>

In this task, you are expected to implement the <strong>”fit predict()” </strong>method inside ”the3 agglomerative clustering.

py”. This method takes desired number of clusters and linkage function as parameters and returns the resultant clusters. This method represents the main loop of the algorithm given in Algorithm1:

<h4>2.3.1          Calculating initial proximity matrix</h4>

In the above algorithm, step 2 defines the initial proximity matrix calculation. Initially, each data point will be assigned to an independent cluster as stated in step 1 of the algorithm. Step 2 of the algorithm states that the initial proximity matrix’ values are the pairwise distances between data points. In this THE, Euclidean distance function should be used to calculate pairwise distances between data points. In order to clarify the issue, assume the following 2-D points are given as in the following table:

<table width="279">

 <tbody>

  <tr>

   <td width="55"><strong>Point</strong></td>

   <td width="112"><strong>x Coordinate</strong></td>

   <td width="112"><strong>y Coordinate</strong></td>

  </tr>

  <tr>

   <td width="55"><strong>p1</strong></td>

   <td width="112">0.40</td>

   <td width="112">0.53</td>

  </tr>

  <tr>

   <td width="55"><strong>p2</strong></td>

   <td width="112">0.22</td>

   <td width="112">0.38</td>

  </tr>

  <tr>

   <td width="55"><strong>p3</strong></td>

   <td width="112">0.35</td>

   <td width="112">0.32</td>

  </tr>

  <tr>

   <td width="55"><strong>p4</strong></td>

   <td width="112">0.86</td>

   <td width="112">0.19</td>

  </tr>

  <tr>

   <td width="55"><strong>p5</strong></td>

   <td width="112">0.98</td>

   <td width="112">0.41</td>

  </tr>

  <tr>

   <td width="55"><strong>p6</strong></td>

   <td width="112">0.45</td>

   <td width="112">0.23</td>

  </tr>

 </tbody>

</table>

Considering the given data points, the corresponding initial proximity matrix will be formed as follows:

<table width="284">

 <tbody>

  <tr>

   <td width="34"> </td>

   <td width="42"><strong>p1</strong></td>

   <td width="42"><strong>p2</strong></td>

   <td width="42"><strong>p3</strong></td>

   <td width="42"><strong>p4</strong></td>

   <td width="42"><strong>p5</strong></td>

   <td width="42"><strong>p6</strong></td>

  </tr>

  <tr>

   <td width="34"><strong>p1</strong></td>

   <td width="42">0.00</td>

   <td width="42">0.23</td>

   <td width="42">0.22</td>

   <td width="42">0.57</td>

   <td width="42">0.59</td>

   <td width="42">0.30</td>

  </tr>

  <tr>

   <td width="34"><strong>p2</strong></td>

   <td width="42">0.23</td>

   <td width="42">0.00</td>

   <td width="42">0.14</td>

   <td width="42">0.67</td>

   <td width="42">0.76</td>

   <td width="42">0.27</td>

  </tr>

  <tr>

   <td width="34"><strong>p3</strong></td>

   <td width="42">0.22</td>

   <td width="42">0.14</td>

   <td width="42">0.00</td>

   <td width="42">0.53</td>

   <td width="42">0.64</td>

   <td width="42">0.13</td>

  </tr>

  <tr>

   <td width="34"><strong>p4</strong></td>

   <td width="42">0.57</td>

   <td width="42">0.67</td>

   <td width="42">0.53</td>

   <td width="42">0.00</td>

   <td width="42">0.25</td>

   <td width="42">0.41</td>

  </tr>

  <tr>

   <td width="34"><strong>p5</strong></td>

   <td width="42">0.59</td>

   <td width="42">0.76</td>

   <td width="42">0.64</td>

   <td width="42">0.25</td>

   <td width="42">0.00</td>

   <td width="42">0.56</td>

  </tr>

  <tr>

   <td width="34"><strong>p6</strong></td>

   <td width="42">0.30</td>

   <td width="42">0.27</td>

   <td width="42">0.13</td>

   <td width="42">0.41</td>

   <td width="42">0.56</td>

   <td width="42">0.00</td>

  </tr>

 </tbody>

</table>

A sample calculation is given below which calculates the distance between <em>p</em>1 and <em>p</em>2:

√         √

<sup>p</sup>(0<em>.</em>40 − 0<em>.</em>22)<sup>2 </sup>+ (0<em>.</em>53 − 0<em>.</em>38)<sup>2 </sup>=         0<em>.</em>0324 + 0<em>.</em>0225 =      0<em>.</em>0559 = 0<em>.</em>23                      (1)

When doing distance calculations, you are expected to round the result to 2 decimal digits.

<h4>2.3.2       Linkage functions</h4>

In the above algorithm, the linkage determines the methodology to merge the clusters. In this THE, <strong>”fit predict()” </strong>may be invoked with the following 3 linkage functions: ”MIN, MAX, GROUP AVERAGE”. You are expected to implement all the linkage functions to get full points. The description of these linkage functions are given below.

<strong>MIN LINKAGE: </strong>In the MIN version (a.k.a single link) of hierarchical clustering, the proximity of two clusters is defined as the minimum of the distance between any two points in the two different clusters. Mathematically:

<em>Proximity</em>(<em>C</em>1<em>,C</em>2) = <em>min</em>(<em>dist</em>(<em>P<sub>i</sub>,P<sub>j</sub></em>)) such that <em>P<sub>i </sub></em>∈ <em>C</em><sub>1</sub><em>,Pj </em>∈ <em>C</em>2                                     (2)

<strong>Example: </strong>Assume the 2-D data points given in the previous section. Assume after 1 iteration of the algorithm, the clusters form as follows: [p1],[p2],[p3,p6],[p4],[p5]. Here, each list (shown as ”[a,b,..]” where a,b are elements of the list) corresponds to an independent cluster and the elements inside each list is a member of that corresponding cluster. The proximity between clusters [p2] and [p3,p6] are given by:

= <em>min</em>(<em>dist</em>(<em>p</em>2<em>,p</em>3)<em>,dist</em>(<em>p</em>2<em>,p</em>6))

= <em>min</em>(0<em>.</em>14<em>,</em>0<em>.</em>27)

(3)

= 0<em>.</em>14

<strong>MAX LINKAGE: </strong>In the MAX version (a.k.a complete link) of hierarchical clustering, the proximity of two clusters is defined as the maximum of the distance between any two points in the two different clusters. Mathematically:

<em>Proximity</em>(<em>C</em>1<em>,C</em>2) = <em>max</em>(<em>dist</em>(<em>P<sub>i</sub>,P<sub>j</sub></em>)) such that <em>P<sub>i </sub></em>∈ <em>C</em><sub>1</sub><em>,Pj </em>∈ <em>C</em>2                                     (4)

<strong>Example: </strong>Assume the 2-D data points given in the previous section. Assume after 1 iteration of the algorithm, the clusters form as follows: [p1],[p2],[p3,p6],[p4],[p5]. Here, each list (shown as ”[a,b,..]” where a,b are elements of the list) corresponds to an independent cluster and the elements inside each list is a member of that corresponding cluster. The proximity between clusters [p2] and [p3,p6] are given by:

= <em>max</em>(<em>dist</em>(<em>p</em>2<em>,p</em>3)<em>,dist</em>(<em>p</em>2<em>,p</em>6)

= <em>max</em>(0<em>.</em>14<em>,</em>0<em>.</em>27)

(5)

= 0<em>.</em>27

<strong>GROUP AVERAGE LINKAGE: </strong>In the GROUP AVERAGE version of hierarchical clustering, the proximity of two clusters is defined as the average pairwise proximity among all pairs of points in the different clusters. Mathematically:

such that <em>P<sub>i </sub></em>∈ <em>C</em><sub>1</sub><em>,Pj </em>∈ <em>C</em>2                                  (6)

where <em>m</em><sub>1</sub><em>,m</em><sub>2 </sub>denote the number of elements in clusters <em>C</em><sub>1</sub><em>,C</em><sub>2</sub>, respectively.

<strong>Example: </strong>Assume the 2-D data points given in the previous section. Assume after 1 iteration of the algorithm, the clusters form as follows: [p1],[p2],[p3,p6],[p4],[p5]. Here, each list (shown as ”[a,b,..]” where a,b are elements of the list) corresponds to an independent cluster and the elements inside each list is a member of that corresponding cluster. The proximity between clusters [p2] and [p3,p6] are given by:

(7)

= 0<em>.</em>21

<h4>2.3.3              Merging the two closest clusters and updating the proximity matrix</h4>

This part of the algorithm represents the loop including the steps between 3-6. In order to merge the two closest clusters, the smallest pairwise proximity value is found in the proximity matrix: The corresponding clusters are then merged. As an example, assume the clusters after 1 iteration of the algorithm are formed as follows: [p1],[p2],[p3,p6],[p4],[p5]. Assume MIN is used as the linkage function. After calculating all the pairwise cluster distances, the resultant proximity matrix will be formed as follows:

<table width="279">

 <tbody>

  <tr>

   <td width="56"> </td>

   <td width="42"><strong>p1</strong></td>

   <td width="42"><strong>p2</strong></td>

   <td width="56"><strong>p3,p6</strong></td>

   <td width="42"><strong>p4</strong></td>

   <td width="42"><strong>p5</strong></td>

  </tr>

  <tr>

   <td width="56"><strong>p1</strong></td>

   <td width="42">0.00</td>

   <td width="42">0.23</td>

   <td width="56">0.22</td>

   <td width="42">0.57</td>

   <td width="42">0.59</td>

  </tr>

  <tr>

   <td width="56"><strong>p2</strong></td>

   <td width="42">0.23</td>

   <td width="42">0.00</td>

   <td width="56">0.14</td>

   <td width="42">0.67</td>

   <td width="42">0.76</td>

  </tr>

  <tr>

   <td width="56"><strong>p3,p6</strong></td>

   <td width="42">0.22</td>

   <td width="42">0.14</td>

   <td width="56">0.00</td>

   <td width="42">0.41</td>

   <td width="42">0.56</td>

  </tr>

  <tr>

   <td width="56"><strong>p4</strong></td>

   <td width="42">0.57</td>

   <td width="42">0.67</td>

   <td width="56">0.41</td>

   <td width="42">0.00</td>

   <td width="42">0.25</td>

  </tr>

  <tr>

   <td width="56"><strong>p5</strong></td>

   <td width="42">0.59</td>

   <td width="42">0.76</td>

   <td width="56">0.56</td>

   <td width="42">0.25</td>

   <td width="42">0.00</td>

  </tr>

 </tbody>

</table>

The smallest value in the above matrix is 0.14 which is the proximity between [p2] and [p3,p6] clusters. These two clusters are merged. After merging these 2 clusters, the proximity matrix is updated as follows:

<table width="282">

 <tbody>

  <tr>

   <td width="78"> </td>

   <td width="42"><strong>p1</strong></td>

   <td width="78"><strong>p2,p3,p6</strong></td>

   <td width="42"><strong>p4</strong></td>

   <td width="42"><strong>p5</strong></td>

  </tr>

  <tr>

   <td width="78"><strong>p1</strong></td>

   <td width="42">0.00</td>

   <td width="78">0.22</td>

   <td width="42">0.57</td>

   <td width="42">0.59</td>

  </tr>

  <tr>

   <td width="78"><strong>p2,p3,p6</strong></td>

   <td width="42">0.22</td>

   <td width="78">0.00</td>

   <td width="42">0.41</td>

   <td width="42">0.56</td>

  </tr>

  <tr>

   <td width="78"><strong>p4</strong></td>

   <td width="42">0.57</td>

   <td width="78">0.41</td>

   <td width="42">0.00</td>

   <td width="42">0.25</td>

  </tr>

  <tr>

   <td width="78"><strong>p5</strong></td>

   <td width="42">0.59</td>

   <td width="78">0.56</td>

   <td width="42">0.25</td>

   <td width="42">0.00</td>

  </tr>

 </tbody>

</table>

The algorithm should stop whenever the desired number of clusters are obtained. The desired number of clusters will be provided as input to <strong>”fit predict()” </strong>function. As an example, assume the desired number of clusters=2 is provided as input. Then, the algorithm should eventually stop when the number of clusters is 2. Continuing with the above example, the algorithm will eventually stop and will return the following clusters: [p1,p2,p3,p6], [p4,p5]. The necessary information on what this method returns is provided in the template file.

<h2>3        Rules, Suggestions and Tips</h2>

<ul>

 <li>Make sure you keep the template file (”the3 agglomerative clustering.py”) structure that is given to you. You can add method(s)/function(s)/member variable(s)/lines of code to the template file, but can not remove any function/method/member variable. Also, you MUST have following lines defined in your code:</li>

</ul>

<h3>self.data=input data self.clusters current=[ ]</h3>

<ul>

 <li>You are expected to implement the desired method(s)/function(s) bodies after ”# TODO: Implement here” comment line. You are expected to write return statements inside function(s)/method(s) considering their usages in the driver file (”the3 main.py”).</li>

 <li>You are NOT allowed to import any libraries other than the given libraries in the template file. If this rule is violated, your submission will not be evaluated and you will get 0 points for this THE.</li>

 <li>Sample input file will be provided to you. The output file considering the code in the driver file will also be provided. The function(s)/method(s) that you are going to implement inside the template file should stick with their usage inside the driver file.</li>

 <li>After you complete your implementation, check sure your outputs are the same as the outputs inside the sample output file to get credits.</li>

 <li>You can test your code with different parameters and input file(s) by modifying the driver file. You will not submit the driver file and it will not be used for evaluation.</li>

 <li>The sample input and output files are provided you as ”sample input.txt” and ”sample output.txt”</li>

 <li>In order to run your code, use the following syntax:</li>

</ul>

python the3 main.py <em>&lt; </em>input file name <em>&gt; </em><strong>Ex: </strong>python the3 main.py sample input.txt