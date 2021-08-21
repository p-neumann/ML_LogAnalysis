# Dr.WangDataAnalysis1
The idea of detecting web attacks through machine learning is not a brand new topic, but an area that still needs better development and research on. 
This project analyzied around 8000000 log flow records from a company in a 5 hour range. After pre-process its data, the machine detected some records being potential attacks and gave its likeihood.

The project first process the data into pandas dataframe, then omit all the features of the record that are not interested in detecting the attacks. 
Next, the data is being compressed from 8000000 datas to around 17000 by combining the records that has the same source and destination ip address in the same unix time. 
This process significantly improved the efficiency of machine learning. 
Then, unsupervised machine learning was applied to give the detection of the dataset using K-means clustering. 
Training/testing the data into 0.66/0.33 to analyze the likeihood of each response being an attacks, and use the previous result as a superviser for accuracy.

The result is saved into result.csv and all detected attacks are saved in attacks.csv

References:

<li>Gong, X., Zhou, Y., Bi, Y., He, M., Sheng, S., Qiu, H., He, R., & Lu, J. (2019, October 3). Estimating web attack detection via model uncertainty from inaccurate annotation. IEEE Xplore. https://ieeexplore.ieee.org/abstract/document/8854029. 
    
<br>This article illustrated the potential attacks in log records that are not successfully recorded, which are label as "unknown". This project is aware of the situation from this article. All the unknown log flow records has no source and destinition ip address, therefore are all filtered out before creating the panda dataframe to avoid it reducing the accuracy of the result.</li><br>
<li>Tian, Z., Luo, C., Qiu, J., Du, X., & Guizani, M. (2019, August 30). A distributed deep learning system for web attack detection on edge devices. IEEE Xplore. https://ieeexplore.ieee.org/document/8821336. 

<br>In this article, the author developed a machine learning model using deep learning to detect web attacks by analyzing its URLs. The result has a high accuracy. The approach of machine learning was inpired into this project in which the arthor created a system that solves challenges in the paradigm of the Edge of Things.</li><br>
<li>Géron, A. (2019). Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition. O'Reilly Media, Inc.
<br>
    
The idea of using K-means clustering, sklearn, data split, training, and testing machine learning algorithms to apply into this project is inspired from this book. </li><br>
<li>Torrano-Gimenez, C., Franke, K., Alvarez, G., & Nguyen, H. T. (2012, August 29). Combining expert knowledge with automatic feature extraction for reliable web attack detection. https://onlinelibrary.wiley.com/doi/epdf/10.1002/sec.603. 
<br>
    
This article discussed the feature construction and feature selection of the web attack detaction. This project applied the idea of omiting the features that are not intertested in attack detection. </li><br>
<li>Betarte, G., Pardo, Á., &amp; Martínez, R. (2019, January 17). Web application attacks detection using machine learning techniques. IEEE Xplore. https://ieeexplore.ieee.org/document/8614199. 
<br>


</li><br>
<li>Abdulraheem, M., &amp; Ibraheem, N. (2019). A DETAILED ANALYSIS OF NEW INTRUSION DETECTION DATASET. http://www.jatit.org/volumes/Vol97No17/4Vol97No17.pdf</li><br>
<li>https://github.com/p-neumann/User-Behavior-Analysis-and-Prediction</li>
