---

# required metadata
title: "Introduction to MicrosoftML"
description: "Learn about the capabilities of MicrosoftML."
keywords: ""
author: "bradsev"
manager: "jhubbard"
ms.date: "12/05/2016"
ms.topic: "get-started-article"
ms.prod: "microsoft-r"
ms.service: ""
ms.assetid: ""

# optional metadata
ROBOTS: ""
audience: ""
ms.devlang: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.technology: "r-server"
ms.custom: ""

---

# Introduction to MicrosoftML

MicrosoftML is a new package for Microsoft R Server that adds state-of-the-art algorithms and data transforms to Microsoft R Server functionality. Microsoft R is a collection of servers and tools that extend the capabilities of R, making it easier and faster to build and deploy R-based solutions. Microsoft R Server brings you the ability to do parallel and chunked data processing that relax the restrictions on dataset size imposed by in-memory open source R. 

MicrosoftML adds algorithms and transforms that are used by product teams across Microsoft. This brings new machine learning functionality with increased speed, performance and scale, especially for handling a large corpus of text data and high-dimensional categorical data.  


## What’s new?

MicrosoftML supports new end-to-end scenarios that include new features and functionality. You can now:
-	Create text classification models for problems such as sentiment analysis and support ticket classification.
-	Train deep neural nets with GPU acceleration in order to solve complex problems such as retail image classification and handwriting analysis.
-	Work with high-dimensional categorical data for scenarios like online advertising click-through prediction.
-	Solve many other common machine learning tasks such as churn prediction, loan risk analysis, and demand forecasting using state-or-the-art, fast and accurate algorithms.

Here are links to Notebooks that contain several tutorials and samples that illustrate how to implement some of the new functionality:

- Fast Linear Algorithm (SDCA) allows you to train 2x faster than logistic regression. [Notebook Link](http://notebookhost.redmond.corp.microsoft.com/notebooks/Tutorials%20and%20Samples/3.%20Samples/FastLinear_Twitter.ipynb)
- GPU acceleration for Neural Nets allows you to train multilayer custom nets on GPUs up to 8x faster. [Notebook Link](http://notebookhost.redmond.corp.microsoft.com/notebooks/Tutorials%20and%20Samples/2.%20Demos/MNIST_GPU.ipynb).
- Feature selection can reduce training time up to 10x while still retaining model accuracy. [Notebook Link](http://notebookhost.redmond.corp.microsoft.com/notebooks/Tutorials%20and%20Samples/2.%20Demos/FeatureSelection_Twitter.ipynb)


## MicrosoftML transforms

The `MicrosoftML` package provides a machine learning transform pipelines that allows you to compose a custom set of transforms that can be applied to your data for featurization before training or testing to facilitate these processes. These include:

- **`concat()`**: creates a single vector-valued column from multiple columns. Combining features of the same type into a vector can significantly speed up training times.
- **`categoricalHash()`**: converts a categorical value into an indicator array using hashing. Useful when the number of categories is large or highly variable
- **`categorical()`**: converts a categorical value into an indicator array using a dictionary. Useful when the number of categories is smaller or fixed.
- **`selectFeatures()`**: selects features from the specified variables using one of the two modes: count or mutual information.
- **`featurizeText()`**: produces a bag of counts of n-grams (sequences of consecutive words) from a given text. It offers language detection, tokenization, stopwords removing, text normalization, feature generation, and term weighting using TF, IDF and TF-IDF.


## MicrosoftML algorithms

The `MicrosoftML` package provides fast and scalable machine learning algorithms that enable you to tackle common machine learning tasks such as classification, regression and anomaly detection. These are high-performance algorithms that are multi-threaded, some of which execute off disk, so that they can scale up to to 100s of GBs on a single-node. These include:

Algorithm | ML task supported | Scalability | Application Examples
--------- | ----------------- | ------------ | -----------
Fast Linear model (SDCA) |  binary classification, linear regression | #cols: ~1B;<br> #rows: ~1B;<br> CPU: multi-proc | Mortgage default prediction, Email spam filtering
OneClass SVM | anomaly detection | cols: ~1K;<br> #rows: RAM-bound;<br> CPU: single-proc | Credit card fraud detection
Fast Tree | binary classification, regression | #cols: ~50K;<br> #rows: RAM-bound;<br> CPU: multi-proc | Bankruptcy prediction
Fast Forest | binary classification, regression | #cols: ~50K;<br> #rows: RAM-bound;<br> CPU: multi-proc | Churn Prediction
Neural Network | binary and multiclass classification, regression | #cols: ~10M;<br> #rows: Inf;<br> CPU: multi-proc CUDA GPU | Check signature recognition, OCR, Click Prediction
Logistic regression | binary and multiclass classification |#cols: ~100M; <br>#rows: Inf for single-proc CPU<br> #rows: RAM-bound for multi-proc CPU| Classifying sentiments from feedback

For more information, see [MicrosoftML functions](microsoftml/microsoftml.md) and the documentation for the individual transforms and functions in the product help.

For guidance when choosing the appropriate machine learning algorithm from the MicrosoftML package, see the [MicrosoftML algorithm cheat sheet](microsoftml-algorithm-cheat-sheet.md).

## Getting started with MicrosoftML

MicrosoftML is currently available in Microsoft R Server on Windows and in the SQL Server 2017 CTP. MicrosoftML functions are provided through the **MicrosoftML** package which is installed in the freely available [Microsoft R Client](r-client.md) and in the commercial product [Microsoft R Server](rserver.md).


## What's next?

[Introduction to Microsoft R](microsoft-r-getting-started.md)

[Diving into data analysis in Microsoft R](data-analysis-in-microsoft-r.md)

[MicrosoftML functions](microsoftml/microsoftml.md) 

[MicrosoftML algorithm cheat sheet](microsoftml-algorithm-cheat-sheet.md)

[Sample code and Data for Microsoft R Server and Microsoft R Client](https://github.com/Microsoft/microsoft-r)