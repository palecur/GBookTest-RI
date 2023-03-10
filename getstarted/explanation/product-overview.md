The Robust Intelligence (RI) Platform secures your machine learning pipeline so you can focus on building better ML models for your business needs.

## The RI Platform

The RI Platform operates at three stages of the ML lifecycle.

During model development, **AI Stress Testing** measures the robustness of your model by running dozens of pre-configured tests, each of which checks the model's vulnerability to a specific form of potential failure in production. After production deployment and before inference, **AI Firewall** protects your model from such critical errors in real-time by flagging or blocking aberrant data from entering your ML system. After inference, **AI Continuous Testing** monitors your model and alerts on issues such as data drift and performance degradation. When things go wrong, it also offers automated root cause analysis of the underlying driver of performance change.

<img src="../_static/rime.png">

## Why use the RI Platform?

In modern engineering organizations, data scientists and machine learning engineers typically spend the majority of their effort on the development stage of the model life cycle, which encompasses data ingestion and cleaning, feature extraction, and model training. During this stage, models are primarily evaluated based on their performance on some clean, held-out test set.

While such metrics might be sufficient for understanding model performance in controlled development environments, deploying models into production introduces a whole new set of challenges and failure modes that are often overlooked. Once a model is deployed, data scientists no longer have complete control over how a model is instantiated, how data is passed into the model, nor do they have any oversight over data pipelines in which the model is integrated. Even when the model is used correctly, the real world can change, and issues like distributional shifts in production data may silently degrade model performance.

## Key Features

The RI Platform addresses these risks with four core products:

### AI Stress Testing
AI Stress Testing is a set of tests that measure the robustness of your ML deployment by computing an aggregate severity score across all tests. The severity score is a measure of the magnitude of the identified failure mode specific to each test. It is a combination of the impact the failure has on model performance (**Performance Change** or **Prediction Change**) and the prevalence of the failure mode in the reference set (**Abnormal Inputs** or **Drift Statistic**). By running hundreds of these unit tests and simulations across both your model and associated reference and evaluation datasets, the RI Platform identifies implicit assumptions and failure modes of the ML deployment.

AI Stress Testing allows you to test your data and model before deployment. We recommend providing a model and labels when running AI Stress Testing to leverage the platform's full potential; however, it is not required. You can run the RI Platform in various modes.

- **Model**: Providing access to the model allows for testing the model behavior under different circumstances. In these tests, we perturb model inputs, provide them to the model, and examine the model behavior to uncover its vulnerabilities.
- **Predictions**: Providing predictions for the data can speed up the RI Platform and allows us to test your model even if you don't provide a model interface. We use sophisticated statistical algorithms to run most of the same tests as when we have direct model access to uncover vulnerabilities within your model and approximate the impact of each vulnerability. If you provide neither a model nor predictions, the RI Platform will still run data quality and data distribution shift tests.
- **Labels**: Providing labels allows for testing model performance under different circumstances. If you do not provide labels, the RI Platform will still run data quality tests, data distribution tests, and prediction distribution tests (if possible).

### AI Firewall
AI Firewall protects your model from bad predictions before model inference. Firewall operates at the data point level. It can flag or block aberrant data points in realtime, and the AI Firewall is automatically configured from the results of stress testing. The end result is that the user gets a custom AI Firewall that protects against the unique forms of model failure to which a given model is susceptible. Firewall can be deployed with a single line of code directly in the inference pipeline of your ML model, wherein it logs, analyzes, and/or acts upon (flag, block, impute) aberrant data points in realtime.

### AI Continuous Testing
AI Continuous Testing enables the user to monitor their ML model after inference. As suggested by the name, this view uses the same Stress Testing framework applied continually across time. Data drift will inevitably occur once a model is deployed in production. Continuous tests help answer both the what and the why of changing data. It not only detects issues as they happen but also alerts you regarding the issues and provides insight into their root causes - shortening the time to resolution. Continuous Testing can be set up by passively logging and analyzing predictions by uploading prediction logs after model inference. These can be automated to run at regular intervals.

### AI Compliance Management
AI Compliance Management allows the user to download auto-generated model cards for internal and external documentation needs. This incorporates results from the AI Stress Testing suite (including a suite of bias and fairness tests) that measure a model???s production readiness. These reports help companies comply with AI regulatory standards.

### Governance Dashboard

A single pane of glass provides visibility into all models in production, providing model health status and the ability to track models to any custom metric. The Governance dashboard is behind a feature flag. Request enabling of this feature directly from Robust Intelligence.

## Key Machine Learning Tasks Covered

### Tabular
- Binary Classification
- Multiclass Classification
- Regression
- Learning to Rank

### Natural Language Processing (NLP)
- Text Classification
- Named Entity Recognition

### Computer Vision (CV)
- Image Classification
- Object Detection

## RI Platform Deployment Patterns
We offer three variations of RI Platform tailored to different deployment patterns. [More information on deployment patterns can be found here](../../installation/index.rst).

|                          | Self-Hosted                 | Managed Cloud         | Cloud                                                                             |
|--------------------------|-----------------------------|-----------------------|-----------------------------------------------------------------------------------|
| **Installation**         | K8s cluster in Customer VPC | K8s cluster in RI VPC | Control Plane K8s cluster in RI VPC <br/> Data Plane K8s cluster in Customer VPC  |
| **Data Location**        | Customer VPC                | RI VPC                | Customer VPC                                                                      |
| **Compute Location**     | Customer VPC                | RI VPC                | Customer VPC                                                                      |
| **Test Result Location** | Customer VPC                | RI VPC                | RI VPC                                                                            |

A lightweight [local installation](../../getstarted/local_trial/index.rst) is available for trial purposes.
