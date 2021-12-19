---
name: ModelDeployment
topic: Model Deployment with R
maintainer: Yuan Tang
email: terrytangyuan@gmail.com
version: 2021-12-19
---



This CRAN task view contains a list of packages, grouped by topic, that
provides functionalities to streamline the process of deploying models
to various environments, such as mobile devices, edge devices, cloud,
and GPUs, for scoring or inferencing on new data.

Model deployment is often challenging due to various reasons. Some
example challenges are:

-   It involves deploying models on heterogenous environments, e.g. edge
    devices, mobile devices, GPUs, etc.
-   It is hard to compress the model to very small size that could fit
    on devices with limited storage while keeping the same precision and
    minimizing the overhead to load the model for inference.
-   Deployed models sometimes need to process new data records within
    limited memory on small devices.
-   Many deployment environments have bad network connectivity so
    sometimes cloud solutions may not meet the requirements.
-   There's interest in stronger user data privacy paradigms where user
    data does not need to leave the mobile device.
-   There's growing demand to perform on-device model-based data
    filtering before collecting the data.

Many of the areas discussed in this Task View are undergoing rapid
changes in industries and academia. Please send any suggestions to the
[task view maintainer](mailto:terrytangyuan@gmail.com) or submit a pull
request or issue to the [Github repository of this task
view](https://github.com/terrytangyuan/ctv-model-deployment) .

Suggestions and corrections by Achim Zeileis, Dirk Eddelbuettel, and
Kevin Kuo (as well as others I may have forgotten to add here) are
gratefully acknowledged. Thanks to Dirk Eddelbuettel who made the
initial `.ctv` file and the Markdown conversion script available at the
Github repository of CRAN Task View for High Performance Computing
[here](https://github.com/eddelbuettel/ctv-hpc) . Last but not least,
thanks to Dirk Eddelbuettel and Achim Zeileis who helped me get started
on organizing this task view.

### Deployment through Different Types of Artifacts

This section includes packages that provides functionalities to export
the trained model to an artifact that could fit in small devices such as
mobile devices (e.g. Android, iOS) and edge devices (Rasberri Pi). These
packages are built based on different model format.

-   Predictive Model Markup Language (PMML) is an XML-based language
    which provides a way for applications to define statistical and data
    mining models and to share models between PMML compliant
    applications. The following packages are based on PMML:
    -   The `r pkg("pmml")` package provides the main
        interface to PMML.
    -   The `r pkg("pmmlTransformations")` package allows
        for data to be transformed before using it to construct models.
        Builds structures to allow functions in the PMML package to
        output transformation details in addition to the model in the
        resulting PMML file.
    -   The `r pkg("rattle")` package allows to load data
        from a CSV file (or via ODBC), transform and explore the data,
        build and evaluate models, and export models as PMML or as
        scores.
    -   The `r pkg("arules")` package provides the
        infrastructure for representing, manipulating and analyzing
        transaction data and patterns (frequent itemsets and association
        rules). The associations can be written to disk in PMML.
    -   The `r pkg("arulesSequences")` package is an add-on
        for arules to handle and mine frequent sequences.
    -   The `r pkg("arulesCBA")` package provides a function
        to build an association rule-based classifier for data frames,
        and to classify incoming data frames using such a classifier.
-   Plain Old Java Object (POJO) or a Model Object, Optimized (MOJO) are
    intended to be easily embeddable in any Java environment. The only
    compilation and runtime dependency for a generated model is a
    h2o-genmodel.jar file produced as the build output of these
    packages. The `r pkg("h2o")` package provides
    easy-to-use interface to build a wide range of machine learning
    models, such as GLM, DRF, and XGBoost models based on
    `r pkg("xgboost")` package, which can then be exported
    as MOJO and POJO format. The MOJO and POJO artifacts can then be
    loaded by its REST interface as well as different language bindings,
    e.g. Java, Scala, R, and Python.
-   Portable Format for Analytics (PFA) is a specification for
    event-based processors that perform predictive or analytic
    calculations and is aimed at helping smooth the transition from
    statistical model development to large-scale and/or online
    production. PFA combines the ease of portability across systems with
    algorithmic flexibility: models, pre-processing, and post-processing
    are all functions that can be arbitrarily composed, chained, or
    built into complex workflows. The `r pkg("aurelius")`
    package provides tools for converting R objects and syntax into the
    PFA format.
-   [TensorFlow](https://www.tensorflow.org/) 's
    [SavedModel](https://www.tensorflow.org/api_docs/python/tf/saved_model)
    as well as its optimized version [TensorFlow
    Lite](https://www.tensorflow.org/mobile/tflite/) , which uses many
    techniques for achieving low latency such as optimizing the kernels
    for mobile apps, pre-fused activations, and quantized kernels that
    allow smaller and faster (fixed-point math) models. It enables
    on-device machine learning inference with low latency and small
    binary size. The packages listed below can produce models in this
    format. Note that these packages are R wrappers of their
    corresponding Python API based on the
    `r pkg("reticulate")` package. Though Python binary is
    required for creating the models, it's not required during
    inference time for deployment.
    -   The `r pkg("tensorflow")` package provides full
        access to TensorFlow API for numerical computation using data
        flow graphs.
    -   The `r pkg("tfestimators")` package provides
        high-level API to machine learning models as well as highly
        customized neural network architectures.
    -   The `r pkg("keras")` package high-level API to
        construct different types of neural networks.
-   The `r pkg("onnx")` package provides the interface to
    [Open Neural Network Exchange (ONNX)](https://onnx.ai/) which is a
    standard format for models built using different frameworks (e.g.
    TensorFlow, MXNet, PyTorch, CNTK, etc). It defines an extensible
    computation graph model, as well as definitions of built-in
    operators and standard data types. Models trained in one framework
    can be easily transferred to another framework for inference. This
    open source format enables the interoperability between different
    frameworks and streamlining the path from research to production
    will increase the speed of innovation in the AI community. Note that
    this package is based on the `r pkg("reticulate")`
    package to interface with the original Python API so Python binary
    is required for deployment.
-   The `r pkg("xgboost")` and
    `r pkg("lightgbm")` packages can be used to create
    gradient-boosted decision tree (GBDT) models and serialize them to
    text and binary formats which can be used to create predictions with
    other technologies outside of R, including but not limited to
    [Apache Spark](https://spark.apache.org/) ,
    [Dask](https://dask.org/) , and
    [treelite](https://github.com/dmlc/treelite) .

### Deployment through Cloud/Server

Many deployment environments are based on cloud/server. The following
packages provides functionalities to deploy models in those types of
environments:

-   The `r pkg("yhatr")` package allows to deploy, maintain,
    and invoke models via the [Yhat](https://www.yhat.com) REST API.
-   The `r pkg("cloudml")` package provides functionality to
    easily deploy models to [Google Cloud ML
    Engine](https://cloud.google.com/ml-engine/) .
-   The `r pkg("tfdeploy")` package provides functions to
    run a local test server that supports the same REST API as CloudML
    and [RStudio Connect](https://www.rstudio.com/products/connect/) .
-   The `r pkg("domino")` package provides R interface to
    [Domino](https://www.dominodatalab.com/) CLI, a service that makes
    it easy to run your code on scalable hardware, with integrated
    version control and collaboration features designed for analytical
    workflows.
-   The `r pkg("tidypredict")` package provides
    functionalities to run predictions inside database. It's based on
    `r pkg("dplyr")` and `r pkg("dbplyr")` that
    could translate data manipulations written in R to database queries
    that can be used later to execute the data transformations and
    aggregations inside various types of databases.
-   The `r pkg("ibmdbR")` package allows many basic and
    complex R operations to be pushed down into the database, which
    removes the main memory boundary of R and allows to make full use of
    parallel processing in the underlying database.
-   The `r pkg("sparklyr")` package provides bindings to
    [Apache Spark](https://spark.apache.org/) 's distributed machine
    learning library and allows to deploy the trained models to
    clusters. Additionally, the `r pkg("rsparkling")`
    package uses `r pkg("sparklyr")` for Spark job
    deployment while using `r pkg("h2o")` package for
    regular model building.
-   The
    [mrsdeploy](https://docs.microsoft.com/en-us/machine-learning-server/r-reference/mrsdeploy/mrsdeploy-package)
    package provides functions for establishing a remote session in a
    console application and for publishing and managing a web service
    that is backed by the R code block or script you provided.
-   The `r pkg("opencpu")` package provides a server that
    exposes a simple but powerful HTTP API for RPC and data interchange
    with R. This provides a reliable and scalable foundation for
    statistical services or building R web applications.
-   Several general purpose server/client frameworks for R exist that
    could help deploy models in server based environments:
    -   The `r pkg("Rserve")` and
        `r pkg("RSclient")` packages both provide server and
        client functionality for TCP/IP or local socket interfaces to
        enable access to R from many languages and systems.
    -   The `r pkg("httpuv")` package provides a low-level
        socket and protocol support for handling HTTP and WebSocket
        requests directly within R.
-   Several packages offer functionality for turning R code into a web
    API:
    -   The `r pkg("FastRWeb")` package provides some basic
        infrastructure for this.
    -   The `r pkg("plumber")` package allows you to create
        a web API by merely decorating your existing R source code with
        special comments.
    -   The `r pkg("RestRserve")` package is a R web API
        framework for building high-performance microservices and app
        backends based on `r pkg("Rserve")`.



### Links
-   [Github repository of CRAN Task View for High Performance
    Computing](https://github.com/eddelbuettel/ctv-hpc)
-   [GitHub repository for this Task
    View](https://github.com/terrytangyuan/ctv-model-deployment)
