<<<<<<< HEAD
# data analysis ml v1

###main file: data_analysis_ml-v1.ipynb
###data directory: data (114 csv files)
###README.md (this file)
###Running environment: Jupyter with matplotlib, pandas, numpy, sklearn


<b>Keywords</b>: log analysis, machine learning, behavior analysis, unsupervised learning, supervised learning.

=======
# Log Data Analysis with ML v1.0
Detecting cyber attacks through machine learning is an area that much effort has been put into in research and development. This project analyzed 822,226 log records from a  company's web login page in a 5-hour range. The Python code first clearns and pre-processes the dataset, and then uses a ML algorithm to identify records that are potential attacks. It finally calculates the likelihood based on the suspicious behaviors. 

The project first loads the data into Pandas data frame and removes features in the record that are not of interests in detecting the attacks. Next, data are "compressed" from 822,226 data to 44,514 by combining the records that have the same source and destination IP addresses in the same unit time. The higher the compression rate is, the more duplicate responses in the dataset. This significantly improved the efficiency of the process. Then, unsupervised machine learning is applied to get the detection of the dataset using K-means clustering. The three clusters are: not-suspicious, suspicious, and gray (in-between) area. 

The "cleaned" data is divided into training/testing with the ratio 0.66/0.33 for turther used to analyze the likelihood of each response's abnormal behaviors, and use the previous result as a supervisor for accuracy. The gray area is again using k-mean clustering to separate into 2 clusters, labeled as "more suspicious" and "less suspicious". The "more suspicious" are added into the suspicious_activity dataset. Doing so ensures the machine does not miss any responses that get filtered out from the analysis but still remain an abnormal behavior. The likelihood of the suspicious is calculated based on the percentage over the maximum response in 1 second.

The initial approach of this problem was to use k-mean clustering based on how much time it took to process the response. However, this is not significant due to the delay from each server and the unknown source of the dataset being analyzed. After researching the definition of abnormal behaviors in reality, most of the features are filtered out because they do not have much impact in analyzing attacks. An attack for a general log-in page is defined as multiple visits, responses, callbacks in a short period of time. Thus, pre-processing the data by combining each duplicate response in the same second helps determine the responses' number of visits that stands out.

The 3-2 double-clustering technique helps the machine narrows down the suspicious activities. If k-means clustering is applied only once with 2 clusters, the uncertain groups of the dataset's log records would possibly wrong the result. Therefore, creating a gray area in the middle of two certainties helps to detect the potential attacks that could be missed.
>>>>>>> d77fc8064a2f7eef90e95bb95a92864f8ff2f17c

The main idea is to use unsupervised learning to better understand the distribution of the input data. Supervised learning is then applied to generate predictions. As a result, the algorithm could learn how to predict/cassify on output from new inputs. Reinforment learning (RL) learns from experiences over time. It can be considerd with more data feed into the system. 

The project first loads the input data into a pandas dataframe, then it removes the features that are not of interests to be used in detecting attacks. Next, the data are "compressed" from 800,000+ to around 40,000 by combining the records that have the same source and destination ip addresses in the same unit time. The higher the compression rate, the more the duplications in the dataset. This significantly improved the efficiency of machine learning. Unsupervised machine learning is applied to the dataset using K-means clustering. The output three clusters are labeled not-suspicious, suspicious, and gray (transition) area. 

<<<<<<< HEAD
The pre-processed data are splitted into 0.66/0.33 for training/testing to further analyze the likelihood of each response's abnormal behaviors. Using results (three clusters) from the unsupervised learning as a superviser, the algorithm continues apply supervised machine learning to discover the threats. In addition to areas that are considered "confident" or "no confident", the transition (gray) area is further analyzed using k-mean clustering to seperate into 2 clusters, labeled as "more suspicious" and "less suspicious". The "more suspicious" tags are then added into the suspicious_activity dataset. By doing so it ensures the machine does not miss any respons that get filtered out from the analysis but still remain an abnormal behavior. The likelihood of the suspicious is calculated based on the percentage over the maximum response per second.

=======
<li>Gong, X., Zhou, Y., Bi, Y., He, M., Sheng, S., Qiu, H., He, R., & Lu, J. (2019, October 3). Estimating web attack detection via model uncertainty from inaccurate annotation. IEEE Xplore. https://ieeexplore.ieee.org/abstract/document/8854029. 
    
<br>This article illustrated the potential attacks in log records that are not successfully recorded, which are label as "unknown". This project is aware of the situation from this article. All the unknown log flow records have no source and destination IP address, therefore are all filtered out before creating the Panda dataframe to avoid it reducing the accuracy of the result.</li><br>
<li>Tian, Z., Luo, C., Qiu, J., Du, X., & Guizani, M. (2019, August 30). A distributed deep learning system for web attack detection on edge devices. IEEE Xplore. https://ieeexplore.ieee.org/document/8821336. 

<br>In this article, the author developed a machine learning model using deep learning to detect web attacks by analyzing its URLs. The result has high accuracy. The approach of machine learning was inspired into this project in which the author created a system that solves challenges in the paradigm of the Edge of Things.</li><br>
<li>Géron, A. (2019). Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition. O'Reilly Media, Inc.
<br>
    
The idea of using K-means clustering, sklearn, data split, training, and testing machine learning algorithms to apply to this project is inspired by this book. </li><br>
<li>Torrano-Gimenez, C., Franke, K., Alvarez, G., & Nguyen, H. T. (2012, August 29). Combining expert knowledge with automatic feature extraction for reliable web attack detection. https://onlinelibrary.wiley.com/doi/epdf/10.1002/sec.603. 
<br>
    
This article discussed the feature construction and feature selection of web attack detection. This project applied the idea of omitting the features that are not interested in attack detection. </li><br>
<li>Betarte, G., Pardo, Á., &amp; Martínez, R. (2019, January 17). Web application attacks detection using machine learning techniques. IEEE Xplore. https://ieeexplore.ieee.org/document/8614199. 
<br>
>>>>>>> d77fc8064a2f7eef90e95bb95a92864f8ff2f17c

The 3-2 two-tier clussing technique helps the machine narrows down the suspicious activities. If the k-means clustering is applied only once with 2 clusters, the uncertain groups of dataset would possibly be wrong for the result. Therefore, creating a gray (transition) area in the middle of two certainties helps detecting the potential attacks that could be missed.

The result is saved into result.csv and all detected attacks are saved in the suspicious_activity.csv
