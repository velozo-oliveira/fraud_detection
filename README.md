# Detectify - Fraud Prevention
<img src=images/detectify_logo.png width="650" height="250"/>

<p>Detectify is a specialized company in fraud detection. The company is launching the Blocker Fraud service, which ensures the block of fraudulent transactions.</p>

<p>Fraud detection is a set of processes and analyses that allow businesses to identify and prevent unauthorized financial activity. Location intelligence tools can be used to pinpoint suspicious activities and accurately identify their users.</p>

<h2 dir="auto">Business Model</h2>
<p>Detectify&rsquo;s Strategy is based on performance:</p>
<ol>
    <li>
        <p>The company receives 20% of each transaction value truly detected as fraud.</p>
    </li>
    <li>
        <p>The company receives 5% of each transaction value detected as fraud, however the transaction is legitimate.</p>
    </li>
    <li>
        <p>The company gives back 100% of the value for the customer in each transaction detected as legitimate, however the transaction is actually a fraud.</p>
    </li>
</ol>

<h2>Project Goal</h2>
<p>Create a model with high accuracy and precision with respect to transactions&apos; fraud detection.</p>

<h2>Deliverables</h2>
<ul>
    <li>
        <p>A model that classifies the transactions as &quot;Fraud&quot; or &quot;Legitimate&quot;.<br></p>
    </li>
    <li>
        <p>Model performance and results report with respect to profit and loss. The following questions must be answered:<br></p>
        <ul>
            <li>
                <p>What is the model&apos;s precision and accuracy?</p>
            </li>
            <li>
                <p>What is the model&apos;s reliability with respect to transactions&apos; classification as legitimate or fraudulent?</p>
            </li>
            <li>
                <p>What is the company&apos;s forecast revenue if the model classifies 100% of the transactions?</p>
            </li>
            <li>
                <p>What is the company&apos;s forecast loss in case of model&apos;s failure?</p>
            </li>
            <li>
                <p>What is the Blocker Fraud Company forecast profit using the model?</p>
            </li>
        </ul>
    </li>
</ul>


<h2>Dataset</h2>
<p>The dataset used on this project is a synthetic financial dataset generated in a simulator called PaySim and available on<a href="https://www.kaggle.com/datasets/ealaxi/paysim1">&nbsp;kaggle</a>. The PaySim simulator uses aggregated data from private dataset to generate a synthetic dataset that resembles the normal operation of transactions and adds malicious behaviour to later evaluate the performance of fraud detection methods.</p>

<h1>Solution methodology</h1>
<p>The solution was developed based on the CRISP (CRoss-Industry Standard Process for data mining) methodology, which is a cyclical approach that streamlines the delivery of value.</p>
<img src=images/CRISP.png width="400" height="400"/>
<p>Source: <a href="https://commons.wikimedia.org/wiki/File:CRISP-DM_Process_Diagram.png">Wikimedia</a>&nbsp;</p>

<p dir="auto"><strong>Step 01. Data Description:&nbsp;</strong> Use statistical metrics to understand the dataset.Check if there are erroneous/missing data, data types and general information about the data who we will working.</p>

<p dir="auto"><strong>Step 02. Feature engineering:</strong> Obtaining new attributes based on the original variables, in order to better describe the phenomenon to be modeled.</p>

<p dir="auto"><strong>Step 03. Exploratory data analysis:&nbsp;</strong> Observe the statistical distribution of each numerical variable and check for outliers.</p>

<p dir="auto"><strong>Step 04. Data preparation:&nbsp;</strong>After analyzing the data, standard and minmax scalers were applied, in addition to label and ordinal encoders for some categorical features. All details are available on the notebook.</p>

<p dir="auto"><strong>Step 05. Feature selection:&nbsp;</strong>The next step was to identify the most relevant features for training machine learning models. The Boruta algorithm was used.</p>

<p dir="auto"><strong>Step 06. Machine learning modelling</strong>: Three different machine learning algorithms were evaluated and tested: Logistic Regression, Support Vector Machine, and Random Forest.</p>
<p dir="auto">Finally, <strong>precision</strong> and <strong>recall</strong> metrics were used to quantify the performance of the models and to choose the better one.</p>
<ul dir="auto">
    <li><strong>Precision: </strong> From all the transactions classified as fraud, how many were right?  
    - true positives / (true positives + false positives) </li>
    <li><strong>Recall: </strong> From all transactions classified as legitimate, how many were right?        
    - true positives / (true positives + false negatives)</li>
</ul>

<p dir="auto"><strong>Step 07. Business Performance:&nbsp;</strong>Convert model performance to business values</p>

<h2 dir="auto">Machine Learning Performance</h2>
<p> Accuracy isn't everything. When working with highly imbalanced data, accuracy is not a reliable performance metric. Because by doing nothing but just predicting everything is in the maority class, you can obtain a higher accuracy than by building a predictive model.</p>

<table style="width: 100%;">
    <tbody>
        <tr>
            <td style="width: 24.6517%;"><strong>Model</strong><br></td>
            <td style="width: 15.2538%;"><strong>Accuracy</strong><br></td>
            <td style="width: 20.0000%;"><strong>Recall</strong><br></td>
            <td style="width: 20.0000%;"><strong>F1-Score</strong><br></td>
            <td style="width: 20.0000%;"><strong>Precision</strong><br></td>
        </tr>
        <tr>
            <td style="width: 24.6517%;">Logistic Regression<br></td>
            <td style="width: 15.2538%;">0.996<br></td>
            <td style="width: 20.0000%;">0.570<br></td>
            <td style="width: 20.0000%;">0.703<br></td>
            <td style="width: 20.0000%;">0.916<br></td>
        </tr>
        <tr>
            <td style="width: 24.6517%;">Support Vector Machine<br></td>
            <td style="width: 15.2538%;"><br>0.995</td>
            <td style="width: 20.0000%;"><br>0.444</td>
            <td style="width: 20.0000%;"><br>0.613</td>
            <td style="width: 20.0000%;"><br>0.989</td>
        </tr>
        <tr>
            <td style="width: 24.6517%;">Random Forest<br></td>
            <td style="width: 15.2538%;"><br>0.999</td>
            <td style="width: 20.0000%;"><br>0.994</td>
            <td style="width: 20.0000%;"><br>0.997</td>
            <td style="width: 20.0000%;"><br>1.000</td>
        </tr>
    </tbody>
</table>

<h1 dir="auto">Business Results</h1>
<p>Addopting Random Forest as the Machine Learning model, Detectify is able to detect 99.39% of all fraudulent transactions and will pay $2,688,507.92 due to transactions considered legal, but actually fraudulent.<p/>

<p>On the other hand, Detectify will receive $438,086,930.85 due to transactions truly detected as fraud.</p>

<p>For more information please visit the <a href="https://github.com/velozo-oliveira/fraud_detection/blob/main/fraud_detection.ipynb">Jupyter Notebook.</a>&nbsp;</p>

![alt text](https://camo.githubusercontent.com/e922b45bfb79029cf4436e255b0d17b00b651e13b24f1751a9f87b14055fb4b1/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6a7570797465722d2532334641304630302e7376673f7374796c653d666f722d7468652d6261646765266c6f676f3d6a757079746572266c6f676f436f6c6f723d7768697465)


<h1 dir="auto">Conclusion</h1>
<p>From the exploring the dataset, we uncovered patterns that allowed us to construct important features and discard useless ones.</p>

<p>A few popular machine learning algorithms were applied and the method that involved generating multiple decisions trees performed better. </p>

<p>Working with this dataset was a lot of work and a lot of fun. I learned a lot about how to deal with large datasets. The data in this case is mostly inbalanced and intrinsic to the problem. No method was applied to balance the data since some ML lgorithms handle imbalanced data effectively.</p>



<h2 dir="auto">Next Steps</h2>
<p>Following the CRISP methodology, here are some steps that can be taken on the next cycle:</p>
<ul>
<li><span class="VIiyi" lang="en"><span class="JLqJ4b ChMk0b" data-language-for-alternatives="en" data-language-to-translate-into="pt" data-phrase-index="0" data-number-of-phrases="5"><span class="Q4iAWc">Create more attributes from the existing ones, seeking to generate more inputs for learning the models.</span></span></span></li>
<li><span class="VIiyi" lang="en"> <span class="JLqJ4b ChMk0b" data-language-for-alternatives="en" data-language-to-translate-into="pt" data-phrase-index="2" data-number-of-phrases="5"><span class="Q4iAWc">Cross-Validation: consider doing a cross validation. Split the data set into training, validation and test.</span></span> </span></li>
<li><span class="VIiyi" lang="en">Apply <span class="JLqJ4b ChMk0b" data-language-for-alternatives="en" data-language-to-translate-into="pt" data-phrase-index="4" data-number-of-phrases="5"><span class="Q4iAWc">hyperparameter fine tuning, in order to optimize the models.</span></span></span></li>
<li>Deploy the ML model to the cloud. So anyone can send data and receive a prediction of fraud through an API request.</li>
</ul>
