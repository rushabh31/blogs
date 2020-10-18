<span style="color:#D3EBD5">The Pyramid Match Kernel: Discriminative Classification with Sets of Image Features</span>

<span style="color:#81BFB7">Kristen Grauman and Trevor Darrell</span>

<span style="color:#81BFB7">Massachusetts Institute of Technology</span>

<span style="color:#81BFB7">Computer Science and Artificial Intelligence Laboratory</span>

<span style="color:#81BFB7">Cambridge\, MA\, USA</span>

Introduction

Related Work

Pyramid Match Kernel

Satisfying Mercer’s Condition

Results

Conclusions

<img src="img/Pyramid-Match-Kernal0.jpg" width=36px />

<img src="img/Pyramid-Match-Kernal1.jpg" width=52px />

<img src="img/Pyramid-Match-Kernal2.jpg" width=45px />

<img src="img/Pyramid-Match-Kernal3.jpg" width=31px />

<img src="img/Pyramid-Match-Kernal4.jpg" width=43px />

<img src="img/Pyramid-Match-Kernal5.jpg" width=25px />

<img src="img/Pyramid-Match-Kernal6.jpg" width=47px />

__It is often useful to represent a single example by the collection of local features or parts that comprise it\.__

__The image can be described by local features extracted from patches around salient interest points\, or a shape may be described by local descriptors defined at edge points\.__

_Set of Features in two images_

<img src="img/Pyramid-Match-Kernal7.jpg" width=500px />

<img src="img/Pyramid-Match-Kernal8.jpg" width=500px />

<img src="img/Pyramid-Match-Kernal9.png" width=500px />

<img src="img/Pyramid-Match-Kernal10.png" width=500px />

__To perform learning tasks like categorization or recognition with such representations is challenging in such cases\.__

__Support Vector Machine \(SVM\) is a widely used approach to discriminative classification that finds the optimal separating hyperplane between two classes\.__

__Kernel functions\, which measure similarity between inputs\, introduce non\-linearities to the decision functions; the kernel non\-linearly maps two examples from the input space to the inner product in some feature space\.__

__Conventional kernel\-based algorithms are designed to operate on fixed\-length vector inputs and hence commonly used general\-purpose kernels defined on n inputs \(e\.g\.\, Gaussian RBF\, polynomial\) are not applicable in the space of vector sets\.__

__The pyramid match kernel – a new kernel function over unordered feature sets that allows them to be used effectively and efficiently in kernel\-based learning methods\. Each feature set is mapped to a multiresolution histogram that preserves the individual features’ distinctness at the finest level\.__

_To perform learning tasks like categorization or recognition with such representations is challenging in such cases\._

_Pyramid Match Kernel_

__Pyramid matching: an efficient method that maps unordered feature sets to multi\-resolution histograms__  __\.__

__Computes a weighted histogram intersection to  find implicit correspondences based on finest  resolution histogram cell where a matched pair first appears__  __\.__

__Approximates similarity measured by optimal  correspondences between feature sets of  unequal cardinality__  __\.__

1GraumanandDarrell\, The PyramidMatchKernel:DiscriminativeClassificationwithSetsofImageFeatures\, IEEEICCV2005\,Vol2\, pp\.1458–1465

<span style="color:#517974">histogram pyramids</span>

<img src="img/Pyramid-Match-Kernal11.png" width=500px />

<img src="img/Pyramid-Match-Kernal12.png" width=500px />

<span style="color:#517974">number of newly matched pairs at level</span>  <span style="color:#517974"> _i_ </span>

<img src="img/Pyramid-Match-Kernal13.png" width=500px />

<span style="color:#517974">measure of difficulty of a match at level</span>  <span style="color:#517974">i</span>

_Pyramid Match Kernel_

__Weights inversely proportional to bin size__

__Normalize kernel values to avoid favoring large sets__

<img src="img/Pyramid-Match-Kernal14.png" width=440px />

<img src="img/Pyramid-Match-Kernal15.png" width=500px />

_Histogram Intersection_

<img src="img/Pyramid-Match-Kernal16.png" width=500px />

<img src="img/Pyramid-Match-Kernal17.png" width=500px />

<img src="img/Pyramid-Match-Kernal18.png" width=52px />

<img src="img/Pyramid-Match-Kernal19.png" width=203px />

<img src="img/Pyramid-Match-Kernal20.png" width=500px />

<img src="img/Pyramid-Match-Kernal21.png" width=52px />

<img src="img/Pyramid-Match-Kernal22.png" width=440px />

<img src="img/Pyramid-Match-Kernal23.png" width=439px />

<img src="img/Pyramid-Match-Kernal24.png" width=208px />

<img src="img/Pyramid-Match-Kernal25.png" width=203px />

__matches at this level__

__matches at previous level__

<img src="img/Pyramid-Match-Kernal26.png" width=500px />

<img src="img/Pyramid-Match-Kernal27.png" width=500px />

Difference in histogram intersections across levels counts _number of_  _new pairs_ matched

_Histogram Intersection_

<img src="img/Pyramid-Match-Kernal28.png" width=500px />

_Pyramid Match Kernel: Method_

__1\-D point sets X\, Y on grid of size 1__

_Pyramid Match Kernel: Method_

__1\-D point sets X\, Y on grid of size 1 \- level 0 histograms__

<img src="img/Pyramid-Match-Kernal29.png" width=217px />

<img src="img/Pyramid-Match-Kernal30.png" width=207px />

_Pyramid Match Kernel: Method_

__1\-D point sets X\, Y on grid of size 1 \- level 0 histograms \- intersection__

<img src="img/Pyramid-Match-Kernal31.png" width=217px />

<img src="img/Pyramid-Match-Kernal32.png" width=207px />

_Pyramid Match Kernel: Method_

__1\-D point sets X\, Y on grid of size 1 \- level 0 histograms \- intersection  2\.__

__Matches weighted by 1\.__

__Using                      the total similarity score: 2 × 1 = 2__

<img src="img/Pyramid-Match-Kernal33.png" width=500px />

<img src="img/Pyramid-Match-Kernal34.png" width=464px />

<img src="img/Pyramid-Match-Kernal35.png" width=216px />

_Pyramid Match Kernel: Method_

__1\-D point sets X\, Y on grid of size 2 \- level 1 histograms – intersection\.__

__\(2 matches weighted by 1\) \+ \(2 weighted by ½ \)\.__

__Using                      calculate total similarity score: 2 × 1 \+ 2 x ½ =3__

<img src="img/Pyramid-Match-Kernal36.png" width=500px />

<img src="img/Pyramid-Match-Kernal37.png" width=450px />

<img src="img/Pyramid-Match-Kernal38.png" width=217px />

_Pyramid Match Kernel: Method_

__1\-D point sets X\, Y on grid of size 4 \- level 2 histograms \- intersection\.__

__\(2 matches weighted by 1\) \+ \(2 weighted by ½ \) \+ \(1 weighted by ¼ \)__

__Using                    total similarity score: 2 × 1 \+ 2 x ½ \+ 1 x ¼  = 3\.25__

<img src="img/Pyramid-Match-Kernal39.png" width=500px />

_Pyramid Match Kernel: Method_

__Weighted sum of histogram intersections at different levels of two images approximates their optimal pairwise matching__

_Pyramid Match Kernel: Efficiency_

__For sets with m features of dimension d\, and pyramids with L levels\, computational complexity of__

_Pyramid match kernel:_

<img src="img/Pyramid-Match-Kernal40.png" width=289px />

_Existing set kernel approaches:_

<img src="img/Pyramid-Match-Kernal41.png" width=335px />

<img src="img/Pyramid-Match-Kernal42.png" width=335px />

_Results: Approximate Partial Matchings_

<img src="img/Pyramid-Match-Kernal43.png" width=500px />

Trial number \(sorted by optimal distance\)

Trial number \(sorted by optimal distance\)

__2\-D points with values uniformly distributed between 1 and 1000\.__

__In one data set\, each point set had equal cardinalities \(100 points each\)\, while in the other cardinalities varied randomly from 5 to 100\.__

_Results : Approximate Partial Matchings_

__Equal cardinality case \(plot on left\)\, both the pyramid match and the L1 embedding produce good approximations; both are on average less than 9% away from the optimal measure\.__

__Pyramid match also approximated the partial matching for the unequal cardinality case and its matchings continue to follow the optimal matching’s trend since it does not penalize outliers\, whereas the L1 embedding fails because it requires all points to match to something\.__

__This method was less than 9% on an average away from the optimal matching’s measure for the unequal cardinality case\, while the L1 matching has an average error of 400%__

_Results : Object Recognition_

* __Train SVM by computing kernel values between all labeled training examples\.__
* __Classify novel examples by computing kernel values against support vectors__
* __ETH\-80 database:__
* __\- 8 object classes__
* __Features:__
  * __\- Harris detector__
  * __\- PCA\-SIFT descriptor\, d=10__

<img src="img/Pyramid-Match-Kernal44.png" width=500px />

<img src="img/Pyramid-Match-Kernal45.png" width=335px />

<img src="img/Pyramid-Match-Kernal46.png" width=335px />

<img src="img/Pyramid-Match-Kernal47.png" width=289px />

_Results : Object Recognition_

<img src="img/Pyramid-Match-Kernal48.png" width=500px />

* Caltech objects database 101 object classes
* Features:
  * SIFT detector
  * PCA\-SIFT descriptor\, _d_ =10
* 30 training images / class
* 43% recognition rate
* \(1% chance performance\)
* 0\.002 seconds per match

