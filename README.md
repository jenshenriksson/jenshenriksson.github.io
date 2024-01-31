## Summary
The past decade has included groundbreaking algorithmic improvements on the back of immense amount of data. For computer vision and perception, the field of deep learning has significantly improved the segmentation and classification performance. However, as automation is increasing, testing and verification of the deep learning models have been seen as a difficult task, due to increased complexity in model development and scenario testing. Both the field of deep learning and safety lack ways of presenting realistic system design and safety case fragments for the usage of deep learning in safety critical applications. 

During the duration of this thesis _Guidance on the Assurance of Machine Learning in Autonomous Systems_ (AMLAS) and _ISO 21448 - Safety Of The Intended Functionality_ (SOTIF) has been researched. Both documents provide a starting ground to validate performance of machine learning based systems in safety automotive applications in a structured manner. However, both are purposely vague with regards to implementation details and testing evaluation metrics. From SOTIF, a key message is to consider a confusion matrix with four states: 1) known safe states, 2) known unsafe states, 3) unknown unsafe states and 4) unknown safe states. This objective share similarities with one studied issue from the deep learning field: handling of uncertain or input samples outside of the scope of the model. The issue stems from the fact that every input sample provides an output prediction, and several sub fields exist to mitigate the impact of undesired inputs e.g. generative models and adversarial training, outlier training and outlier detection. 

This thesis has focused on utilizing the knowledge from the field of outlier detection as a method to estimate uncertainty and as a rejection strategy of predictions when operating on data that are too far from the training domain. The technique has been constructed and tested on several image-based datasets with various difficulty ranging from simple black and white digits to real automotive front looking cameras and shows how a safety measure can be applied to a deep learning function to reduce the risk of misclassifications. The beneficial safety argumentation of this approach is that it provides meta data of confidence to subsequent elements in the system. 
The approach is referred to as _supervisor_,or safety cage, throughout the papers where it has the role to act on incoming data (cf. monitoring in safety design that is incorporated as an observer, but not with an acting role). The supervisor is motivated through the study of nominal performance through AUROC measures (Area on the receiver operating characteristics curve) and risk-versus-coverage metric that allows a user defined accepted risk threshold as a connection to safety requirements. 

### Thesis included papers

1. [*Automotive safety and machine learning: Initial results from a study on how to adapt the ISO 26262 safety standard*](http://mrksbrg.com/wp-content/uploads/preprints/2018_SEFAIAS_ISO26262.pdf), **Jens Henriksson**, Markus Borg, Cristofer Englund. IEEE/ACM International Workshop on Software Engineering for AI in Autonomous Systems (SEFAIAS) 2018  
    <button onclick="toggleAbstract(1)">Show Abstract</button>  
    <p id="abstract1" style="display:none">Machine learning (ML) applications generate a continuous stream of success stories from various domains. ML enables many novel applications, also in safety-critical contexts. However, the functional safety standards such as ISO 26262 did not evolve to cover ML. We conduct an exploratory study on which parts of ISO 26262 represent the most critical gaps between safety engineering and ML development. While this paper only reports the first steps toward a larger research endeavor, we report three adaptations that are critically needed to allow ISO 26262 compliant engineering, and related suggestions on how to evolve the standard.</p>
2. [*Towards Structured Evaluation of Deep Neural Network Supervisors*](https://arxiv.org/pdf/1903.01263.pdf), **Jens Henriksson**, Christian Berger, Markus Borg, Lars Tornberg, Cristofer Englund, Sankar Raman Sathyamoorthy, Stig Ursing. IEEE International Conference On Artificial Intelligence Testing (AITest) 2019  
    <button onclick="toggleAbstract(2)">Show Abstract</button>  
    <p id="abstract2" style="display:none">Deep Neural Networks (DNN) have improved the quality of several non-safety related products in the past years. However, before DNNs should be deployed to safety-critical applications, their robustness needs to be systematically analyzed. A common challenge for DNNs occurs when input is dissimilar to the training set, which might lead to high confidence predictions despite proper knowledge of the input. Several previous studies have proposed to complement DNNs with a supervisor that detects when inputs are outside the scope of the network. Most of these supervisors, however, are developed and tested for a selected scenario using a specific performance metric. In this work, we emphasize the need to assess and compare the performance of supervisors in a structured way. We present a framework constituted by four datasets organized in six test cases combined with seven evaluation metrics. The test cases provide varying complexity and include data from publicly available sources as well as a novel dataset consisting of images from simulated driving scenarios. The latter we plan to make publicly available. Our framework can be used to support DNN supervisor evaluation, which in turn could be used to motive development, validation, and deployment of DNNs in safety-critical applications.</p>
3. [*Performance Analysis of Out-of-Distribution Detection on Trained Neural Networks*](https://arxiv.org/pdf/2204.12378.pdf), **Jens Henriksson**, Christian Berger, Markus Borg, Lars Tornberg, Sankar Raman Sathyamoorthy,  Cristofer Englund. In Journal of Information and Software Technology 2020  
    <button onclick="toggleAbstract(3)">Show Abstract</button>  
    <p id="abstract3" style="display:none">Deep Neural Networks have shown great promise in various fields. However, before deploying these neural networks, the models need to be tested for robustness. One common challenge occurs when the model is exposed to samples outside of the intended operating domain, which can yield outputs with high confidence despite no prior knowledge of the input. **Objective:** The aim of this paper is to investigate how the performance of detecting out-of-distribution samples changes for outlier detection methods, as a deep neural network becomes better on training samples.  **Method:** Our experimental setup defines comparable metrics and datasets that reflect the most common setups in related work. The experimental setup allows for a fair comparison of supervisors, i.e methods with the goal of detecting out-of-distribution samples to a deep neural network. In order to enhance the comparison, four different deep neural networks are compared with three different supervisors during different stages of training, to detect when the performance of the supervisors begins to deteriorate. **Results:** We find that all supervisors has increased outlier detection performance as the quality of the model improves. However, we also find that all supervisors inherit a large variation in performance, which is affected by small variations in the network parameters, as well requiring parameter tuning. We observe that understanding the relationship between training results and supervisor performance is crucial to improve the model's robustness and to indicate, what input samples require further measures to improve the robustness of a DNN. **Conclusion:** Analysing Deep Neural Networks for robustness is a challenging task. We show that small variations in model parameters can have large impact on out-of-distribution detection performance. This kind of model behavior needs to be addressed to allow for safety argumentation of how deep neural networks shall be tested.</p>
4. [*Understanding the Impact of Edge Cases from Occluded Pedestrians for ML Systems*](https://arxiv.org/pdf/2204.12402.pdf), **Jens Henriksson**, Christian Berger, Stig Ursing. In 47th Euromicro Conference on Software Engineering and Advanced Applications 2021  
    <button onclick="toggleAbstract(4)">Show Abstract</button>  
    <p id="abstract4" style="display:none">Machine learning (ML)-enabled approaches are considered a substantial support technique of detection and classification of obstacles of traffic participants in self-driving vehicles. Major breakthroughs have been demonstrated the past few years, even covering complete end-to-end data processing chain from sensory inputs through perception and planning to vehicle control of acceleration, breaking and steering. YOLO (you-only-look-once) is a state-of-the-art perception neural network (NN) architecture providing object detection and classification through bounding box estimations on camera images. As the NN is trained on well annotated images, in this paper we study the variations of confidence levels from the NN when tested on hand-crafted occlusion added to a test set. We compare regular pedestrian detection to upper and lower body detection. Our findings show that the two NN using only partial information perform similarly well like the NN for the full body when the full body NN’s performance is 0.75 or better. Furthermore and as expected, the network, which is only trained on the lower half body is least prone to disturbances from occlusions of the upper half and vice versa.</p>
5. [*Ergo, SMIRK is Safe: A Safety Case for a Machine Learning Component in a Pedestrian Automatic Emergency Brake System*](https://arxiv.org/pdf/2204.07874.pdf), Markus Borg, **Jens Henriksson**, Kasper Socha, Olof Lennartsson, Elias Sonnsjö Lönegren, Thanh Bui, Piotr Tomaszewski, Sankar Raman Sathyamoorthy, Sebastian Brink and Mahshid Helali Moghadam. In Software Quality Journal 2023  
    <button onclick="toggleAbstract(5)">Show Abstract</button>  
    <p id="abstract5" style="display:none">Integration of Machine Learning (ML) components in critical applications introduces novel challenges for software certification and verification. New safety standards and technical guidelines are under development to support the safety of ML-based systems, e.g., ISO~21448 SOTIF for the automotive domain and the Assurance of Machine Learning for use in Autonomous Systems (AMLAS) framework. SOTIF and AMLAS provide high-level guidance but the details must be chiseled out for each specific case. We report results from an industry-academia collaboration on safety assurance of SMIRK, an ML-based pedestrian automatic emergency braking demonstrator running in an industry-grade simulator. We present  the outcome of applying AMLAS on SMIRK for a minimalistic operational design domain, i.e., a complete safety case for its integrated ML-based component. Finally, we report lessons learned and provide both SMIRK and the safety case under an open-source licence for the research community to reuse.</p>
6. [*Ergo, SMIRK is Safe: A Safety Case for a Machine Learning Component in a Pedestrian Automatic Emergency Brake System*](https://arxiv.org/abs/2401.17013), Markus Borg, **Jens Henriksson**, Kasper Socha, Olof Lennartsson, Elias Sonnsjö Lönegren, Thanh Bui, Piotr Tomaszewski, Sankar Raman Sathyamoorthy, Sebastian Brink and Mahshid Helali Moghadam. In Software Quality Journal 2023  
    <button onclick="toggleAbstract(5)">Show Abstract</button>  
    <p id="abstract5" style="display:none">To advance the ability to verify perception deep neural networks (DNNs) for safety critical applications, more safety measures need to be investigated that evaluate the intended performance of DNNs. Due to a lack of verification methods for high-dimensional DNNs, a trade-off is needed between accepted performance and handling of out-of-distribution (OOD) samples. This work evaluates output rejections from semantic segmentation DNNs by applying a Mahalanobis distance (MD) based on the most probable class-conditional Gaussian distribution for the predicted class as an OOD score. The evaluation follows three DNNs trained on the Cityscapes dataset and tested on four automotive datasets and find that classification risk can drastically be reduced at the cost of pixel coverage, even when applied on unseen datasets. The applicability of our findings will support to legitimize and motivate usage of safety measures when arguing for safe usage of DNNs in automotive perception.</p>


<script>
function toggleAbstract(id) {
  var x = document.getElementById("abstract" + id);
  var button = document.querySelector("button[onclick='toggleAbstract(" + id + ")']");
  if (x.style.display === "none") {
    x.style.display = "block";
    button.textContent = "Hide Abstract";
  } else {
    x.style.display = "none";
    button.textContent = "Show Abstract";
  }
}
</script>



### Additional papers
* **\*Best Paper Award\*:** [*Performance Analysis of Out-of-Distribution Detection on Various Trained Neural Networks*](https://ieeexplore.ieee.org/abstract/document/8906748), **Jens Henriksson**, Christian Berger, Markus Borg, Lars Tornberg, Sankar Raman Sathyamoorthy, Cristofer Englund. In 45th Euromicro Conference on Software Engineering and Advanced Applications (SEAA) 2019 

* [*Controlled time series generation for automotive software-in-the-loop testing using GANs*](https://arxiv.org/pdf/2002.06611.pdf), Dhasarathy Parthasarathy, Karl Bäckström, **Jens Henriksson**, Sólrún Einarsdóttir. In IEEE International Conference On Artificial Intelligence Testing (AITest) 2020

* [*On Improving Validity of Deep Neural Networks in Safety Critical Applications*](https://ieeexplore.ieee.org/abstract/document/8906748), **Jens Henriksson**. Thesis for the degree of Licentiate of Engineering 2020. Department of Computer Science and Engineering, Chalmers University of Technology. 

* [SMIRK: A machine learning-based pedestrian automatic emergency braking system with a complete safety case](https://www.sciencedirect.com/science/article/pii/S2665963822000689/pdfft?md5=07caef8ce853a570b9e81747dd2bda5e&pid=1-s2.0-S2665963822000689-main.pdf), Kasper Socha, Markus Borg, **Jens Henriksson**. In Software Impacts Journal, Volume 13, 2022. 

* [On Improving Validity of Deep Neural Networks in Safety Critical Applications](https://research.chalmers.se/publication/517219/file/517219_Fulltext.pdf), **Jens Henriksson**. Thesis for the degree of Licentiate of Engineering, 2020. 

* [*Out-of-Distribution Detection as Support for Autonomous Driving Safety Lifecycle*](https://warg.org/fredrik/publ/refsq2023/OoD_Detection_as_Support_for_AD_Safety_Lifecycle.pdf), **Jens Henriksson**, Stig Ursing, Fredrik Warg, Anders Thorsén, Murat Erdogan, Johan Jaxing Ola Örsmark. In Requirements Engineering: Foundation for Software Quality: 29th International Working Conference, REFSQ 2023.  
     <button onclick="toggleAbstract(7)">Show Abstract</button>  
     <p id="abstract7" style="display:none">[Context and Motivation] The automotive industry is moving towards increased automation, where features such as automated driving systems typically include machine learning (ML), e.g. in the perception system. [Question/Problem] Ensuring safety for systems partly relying on ML is challenging. Different approaches and frameworks have been proposed, typically where the developer must define quantitative and/or qualitative acceptance criteria, and ensure the criteria are fulfilled using different methods to improve e.g., design, robustness and error detection. However, there is still a knowledge gap between quality methods and metrics employed in the ML domain and how such methods can contribute to satisfying the vehicle level safety requirements. [Principal Ideas/Results] In this paper, we argue the need for connecting available ML quality methods and metrics to the safety lifecycle and explicitly show their contribution to safety. In particular, we analyse Out-of-Distribution (OoD) detection, e.g., the frequency of novelty detection, and show its potential for multiple safety-related purposes. I.e., as (a) an acceptance criterion contributing to the decision if the software fulfills the safety requirements and hence is ready-for-release, (b) in operational design domain selection and expansion by including novelty samples into the training/development loop, and (c) as a runtime measure, if there is a sequence of novel samples, the vehicle should consider reaching a minimal risk condition. [Contribution] This paper describes the possibility to use OoD detection as a safety measure, and the potential contributions in different stages of the safety lifecycle.</p>
