## L5 Thinking
**1、什么是矩阵分解，都有哪些应用场景？**  
答：矩阵分解是将M个用户与N个商品构成的M×N矩阵分解成M×A的用户特征矩阵以及A×N的商品特征矩阵的过程，其中A是商品隐分类种类的个数。矩阵分解主要是用来做矩阵信息的补全，根据用户对商品的已有评分预测用户对其他商品的评分，或通过用户的一些隐式行为（如点击）预测用户的偏好，并通过计算出的偏好来进行商品推荐。此外，矩阵分解还可以对特征进行降维，实现如对图像进行压缩的用途。  

**2、矩阵分解算法ALS-WR是如何进行的？**  
答：假设用户商品矩阵为R矩阵，用户特征矩阵为U矩阵，商品特征矩阵为I矩阵，那么有R = UT × I  
ALS-WR算法的目标函数为 min （R – ITU）T（R - ITU）+λ（UTU+ITI）  
步骤：（1）用较小的随机数初始化 I 矩阵；  
（2）固定 I 矩阵，计算使目标函数最小化的U矩阵；  
（3）固定U矩阵，计算使目标函数最小化的I矩阵；  
（4）对I矩阵与U矩阵进行反复迭代，直到RMSE值的变化率小于设定的阈值  
**3、梯度下降法中的批量梯度下降（BGD），随机梯度下降（SGD），和小批量梯度下降有什么区别（MBGD）？**  
答：（1）批量梯度下降（BGD）每次的参数更新使用全量样本进行更新，随机梯度下降（SGD）每次的参数更新仅使用单个样本进行更新，小批量梯度下降（MBGD）每次的参数更新使用部分样本进行更新。  
（2）批量梯度下降（BGD）的计算量较大，收敛速度较慢，但参数更新的路径较为稳定；随机梯度下降（SGD）的计算量相对较小，收敛速度较快，但最终的参数可能会落在局部最优解，而非全局最优解；小批量梯度下降的计算量较为适中，故收敛速度与参数结果的质量均较为适中
**4、推荐系统中的冷启动都有哪些情况，有哪些常用的解决方法？**
答：（1）推荐系统的冷启动分为三类：a、用户冷启动，针对新用户，如何进行个性化推荐；b、商品冷启动，针对新加入商品，如何向用户进行个性化推荐；c、系统冷启动，针对新开发的平台，如何对用户进行个性化推荐。
（2）对于冷启动的解决方法总体思路就是利用一切能够利用的信息，具体而言有以下几种解决方法：a、提供非个性化的推荐，即分类别推送一些热门商品，而非针对用户偏好；b、利用用户的注册信息，即利用在用户注册过程中提供的年龄、性别等信息进行商品推荐，抑或是在注册过程中让用户选取感兴趣的类别，以此为依据进行商品推荐；c、利用用户在同平台的其他产品内积累的用户信息来进行个性化推荐，例如用微信账号登录某新上线网站，该网站利用微信内的用户信息进行推荐；d、采用专家标注的方法人工对商品进行特征处理，并计算商品的相似度；e、通过给用户推送多商品的组合，根据用户的反馈进一步加强相关商品的推荐权重；f、利用用户/商品的相似度进行推荐
**5、你阅读过和推荐系统，机器学习相关的论文么？有哪些论文是你比较推荐的，可以分享到微信群中**
答：通过这门课程才刚接触到推荐系统以及机器学习的相关论文，故目前涉足的阅读范围仅为课程推荐的相关论文，而且尚处在开始阶段未有充足的积累。目前已经阅读的论文仅包括《Practical Lessons from Predicting Clicks on Ads at Facebook》、《Slope One Predictors for Online Rating-Based Collaborative Filtering》、《Large-scale Parallel Collaborative Filtering for the Netflix Prize》这三篇，后续将继续将课程推荐论文继续补完。