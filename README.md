# Arabic-Dialect-SemiSupervised-LLM-AI-Project-

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arabic Dialect Classification with Synthetic Data and Semi-Supervised Learning</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Arabic Dialect Classification with Synthetic Data and Semi-Supervised Learning</h1>

    <h2>Overview</h2>
    <p>This project investigates the impact of Large Language Model (LLM)-generated synthetic data on Arabic dialect classification, utilizing semi-supervised learning (SSL) techniques to address the challenges posed by the lack of labeled data. We experiment with both real and synthetic data to evaluate their effect on model performance in the classification of Arabic dialects from the MADAR dataset. Our approach demonstrates that synthetic data, in conjunction with SSL, can partially mitigate the lack of labeled data and enhance the performance of dialect classification models in low-resource settings.</p>

    <h2>Abstract</h2>
    <p>The scarcity of labeled data presents significant challenges in training high-performance machine learning models, especially for underrepresented languages like Arabic dialects. To address this, we generated synthetic data using LLMs and applied an SSL approach to effectively utilize unlabeled data. Three main experiments were conducted:</p>
    <ol>
        <li><strong>Real Data + SSL</strong>: Using real data with SSL.</li>
        <li><strong>Real + Synthetic Data + SSL</strong>: Combining real data with synthetic data for SSL.</li>
        <li><strong>Synthetic Data + SSL</strong>: Using only synthetic data for SSL.</li>
    </ol>
    <p>Our results show that semi-supervised models outperform supervised models trained on limited real data, while synthetic data, when used alone, performs within 5.3% of supervised models trained on a small portion of real data. These findings indicate that both SSL and synthetic data hold promise in overcoming data scarcity issues in Arabic dialect classification.</p>

    <h2>Objectives</h2>
    <p>The primary objectives of this project are:</p>
    <ul>
        <li>To address the <strong>data scarcity</strong> issue by generating synthetic data using LLMs.</li>
        <li>To mitigate the <strong>label shortage</strong> problem by leveraging SSL to utilize both labeled and unlabeled data.</li>
        <li>To evaluate the impact of combining synthetic and real data in improving model performance for Arabic dialect classification.</li>
    </ul>

    <h2>Methodology</h2>

    <h3>Data Generation</h3>
    <ul>
        <li><strong>Real Data</strong>: We used the MADAR dataset, which includes samples from various Arabic dialects.</li>
        <li><strong>Synthetic Data</strong>: Synthetic sentences were generated using GPT-4o and GPT-4o-mini models for five dialect categories. These synthetic sentences were then utilized alongside real data to evaluate their impact.</li>
    </ul>

    <h3>Experiments</h3>
    <p>We conducted three primary experiments to assess the effectiveness of synthetic data:</p>
    <ol>
        <li><strong>Real Data + SSL</strong>: Evaluated SSL performance using only real data.</li>
        <li><strong>Real + Synthetic Data + SSL</strong>: Combined real and LLM-generated synthetic data for SSL, with models tested on real data.</li>
        <li><strong>Synthetic Data + SSL</strong>: Tested SSL using only synthetic data to determine its effectiveness as a substitute for real data.</li>
    </ol>

    <h3>Machine Learning Models</h3>
    <p>The models implemented include:</p>
    <ul>
        <li><strong>Stochastic Gradient Descent (SGD) Classifier</strong></li>
        <li><strong>Logistic Regression</strong></li>
        <li><strong>Linear Support Vector Classifier (SVC)</strong></li>
        <li><strong>Passive-Aggressive Classifier</strong></li>
        <li><strong>Multinomial Naive Bayes</strong></li>
    </ul>
    <p>All models were tested under both supervised and self-training settings to evaluate their effectiveness with different combinations of real and synthetic data.</p>

    <h2>Results</h2>
    <p>The findings of our experiments are summarized as follows:</p>
    <ul>
        <li><strong>Self-Training Performance</strong>: Semi-supervised models trained with a mix of real and synthetic data significantly outperformed those trained on only 20% of the real data, showing the value of SSL in low-resource environments.</li>
        <li><strong>Synthetic vs. Real Data</strong>: Models trained solely on synthetic data performed within 5.3% of supervised models trained on 20% real data, indicating that synthetic data can be an effective substitute when real data is limited.</li>
        <li><strong>Dialect-Specific Observations</strong>: Egyptian dialect achieved the highest accuracy, while Gulf dialect presented the most challenges across all models.</li>
    </ul>

    <figure>
        <img src="https://github.com/user-attachments/assets/953ed38a-3d7b-4446-a51f-b1a41eca05f4" alt="Comparison Graph">
        <figcaption>Comparison Graph: Performance differences of average linear classifiers between Real and Generated datasets across dialects.</figcaption>
    </figure>

    <h2>Key Insights</h2>
    <ol>
        <li><strong>Data Scarcity</strong>: Leveraging SSL and synthetic data effectively mitigates the challenges of data scarcity, enabling improved model performance.</li>
        <li><strong>Model Performance</strong>: Real data still outperforms generated data in all metrics, but generated data shows promise, especially when used with SSL.</li>
        <li><strong>Dialect Complexity</strong>: Gulf dialect remains a challenging category, requiring more nuanced methods for accurate classification.</li>
    </ol>

    <h2>How to Run the Code</h2>
    <ol>
        <li><strong>Clone the Repository</strong>:
            <pre><code>git clone https://github.com/SondosBsharat/Arabic-Dialect-SemiSupervised-LLM-AI-Project.git</code></pre>
        </li>
        <li><strong>Set Up the Environment</strong>:
            <p>Install dependencies using the <code>requirements.txt</code> file:</p>
            <pre><code>pip install -r requirements.txt</code></pre>
        </li>
        <li><strong>Data Preparation</strong>:
            <ul>
                <li>Prepare the datasets by following the instructions in <code>data_preparation.md</code>.</li>
                <li>Generate synthetic data using the provided notebook <code>data_generation.ipynb</code>.</li>
            </ul>
        </li>
        <li><strong>Train and Evaluate Models</strong>:
            <ul>
                <li>Use <code>train_model.py</code> to train models and <code>evaluate.py</code> to assess their performance.</li>
            </ul>
        </li>
    </ol>

    <h2>Contributions</h2>
    <ul>
        <li><strong>Sondos Bsharat</strong>: Data extraction and analysis of the MADAR dataset, LLM-generated data analysis, and preprocessing.</li>
        <li><strong>Mena Attia</strong>: Prompt engineering for synthetic data extraction using GPT-4o and GPT-4o-mini.</li>
        <li><strong>Mariam Barakat</strong>: Implementation of the self-training and supervised pipeline, including experimental setups and comparative analysis.</li>
    </ul>

    <h2>Future Work</h2>
    <p>Future research directions include:</p>
    <ul>
        <li><strong>Exploring LLM Variations</strong>: Experimenting with synthetic data generated by other LLMs to evaluate their impact on model performance.</li>
        <li><strong>Benchmark Development</strong>: Creating more comprehensive benchmarks for Arabic dialect classification to evaluate the scalability of SSL with synthetic data.</li>
        <li><strong>Increasing Synthetic Data Volume</strong>: Generating larger synthetic datasets to assess improvements in model accuracy and generalization.</li>
    </ul>

    <h2>License</h2>
    <p>This project is licensed under the MIT License. See the <code>LICENSE</code> file for details.</p>

    <h2>Acknowledgments</h2>
    <p>We extend our gratitude to Mohamed Bin Zayed University of Artificial Intelligence for supporting this research.</p>

    <h2>Contact</h2>
    <p>For questions or collaborations, please contact:</p>
    <ul>
        <li>Sondos Bsharat: <a href="mailto:sondos.bsharat@mbzuai.ac.ae">sondos.bsharat@mbzuai.ac.ae</a></li>
        <li>GitHub Repository: <a href="https://github.com/SondosBsharat/Arabic-Dialect-SemiSupervised-LLM-AI-Project">Arabic-Dialect-SemiSupervised-LLM-AI-Project</a></li>
    </ul>
</body>
</html>

