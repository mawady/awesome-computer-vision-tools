# Awesome Computer Vision Tools

Curated tools for the full CV pipeline — training → inference → deployment → MLOps.  
**Python-first. Production-ready. Actively maintained.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![GitHub last commit](https://img.shields.io/github/last-commit/mawady/awesome-computer-vision-tools)](https://github.com/mawady/awesome-computer-vision-tools)
[![GitHub stars](https://img.shields.io/github/stars/mawady/awesome-computer-vision-tools?style=social)](https://github.com/mawady/awesome-computer-vision-tools)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen)](#contributing)
[![License: CC BY 4.0](https://img.shields.io/badge/license-CC--BY--4.0-blue)](LICENSE)

---

## 🚀 Quick-Start Decision Guide

Not sure where to begin? Use this table to find the right stack for your situation.

| Use Case | Recommended Stack |
|---|---|
| **Just starting out** | PyTorch → AlbumentationsX → WandB → Gradio → HuggingFace Spaces |
| **Research / academia** | PyTorch + JAX → WandB → FiftyOne → HuggingFace Hub |
| **Production API serving** | ONNX Runtime → Triton → BentoML → Docker → Kubernetes |
| **Edge / on-device deployment** | ONNX → TensorRT (NVIDIA) or OpenVINO (Intel) or TFLite (mobile) |
| **Rapid prototyping & demo** | Gradio or Streamlit → HuggingFace Spaces |
| **Enterprise MLOps pipeline** | Airflow or Flyte → MLflow → SageMaker → GitHub Actions |
| **Budget GPU training** | Vast.ai or RunPod → PyTorch → WandB |
| **Apple / iOS deployment** | PyTorch → CoreML → Xcode |

> **Legend for tags used throughout this list:**
> ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) free, source-available &nbsp;|&nbsp; ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) free tier + paid plans &nbsp;|&nbsp; ![paid](https://img.shields.io/badge/paid-red?style=flat) commercial license required &nbsp;|&nbsp; ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) best-in-class for most use cases

---

## Contents

* [Deep Learning Frameworks](#deep-learning-frameworks)
* [Data Augmentation](#data-augmentation-frameworks)
* [Experiment Tracking & Management](#experiment-tracking--management)
* [Workflow Orchestration](#workflow-orchestration)
* [Evaluation & Visualization](#evaluation--visualization)
* [Inference & Model Serving](#inference--model-serving)
* [Edge & Embedded Deployment](#edge--embedded-deployment)
* [Container Management](#container-management)
* [Cloud Computing Providers](#cloud-computing-providers)
* [Cheap GPU Training Providers](#cheap-gpu-training-providers)
* [Storage](#storage)
* [Data Serialization Formats](#data-serialization-formats)
* [Media Quality Formats](#media-quality-formats)
* [API Tools](#api-tools)
* [Application Development](#application-development)
* [Web Hosting Platforms](#web-hosting-platforms)
* [Application Testing](#application-testing)
* [CI/CD](#cicd)
* [Error Monitoring & Logging](#error-monitoring--logging)
* [IDEs & Dev Tools](#ides--dev-tools)
* [Python Environment & Package Managers](#python-environment--package-managers)

---

## Deep Learning Frameworks

> Core frameworks for building and training CV models.

* **PyTorch** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/pytorch/pytorch?style=flat&label=★)](https://github.com/pytorch/pytorch): The dominant research and production framework for deep learning. Strong ecosystem. [[Website](https://pytorch.org)] | [[Github](https://github.com/pytorch/pytorch)]
* **TensorFlow** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/tensorflow/tensorflow?style=flat&label=★)](https://github.com/tensorflow/tensorflow): Google's production-oriented framework. Strong mobile/edge support via TFLite. [[Website](https://www.tensorflow.org)] | [[Github](https://github.com/tensorflow/tensorflow)]
* **Keras** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/keras-team/keras?style=flat&label=★)](https://github.com/keras-team/keras): High-level API that runs on top of TensorFlow, JAX, or PyTorch. Great for rapid prototyping. [[Website](https://keras.io)] | [[Github](https://github.com/keras-team/keras)]
* **JAX** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/google/jax?style=flat&label=★)](https://github.com/google/jax): Google's high-performance numerical computation library with auto-differentiation and XLA acceleration. [[Website](https://jax.readthedocs.io)] | [[Github](https://github.com/google/jax)]
* **Caffe** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat): Early CV-focused framework. [[Website](https://caffe.berkeleyvision.org)] ![discontinued](https://img.shields.io/badge/discontinued-lightgrey?style=flat)
* **Theano** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat): Pioneer automatic differentiation library. [[Github](https://github.com/Theano/Theano)] ![discontinued](https://img.shields.io/badge/discontinued-lightgrey?style=flat)

---

## Data Augmentation Frameworks

> Libraries for augmenting images and annotations during training.

* **AlbumentationsX** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/albumentations-team/AlbumentationsX?style=flat&label=★)](https://github.com/albumentations-team/AlbumentationsX): Fast, flexible augmentation library supporting bounding boxes, masks, and keypoints. Fork of albumentations with active development. [[Github](https://github.com/albumentations-team/AlbumentationsX)]
* **Kornia** ![recommended](https://img.shields.io/badge/★-recommended_for_GPU_pipelines-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/kornia/kornia?style=flat&label=★)](https://github.com/kornia/kornia): Differentiable CV library for PyTorch. Augmentations run on GPU within the training loop. [[Website](https://kornia.readthedocs.io)] | [[Github](https://github.com/kornia/kornia)]
* **torchvision.transforms v2** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/pytorch/vision?style=flat&label=★)](https://github.com/pytorch/vision): Official PyTorch augmentation API with bounding box and mask support. [[Docs](https://pytorch.org/vision/stable/transforms.html)] | [[Github](https://github.com/pytorch/vision)]
* **albumentations** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat): Original library; now archived. [[Github](https://github.com/albumentations-team/albumentations)] ![archived](https://img.shields.io/badge/archived_Jul_2025-lightgrey?style=flat)
* **imgaug** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/aleju/imgaug?style=flat&label=★)](https://github.com/aleju/imgaug): Feature-rich library, no longer actively maintained. [[Github](https://github.com/aleju/imgaug)] ![last active](https://img.shields.io/badge/last_active-Jun_2020-orange?style=flat)
* **Augmentor** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/mdbloice/Augmentor?style=flat&label=★)](https://github.com/mdbloice/Augmentor): Simple pipeline-based augmentation, low maintenance. [[Github](https://github.com/mdbloice/Augmentor)] ![last active](https://img.shields.io/badge/last_active-Mar_2023-orange?style=flat)

---

## Experiment Tracking & Management

> Tools for logging runs, metrics, hyperparameters, and model artifacts.

* **MLflow** ![recommended](https://img.shields.io/badge/★-recommended_for_commercial%2Fself--hosted-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/mlflow/mlflow?style=flat&label=★)](https://github.com/mlflow/mlflow): Open-source platform for experiment tracking, model registry, and deployment. Self-hostable. [[Website](https://mlflow.org)] | [[Github](https://github.com/mlflow/mlflow)]
* **Weights & Biases (WandB)** ![recommended](https://img.shields.io/badge/★-recommended_for_academic_%26_personal-gold?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/wandb/wandb?style=flat&label=★)](https://github.com/wandb/wandb): Rich experiment tracking with dashboards, artifact versioning, and sweep hyperparameter tuning. [[Website](https://wandb.ai)] | [[Github](https://github.com/wandb/wandb)]
* **TrackIO** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/gradio-app/trackio?style=flat&label=★)](https://github.com/gradio-app/trackio): Lightweight WandB-compatible tracker from the Gradio team. Easy drop-in alternative. [[Website](https://huggingface.co/docs/trackio/index)] | [[Github](https://github.com/gradio-app/trackio)]
* **Neptune AI** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/neptune-ai/neptune-client?style=flat&label=★)](https://github.com/neptune-ai/neptune-client): Experiment metadata store with strong team collaboration features. [[Website](https://neptune.ai)] | [[Github](https://github.com/neptune-ai/neptune-client)]
* **ClearML** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/clearml/clearml?style=flat&label=★)](https://github.com/clearml/clearml): Open-source MLOps platform covering experiment tracking, data versioning, and orchestration. [[Website](https://clear.ml)] | [[Github](https://github.com/clearml/clearml)]
* **TensorBoard** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/tensorflow/tensorboard?style=flat&label=★)](https://github.com/tensorflow/tensorboard): TensorFlow's built-in visualisation tool for loss curves, images, histograms, and embeddings. [[Website](https://www.tensorflow.org/tensorboard)] | [[Github](https://github.com/tensorflow/tensorboard)]

---

## Workflow Orchestration

> Tools for scheduling and managing ML pipelines.

* **Airflow** ![recommended](https://img.shields.io/badge/★-recommended_for_enterprise-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/apache/airflow?style=flat&label=★)](https://github.com/apache/airflow): Industry-standard DAG-based workflow scheduler. Large plugin ecosystem. [[Website](https://airflow.apache.org)] | [[Github](https://github.com/apache/airflow)]
* **Prefect** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/PrefectHQ/prefect?style=flat&label=★)](https://github.com/PrefectHQ/prefect): Modern Python-native orchestration with dynamic workflows. [[Website](https://www.prefect.io)] | [[Github](https://github.com/PrefectHQ/prefect)]
* **Dagster** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/dagster-io/dagster?style=flat&label=★)](https://github.com/dagster-io/dagster): Asset-based orchestration with strong observability and data lineage. [[Website](https://dagster.io)] | [[Github](https://github.com/dagster-io/dagster)]
* **Flyte** ![recommended](https://img.shields.io/badge/★-recommended_for_Kubernetes-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/flyteorg/flyte?style=flat&label=★)](https://github.com/flyteorg/flyte): Kubernetes-native typed workflow engine from Lyft. [[Website](https://flyte.org)] | [[Github](https://github.com/flyteorg/flyte)]
* **Metaflow** ![recommended](https://img.shields.io/badge/★-recommended_for_AWS-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/Netflix/metaflow?style=flat&label=★)](https://github.com/Netflix/metaflow): Netflix's framework for human-friendly ML pipelines on AWS. [[Website](https://metaflow.org)] | [[Github](https://github.com/Netflix/metaflow)]
* **Ploomber** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/ploomber/ploomber?style=flat&label=★)](https://github.com/ploomber/ploomber): Notebook-to-pipeline converter. Great for transitioning from Jupyter to production. [[Website](https://docs.ploomber.io)] | [[Github](https://github.com/ploomber/ploomber)]
* **Luigi** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/spotify/luigi?style=flat&label=★)](https://github.com/spotify/luigi): Spotify's lightweight pipeline library. Simple and battle-tested. [[Github](https://github.com/spotify/luigi)]

---

## Evaluation & Visualization

> Tools for measuring model performance and visualising predictions.

* **FiftyOne** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/voxel51/fiftyone?style=flat&label=★)](https://github.com/voxel51/fiftyone): Dataset visualisation and model evaluation platform. Browse predictions, find label errors, compute metrics interactively. [[Website](https://fiftyone.ai)] | [[Github](https://github.com/voxel51/fiftyone)]
* **Supervision** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/roboflow/supervision?style=flat&label=★)](https://github.com/roboflow/supervision): Roboflow's utility library for drawing, filtering, and evaluating object detections with any model. [[Website](https://supervision.roboflow.com)] | [[Github](https://github.com/roboflow/supervision)]
* **TIDE** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/dbolya/tide?style=flat&label=★)](https://github.com/dbolya/tide): Diagnostic tool that breaks down object detection errors by type (classification, localisation, etc.). [[Github](https://github.com/dbolya/tide)] | [[Github](https://github.com/dbolya/tide)]
* **pytorch-grad-cam** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/jacobgil/pytorch-grad-cam?style=flat&label=★)](https://github.com/jacobgil/pytorch-grad-cam): Visualisation of model attention maps using gradient-weighted class activation maps. [[Github](https://github.com/jacobgil/pytorch-grad-cam)] | [[Github](https://github.com/jacobgil/pytorch-grad-cam)]
* **Netron** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/lutzroeder/netron?style=flat&label=★)](https://github.com/lutzroeder/netron): Visual inspector for neural network architectures. Supports ONNX, TF, PyTorch, CoreML. [[Website](https://netron.app)] | [[Github](https://github.com/lutzroeder/netron)]

---

## Inference & Model Serving

> Frameworks for deploying CV models at scale.

* **Triton Inference Server** ![recommended](https://img.shields.io/badge/★-recommended_for_GPU_serving-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/triton-inference-server/server?style=flat&label=★)](https://github.com/triton-inference-server/server): NVIDIA's high-performance model serving platform. Supports TensorRT, ONNX, PyTorch, TensorFlow. [[Github](https://github.com/triton-inference-server/server)]
* **TorchServe** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/pytorch/serve?style=flat&label=★)](https://github.com/pytorch/serve): PyTorch's official model serving library with REST/gRPC and multi-model support. [[Website](https://pytorch.org/serve)] | [[Github](https://github.com/pytorch/serve)]
* **ONNX Runtime** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/microsoft/onnxruntime?style=flat&label=★)](https://github.com/microsoft/onnxruntime): Cross-platform inference engine for ONNX models optimised for CPU and GPU. [[Website](https://onnxruntime.ai)] | [[Github](https://github.com/microsoft/onnxruntime)]
* **BentoML** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/bentoml/BentoML?style=flat&label=★)](https://github.com/bentoml/BentoML): Framework-agnostic model serving with built-in batching, versioning, and containerisation. [[Website](https://bentoml.com)] | [[Github](https://github.com/bentoml/BentoML)]
* **Ray Serve** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/ray-project/ray?style=flat&label=★)](https://github.com/ray-project/ray): Scalable model serving built on Ray with dynamic batching and multi-model pipelines. [[Website](https://docs.ray.io/en/latest/serve)] | [[Github](https://github.com/ray-project/ray)]
* **Seldon Core** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/SeldonIO/seldon-core?style=flat&label=★)](https://github.com/SeldonIO/seldon-core): Kubernetes-native ML serving with A/B testing and drift detection. [[Website](https://www.seldon.io)] | [[Github](https://github.com/SeldonIO/seldon-core)]

---

## Edge & Embedded Deployment

> Tools for optimising and deploying models on-device or at the edge.

* **ONNX** ![recommended](https://img.shields.io/badge/★-recommended_first_step-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/onnx/onnx?style=flat&label=★)](https://github.com/onnx/onnx): Open standard for representing ML models. Export from any framework, run anywhere. [[Website](https://onnx.ai)] | [[Github](https://github.com/onnx/onnx)]
* **TensorRT** ![free](https://img.shields.io/badge/free-brightgreen?style=flat) ![paid](https://img.shields.io/badge/paid-red?style=flat): NVIDIA's inference optimiser. Highest throughput on NVIDIA GPUs. [[Website](https://developer.nvidia.com/tensorrt)]
* **OpenVINO** ![recommended](https://img.shields.io/badge/★-recommended_for_Intel_hardware-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/openvinotoolkit/openvino?style=flat&label=★)](https://github.com/openvinotoolkit/openvino): Intel's toolkit for optimising and deploying on Intel CPUs, iGPUs, and VPUs. [[Website](https://docs.openvino.ai)] | [[Github](https://github.com/openvinotoolkit/openvino)]
* **TensorFlow Lite (TFLite)** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat): Lightweight TF runtime for mobile and embedded devices. [[Website](https://www.tensorflow.org/lite)]
* **CoreML** ![free](https://img.shields.io/badge/free-brightgreen?style=flat): Apple's framework for deploying models on iOS/macOS devices. [[Website](https://developer.apple.com/documentation/coreml)]
* **NCNN** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/Tencent/ncnn?style=flat&label=★)](https://github.com/Tencent/ncnn): Tencent's high-performance inference framework optimised for mobile ARM CPUs. [[Github](https://github.com/Tencent/ncnn)]

---

## Container Management

> Tools for packaging and running containerised workloads.

* **Docker** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): The standard for containerising ML training and inference environments. [[Website](https://www.docker.com)]
* **Kubernetes** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/kubernetes/kubernetes?style=flat&label=★)](https://github.com/kubernetes/kubernetes): Container orchestration for scaling and managing inference services. [[Website](https://kubernetes.io)] | [[Github](https://github.com/kubernetes/kubernetes)]
* **Podman** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/containers/podman?style=flat&label=★)](https://github.com/containers/podman): Daemonless, rootless Docker-compatible container engine. [[Github](https://github.com/containers/podman)] 
* **Buildah** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/containers/buildah?style=flat&label=★)](https://github.com/containers/buildah): Tool for building OCI container images without a daemon. Often paired with Podman. [[Github](https://github.com/containers/buildah)] 
* **Incus** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/lxc/incus?style=flat&label=★)](https://github.com/lxc/incus): Lightweight Linux container and VM manager. [[Github](https://github.com/lxc/incus)] 
* **container** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/apple/container?style=flat&label=★)](https://github.com/apple/container): Apple's lightweight container runtime for macOS. [[Github](https://github.com/apple/container)]

---

## Cloud Computing Providers

> Major cloud platforms for managed GPU training and inference.

* **AWS (SageMaker, EC2)** ![recommended](https://img.shields.io/badge/★-recommended_for_enterprise-gold?style=flat) ![paid](https://img.shields.io/badge/paid-red?style=flat): Broadest service catalog; SageMaker offers managed training, endpoints, and pipelines. [[Website](https://aws.amazon.com)]
* **Google Cloud (Vertex AI, GKE)** ![paid](https://img.shields.io/badge/paid-red?style=flat): Strong TPU access and tight integration with BigQuery and GCS. [[Website](https://cloud.google.com)]
* **Azure (ML Studio, AKS)** ![paid](https://img.shields.io/badge/paid-red?style=flat): Best for Microsoft-heavy enterprises; strong MLOps tooling. [[Website](https://azure.microsoft.com)]

---

## Cheap GPU Training Providers

> Cost-effective alternatives to major cloud providers for GPU compute.

* **Vast.ai** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![paid](https://img.shields.io/badge/paid-red?style=flat): Marketplace for renting consumer and datacenter GPUs at low cost. [[Website](https://vast.ai)]
* **RunPod** ![paid](https://img.shields.io/badge/paid-red?style=flat): On-demand GPU cloud with persistent storage and serverless options. [[Website](https://www.runpod.io)]
* **Lambda Cloud** ![paid](https://img.shields.io/badge/paid-red?style=flat): GPU cloud with straightforward per-hour pricing, popular in the research community. [[Website](https://lambdalabs.com/service/gpu-cloud)]
* **Paperspace (Gradient)** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Notebook-first GPU environment with free tier. [[Website](https://www.paperspace.com)]
* **Google Colab Pro** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Hosted Jupyter notebooks with T4/A100 access. Best for experimentation. [[Website](https://colab.research.google.com/signup)]

---

## Storage

> Databases and storage systems commonly used in CV pipelines.

* **PostgreSQL** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) `SQL`: Robust relational database for metadata, annotations, and job queues. [[Website](https://www.postgresql.org)]
* **MongoDB** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) `NoSQL`: Document store well-suited for variable-length annotation data. [[Website](https://www.mongodb.com)]
* **Redis** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) `In-Memory`: Fast in-memory store for caching predictions, feature vectors, and job queues. [[Website](https://redis.io)]
* **Kafka** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) `Streaming`: Distributed event stream platform for real-time video frame pipelines. [[Website](https://kafka.apache.org)]
* **MySQL** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) `SQL`: Widely used relational database for transactional metadata. [[Website](https://www.mysql.com)]
* **Cassandra** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) `NoSQL`: Distributed NoSQL database for high-write, high-availability use cases. [[Website](https://cassandra.apache.org)]
* **Memcached** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) `In-Memory`: Simple, high-performance distributed memory caching. [[Website](https://memcached.org)]

---

## Data Serialization Formats

> Common file formats and their purpose in CV data pipelines, with supporting libraries.

| Format | Best For | Python Library |
| --- | --- | --- |
| `JSON` | API communication, web apps, config files. | `json` (stdlib), [`orjson`](https://github.com/ijl/orjson) *(fast)* |
| `YAML` | DevOps config (Docker Compose, Kubernetes). | [`PyYAML`](https://github.com/yaml/pyyaml), [`ruamel.yaml`](https://github.com/ruamel/yaml) |
| `CSV` | Simple tabular data; human-readable but slow at scale. | `csv` (stdlib), [`pandas`](https://github.com/pandas-dev/pandas) |
| `XML` | Document storage, legacy web services (SOAP). | `xml.etree` (stdlib), [`lxml`](https://github.com/lxml/lxml) |
| `Parquet` | Columnar storage; fast analytics. Preferred over CSV/NumPy for large datasets. | [`pyarrow`](https://github.com/apache/arrow), [`pandas`](https://github.com/pandas-dev/pandas) |
| `HDF5 / H5Py` | Large scientific arrays and datasets. | [`h5py`](https://github.com/h5py/h5py) |
| `NumPy .npy / .npz` | Fast numerical array storage in Python. | [`numpy`](https://github.com/numpy/numpy) |
| `MessagePack` | Compact binary serialisation; preferred over Pickle for portability. | [`msgpack`](https://github.com/msgpack/msgpack-python) |
| `Parquet (ORC variant)` | Suitable for streaming large data with cross-language support. | [`pyarrow`](https://github.com/apache/arrow) |
| `Pickle` | Python object serialisation; avoid for long-term or cross-language use. | `pickle` (stdlib) ⚠️ *unsafe with untrusted data* |

---


## Media Quality Formats

> Prefer lossless formats in CV pipelines to preserve full fidelity; avoid lossy formats for training data and annotations.

| Format | Media | Quality | Notes |
| --- | --- | --- | --- |
| `JPEG / JPG` | Image | ⚠️ lossy | Most common format; DCT compression introduces blocking artefacts. Avoid for training data and annotations. |
| `HEIF / HEIC` | Image | ⚠️ lossy | Apple default capture format; lossy by default. |
| `PNG` | Image | ✅ lossless | Most common lossless choice for CV datasets. Note: strip alpha channel if only RGB is needed. |
| `WebP` | Image | ✅ lossless (optional lossy) | Smaller than PNG at equivalent quality; good for web-facing pipelines. |
| `TIFF` | Image | ✅ lossless (optional lossy) | Industry standard for scientific and medical imaging. Supports multi-channel and high bit-depth (16/32-bit). |
| `BMP` | Image | ✅ lossless | Uncompressed bitmap; large file sizes. Generally superseded by PNG. |
| `Others (AVIF, PPM/PGM/PBM, SGI, TGA)` | Image | ✅ lossless | AVIF (AV1-based), PPM / PGM / PBM (plain pixel), SGI, TGA (game industry legacy). |
| `Raw (CR2, NEF, ARW)` | Image | ✅ lossless | Proprietary sensor-level formats. Contain unprocessed Bayer data; require demosaicing before use. |
| `DICOM` | Image | ✅ lossless | Medical imaging standard. Encodes pixel data alongside patient and acquisition metadata. |
| `H.264 / AVC` | Video | ⚠️ lossy | Most widely deployed codec. Introduces artefacts; acceptable for preview, not ground truth. |
| `H.265 / HEVC` | Video | ⚠️ lossy | Successor to H.264; ~50% better compression but same lossy caveats. |
| `VP9` | Video | ⚠️ lossy | Google's open codec; common on the web. |
| `AV1` | Video | ⚠️ lossy (near-lossless possible) | Modern open codec; very high quality settings approach lossless. |
| `FFV1` | Video | ✅ lossless | Open lossless codec by FFmpeg. Best choice for archiving raw video frames. |
| `HuffYUV / Lagarith` | Video | ✅ lossless | Fast CPU lossless codecs; larger files than FFV1. |
| `ProRes 4444 / RAW` | Video | ✅ near-lossless | Apple professional codec; ProRes 4444 preserves alpha, ProRes RAW retains sensor data. |
| `Uncompressed (rawvideo)` | Video | ✅ lossless | Frame-by-frame uncompressed. Largest files; preferred for frame-level dataset extraction. |
| `JPEG` | Figure | ⚠️ raster | Avoid for figures: artefacts visible around text and sharp edges. |
| `PNG` | Figure | ⚠️ raster | Best raster choice for figures; lossless, supports transparency, universally supported. |
| `TIFF` | Figure | ⚠️ raster | High-resolution raster export; large file sizes. |
| `SVG` | Figure | ✅ vector | Web-native; ideal for web embedding and editing in Inkscape / Illustrator. |
| `EPS` | Figure | ✅ vector | Legacy PostScript format; still required by some journal submission systems. |
| `PDF` | Figure | ✅ vector | Best all-round choice for scientific figures. Embeds fonts, renders at any zoom, accepted by most journals and LaTeX. *(recommended)* |


---

## API Tools

> Tools for building, testing, and documenting REST APIs for model endpoints.

* **Postman** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Full-featured API development environment with test suites and mocking. [[Website](https://www.postman.com)]
* **Bruno** ![recommended](https://img.shields.io/badge/★-recommended_for_teams-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/usebruno/bruno?style=flat&label=★)](https://github.com/usebruno/bruno): Open-source, Git-friendly API client that stores collections as plain files. [[Github](https://github.com/usebruno/bruno)]
* **Hoppscotch** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/hoppscotch/hoppscotch?style=flat&label=★)](https://github.com/hoppscotch/hoppscotch): Lightweight, open-source Postman alternative that runs in the browser. [[Github](https://github.com/hoppscotch/hoppscotch)] 
* **Insomnia** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/Kong/insomnia?style=flat&label=★)](https://github.com/Kong/insomnia): Clean REST and GraphQL client with environment variable support. [[Github](https://github.com/Kong/insomnia)]
* **Testfully** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Automated API testing with scheduling and monitoring. [[Website](https://testfully.io)]

---

## Application Development

> Frameworks for building interactive ML demos and internal tools.

* **Gradio** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/gradio-app/gradio?style=flat&label=★)](https://github.com/gradio-app/gradio): Build shareable ML demos with a few lines of Python. Hosts natively on HF Spaces. [[Website](https://gradio.app)] | [[Github](https://github.com/gradio-app/gradio)]
* **Streamlit** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/streamlit/streamlit?style=flat&label=★)](https://github.com/streamlit/streamlit): Turn Python scripts into interactive web apps. Great for CV demos and dashboards. [[Website](https://streamlit.io)] | [[Github](https://github.com/streamlit/streamlit)]
* **Dash** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/plotly/dash?style=flat&label=★)](https://github.com/plotly/dash): React-based analytical web app framework from Plotly. [[Website](https://plotly.com/dash)] | [[Github](https://github.com/plotly/dash)]
* **Panel** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/holoviz/panel?style=flat&label=★)](https://github.com/holoviz/panel): Flexible dashboarding for notebooks and scripts. [[Website](https://panel.holoviz.org)] | [[Github](https://github.com/holoviz/panel)]
* **Voila** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/voila-dashboards/voila?style=flat&label=★)](https://github.com/voila-dashboards/voila): Turns Jupyter notebooks into standalone web apps. [[Website](https://voila.readthedocs.io)] | [[Github](https://github.com/voila-dashboards/voila)]

---

## Web Hosting Platforms

> Platforms for hosting CV demos and model APIs publicly.

* **HuggingFace Spaces** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Best place to host Gradio and Streamlit CV demos. Free tier available. [[Website](https://huggingface.co/spaces)]
* **Replicate** ![paid](https://img.shields.io/badge/paid-red?style=flat): Host and run models via API in the cloud. [[Website](https://replicate.com)]
* **Vercel** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Fast frontend hosting for lightweight CV apps. [[Website](https://vercel.com)]
* **Render** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Simple cloud hosting for APIs and web apps. [[Website](https://render.com)]
* **DigitalOcean App Platform** ![paid](https://img.shields.io/badge/paid-red?style=flat): Managed deployment for containerised apps. [[Website](https://www.digitalocean.com)]
* **Heroku** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Easy PaaS for small deployments. [[Website](https://www.heroku.com)]

---

## Application Testing

> Tools for testing web, mobile, and desktop CV applications.


* **Playwright** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/microsoft/playwright?style=flat&label=★)](https://github.com/microsoft/playwright): Reliable end-to-end `web` browser testing from Microsoft. [[Website](https://playwright.dev)] | [[Github](https://github.com/microsoft/playwright)]
* **Appium** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/appium/appium?style=flat&label=★)](https://github.com/appium/appium): Cross-platform `mobile` | `web` | `desktop` UI automation framework. [[Website](http://appium.io)] | [[Github](https://github.com/appium/appium)]
* **Lighthouse** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/GoogleChrome/lighthouse?style=flat&label=★)](https://github.com/GoogleChrome/lighthouse): Automated `web` | `desktop` auditing for performance and accessibility. [[Chrome Extension](https://chromewebstore.google.com/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk)] | [[Github](https://github.com/GoogleChrome/lighthouse)]
* **Maestro** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/mobile-dev-inc/Maestro?style=flat&label=★)](https://github.com/mobile-dev-inc/Maestro): Simple `mobile` | `web` UI testing framework. [[Website](https://www.maestro.dev)] | [[Github](https://github.com/mobile-dev-inc/Maestro)]
* **axe DevTools** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/dequelabs/axe-core?style=flat&label=★)](https://github.com/dequelabs/axe-core): `web` accessibility testing toolkit. [[Chrome Extension](https://chromewebstore.google.com/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd)] | [[Github](https://github.com/dequelabs/axe-core)]
* **WAVE Evaluation Tool** ![free](https://img.shields.io/badge/free-brightgreen?style=flat): Browser-based `web` accessibility evaluation tool. [[Chrome Extension](https://chromewebstore.google.com/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh)] | [[Website](https://wave.webaim.org)]
* **flashlight** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/bamlab/flashlight?style=flat&label=★)](https://github.com/bamlab/flashlight): `mobile` performance auditing tool for mobile apps. [[Website](https://docs.flashlight.dev)] | [[Github](https://github.com/bamlab/flashlight)]

---

## CI/CD

> Tools for automating testing and deployment pipelines.

* **GitHub Actions** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Tightly integrated with GitHub; free for public repos. [[Website](https://github.com/features/actions)]
* **Jenkins** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/jenkinsci/jenkins?style=flat&label=★)](https://github.com/jenkinsci/jenkins): Self-hosted, highly configurable CI/CD server. [[Website](https://www.jenkins.io)] | [[Github](https://github.com/jenkinsci/jenkins)]
* **CircleCI** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Cloud-native CI with strong Docker support. [[Website](https://circleci.com)]
* **Travis CI** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Simple CI for open-source projects. [[Website](https://travis-ci.org)]

---

## Error Monitoring & Logging

> Tools for tracking errors and logs in production CV applications.

* **Sentry** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/getsentry/sentry?style=flat&label=★)](https://github.com/getsentry/sentry): Real-time error tracking and performance monitoring. [[Website](https://sentry.io)] | [[Github](https://github.com/getsentry/sentry)]
* **Loguru** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/Delgan/loguru?style=flat&label=★)](https://github.com/Delgan/loguru): Simplified, structured Python logging. [[Github](https://github.com/Delgan/loguru)]
* **Countly** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) [![Stars](https://img.shields.io/github/stars/Countly/countly-server?style=flat&label=★)](https://github.com/Countly/countly-server): Open-source product analytics and crash reporting. [[Website](https://countly.com)] | [[Github](https://github.com/Countly/countly-server)]
* **stackprinter** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/cknd/stackprinter?style=flat&label=★)](https://github.com/cknd/stackprinter): Prints clean, readable Python stack traces. [[Github](https://github.com/cknd/stackprinter)] | [[Github](https://github.com/cknd/stackprinter)]

---

## IDEs & Dev Tools

> Editors and remote access tools for CV development.

* **VSCode** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![free](https://img.shields.io/badge/free-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/microsoft/vscode?style=flat&label=★)](https://github.com/microsoft/vscode): Most popular editor for Python/ML with a rich extension ecosystem. [[Website](https://code.visualstudio.com)] | [[Github](https://github.com/microsoft/vscode)]
* **Zed** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/zed-industries/zed?style=flat&label=★)](https://github.com/zed-industries/zed): Fast, modern code editor built in Rust. [[Website](https://zed.dev)] | [[Github](https://github.com/zed-industries/zed)]
* **PyCharm** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Full-featured Python IDE from JetBrains. [[Website](https://www.jetbrains.com/pycharm)]
* **Eclipse** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat): Extensible open-source IDE with Python support via PyDev plugin. [[Website](https://www.eclipse.org)]
* **RustDesk** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/rustdesk/rustdesk?style=flat&label=★)](https://github.com/rustdesk/rustdesk): Open-source, self-hostable remote desktop. [[Website](https://rustdesk.com)] | [[Github](https://github.com/rustdesk/rustdesk)]
* **Chrome Remote Desktop** ![free](https://img.shields.io/badge/free-brightgreen?style=flat): Simple browser-based remote access. [[Website](https://remotedesktop.google.com)]
* **AnyDesk** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Fast remote desktop with low latency. [[Website](https://anydesk.com)]
* **TeamViewer** ![freemium](https://img.shields.io/badge/freemium-blue?style=flat): Popular cross-platform remote desktop and support tool. [[Website](https://www.teamviewer.com)]

---

## Python Environment & Package Managers

>  Tools for managing Python versions, dependencies, and virtual environments.

* **uv** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/astral-sh/uv?style=flat&label=★)](https://github.com/astral-sh/uv): Extremely fast Python package and project manager. [[Website](https://docs.astral.sh/uv)] | [[Github](https://github.com/astral-sh/uv)]
* **pipenv** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/pypa/pipenv?style=flat&label=★&cacheSeconds=3600)](https://github.com/pypa/pipenv): Virtualenv and dependency management for Python projects. [[Website](https://pipenv.pypa.io/en/latest/)] | [[Github](https://github.com/pypa/pipenv)]
* **pyenv** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/pyenv/pyenv?style=flat&label=★)](https://github.com/pyenv/pyenv): Simple Python version management: install and switch between multiple Python versions. [[Github](https://github.com/pyenv/pyenv)]
* **Poetry** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/python-poetry/poetry?style=flat&label=★)](https://github.com/python-poetry/poetry): Dependency management with lock files and publishing support. [[Website](https://python-poetry.org)] | [[Github](https://github.com/python-poetry/poetry)]
* **Conda** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/conda/conda?style=flat&label=★)](https://github.com/conda/conda): Environment and package manager with binary package support; widely used in ML. [[Website](https://docs.conda.io/projects/conda/)] | [[Github](https://github.com/conda/conda)]
* **Mamba** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/mamba-org/mamba?style=flat&label=★)](https://github.com/mamba-org/mamba): Fast drop-in replacement for Conda with parallel downloads and a faster solver. [[Github](https://github.com/mamba-org/mamba)]
* **pip** ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) [![Stars](https://img.shields.io/github/stars/pypa/pip?style=flat&label=★)](https://github.com/pypa/pip): The standard Python package installer. [[Website](https://pypi.org)] | [[Github](https://github.com/pypa/pip)]

---

## Contributing

Contributions are very welcome! Please read the [contribution guidelines](CONTRIBUTING.md) before opening a PR.

To add a new tool, open a pull request with:

1. The tool added under the correct category (alphabetically within the category)
2. Format: `**Tool Name** \`license-tag\`: One-sentence description. [[Website](url)] | [[Github](url)] | ![Stars badge]`
3. If a tool is archived or discontinued, mark it with `![discontinued](https://img.shields.io/badge/discontinued-lightgrey?style=flat)` or `![archived](https://img.shields.io/badge/archived-lightgrey?style=flat)`

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Mohamed Elawady](https://github.com/mawady) has waived all copyright and related rights to this work.