# Awesome Computer Vision Tools

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Last Updated](https://img.shields.io/badge/last%20updated-March%202026-brightgreen)
![GitHub stars](https://img.shields.io/github/stars/mawady/awesome-computer-vision-tools?style=social)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-blue.svg)](CONTRIBUTING.md)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

> A curated list of tools covering the full Computer Vision pipeline: from training to inference, deployment, and MLOps.

**Python-first. Production-ready. Actively maintained.**

---

## Contents

- [Deep Learning Frameworks](#deep-learning-frameworks)
- [Data Augmentation](#data-augmentation)
- [Experiment Tracking & Management](#experiment-tracking--management)
- [Workflow Orchestration](#workflow-orchestration)
- [Evaluation & Visualization](#evaluation--visualization)
- [Inference & Model Serving](#inference--model-serving)
- [Edge & Embedded Deployment](#edge--embedded-deployment)
- [Container Management](#container-management)
- [Cloud Computing Providers](#cloud-computing-providers)
- [Cheap GPU Training Providers](#cheap-gpu-training-providers)
- [Storage](#storage)
- [API Tools](#api-tools)
- [Application Development](#application-development)
- [Web Hosting Platforms](#web-hosting-platforms)
- [Application Testing](#application-testing)
- [CI/CD](#cicd)
- [Error Monitoring & Logging](#error-monitoring--logging)
- [IDEs & Dev Tools](#ides--dev-tools)
- [Python Environment & Package Managers](#python-environment--package-managers)
- [Data Formats Reference](#data-formats-reference)

---

## Deep Learning Frameworks


> Core frameworks for building and training CV models.

- **PyTorch**: The dominant research and production framework for deep learning. Strong ecosystem. [[Website](https://pytorch.org)] *(recommended)*
- **TensorFlow**: Google's production-oriented framework. Strong mobile/edge support via TFLite. [[Website](https://www.tensorflow.org)]
- **Keras**: High-level API that runs on top of TensorFlow, JAX, or PyTorch. Great for rapid prototyping. [[Website](https://keras.io)]
- **JAX**: Google's high-performance numerical computation library with auto-differentiation and XLA acceleration. [[Website](https://jax.readthedocs.io)] | [[Github](https://github.com/google/jax)]
- **Caffe**: Early CV-focused framework. [[Website](https://caffe.berkeleyvision.org)] *(discontinued)*
- **Theano**: Pioneer automatic differentiation library. [[Website](https://github.com/Theano/Theano)] *(discontinued)*

---

## Data Augmentation Frameworks

> Libraries for augmenting images and annotations during training.

- **AlbumentationsX** `images & masks`: Fast, flexible augmentation library supporting bounding boxes, masks, and keypoints. Fork of albumentations with active development. [[Github](https://github.com/albumentations-team/AlbumentationsX)] *(recommended)*
- **Kornia** `GPU-native`: Differentiable CV library for PyTorch. Augmentations run on GPU within the training loop. [[Website](https://kornia.readthedocs.io)] | [[Github](https://github.com/kornia/kornia)] *(recommended for GPU pipelines)*
- **torchvision.transforms v2** `PyTorch-native`: Official PyTorch augmentation API with bounding box and mask support. [[Docs](https://pytorch.org/vision/stable/transforms.html)]
- **albumentations**: Original library; now archived. [[Github](https://github.com/albumentations-team/albumentations)] *(archived Jul 2025)*
- **imgaug**: Feature-rich library, no longer actively maintained. [[Github](https://github.com/aleju/imgaug)] *(last active Jun 2020)*
- **Augmentor**: Simple pipeline-based augmentation, low maintenance. [[Github](https://github.com/mdbloice/Augmentor)] *(last active Mar 2023)*

---

## Experiment Tracking & Management


> Tools for logging runs, metrics, hyperparameters, and model artifacts.

- **MLflow**: Open-source platform for experiment tracking, model registry, and deployment. Self-hostable. [[Website](https://mlflow.org)] | [[Github](https://github.com/mlflow/mlflow)] *(recommended for commercial/self-hosted)*
- **Weights & Biases (WandB)**: Rich experiment tracking with dashboards, artifact versioning, and sweep hyperparameter tuning. [[Website](https://wandb.ai)] | [[Github](https://github.com/wandb/wandb)] *(recommended for academic & personal)*
- **TrackIO**: Lightweight WandB-compatible tracker from the Gradio team. Easy drop-in alternative. [[Website](https://huggingface.co/docs/trackio/index)] | [[Github](https://github.com/gradio-app/trackio)]
- **Neptune AI**: Experiment metadata store with strong team collaboration features. [[Website](https://neptune.ai)] | [[Github](https://github.com/neptune-ai/neptune-client)]
- **ClearML**: Open-source MLOps platform covering experiment tracking, data versioning, and orchestration. [[Website](https://clear.ml)] | [[Github](https://github.com/clearml/clearml)]
- **TensorBoard**: TensorFlow's built-in visualisation tool for loss curves, images, histograms, and embeddings. [[Website](https://www.tensorflow.org/tensorboard)] | [[Github](https://github.com/tensorflow/tensorboard)]


---

## Workflow Orchestration

> Tools for scheduling and managing ML pipelines.

- **Airflow**: Industry-standard DAG-based workflow scheduler. Large plugin ecosystem. [[Website](https://airflow.apache.org)] | [[Github](https://github.com/apache/airflow)] *(recommended for enterprise)*
- **Prefect**: Modern Python-native orchestration with dynamic workflows. [[Website](https://www.prefect.io)] | [[Github](https://github.com/PrefectHQ/prefect)]
- **Dagster**: Asset-based orchestration with strong observability and data lineage. [[Website](https://dagster.io)] | [[Github](https://github.com/dagster-io/dagster)]
- **Flyte**: Kubernetes-native typed workflow engine from Lyft. [[Website](https://flyte.org)] | [[Github](https://github.com/flyteorg/flyte)] *(recommended for Kubernetes)*
- **Metaflow**: Netflix's framework for human-friendly ML pipelines on AWS. [[Website](https://metaflow.org)] | [[Github](https://github.com/Netflix/metaflow)] *(recommended for AWS)*
- **Ploomber**: Notebook-to-pipeline converter. Great for transitioning from Jupyter to production. [[Website](https://docs.ploomber.io)] | [[Github](https://github.com/ploomber/ploomber)]
- **Luigi**: Spotify's lightweight pipeline library. Simple and battle-tested. [[Github](https://github.com/spotify/luigi)]

---

## Evaluation & Visualization

> Tools for measuring model performance and visualising predictions.

- **FiftyOne**: Dataset visualisation and model evaluation platform. Browse predictions, find label errors, compute metrics interactively. [[Website](https://fiftyone.ai)] | [[Github](https://github.com/voxel51/fiftyone)] *(recommended)*
- **Supervision**: Roboflow's utility library for drawing, filtering, and evaluating object detections with any model. [[Website](https://supervision.roboflow.com)] | [[Github](https://github.com/roboflow/supervision)] *(recommended)*
- **TIDE**: Diagnostic tool that breaks down object detection errors by type (classification, localisation, etc.). [[Github](https://github.com/dbolya/tide)]
- **pytorch-grad-cam**: Visualisation of model attention maps using gradient-weighted class activation maps. [[Github](https://github.com/jacobgil/pytorch-grad-cam)]
- **Netron**: Visual inspector for neural network architectures. Supports ONNX, TF, PyTorch, CoreML. [[Website](https://netron.app)] | [[Github](https://github.com/lutzroeder/netron)]

---

## Inference & Model Serving

> Frameworks for deploying CV models at scale.

- **Triton Inference Server**: NVIDIA's high-performance model serving platform. Supports TensorRT, ONNX, PyTorch, TensorFlow. [[Github](https://github.com/triton-inference-server/server)] *(recommended for GPU serving)*
- **TorchServe**: PyTorch's official model serving library with REST/gRPC and multi-model support. [[Website](https://pytorch.org/serve)] | [[Github](https://github.com/pytorch/serve)]
- **ONNX Runtime**: Cross-platform inference engine for ONNX models optimised for CPU and GPU. [[Website](https://onnxruntime.ai)] | [[Github](https://github.com/microsoft/onnxruntime)] *(recommended)*
- **BentoML**: Framework-agnostic model serving with built-in batching, versioning, and containerisation. [[Website](https://bentoml.com)] | [[Github](https://github.com/bentoml/BentoML)]
- **Ray Serve**: Scalable model serving built on Ray with dynamic batching and multi-model pipelines. [[Website](https://docs.ray.io/en/latest/serve)] | [[Github](https://github.com/ray-project/ray)]
- **Seldon Core**: Kubernetes-native ML serving with A/B testing and drift detection. [[Website](https://www.seldon.io)] | [[Github](https://github.com/SeldonIO/seldon-core)]

---

## Edge & Embedded Deployment

> Tools for optimising and deploying models on-device or at the edge.

- **ONNX**: Open standard for representing ML models. Export from any framework, run anywhere. [[Website](https://onnx.ai)] | [[Github](https://github.com/onnx/onnx)] *(recommended first step)*
- **TensorRT**: NVIDIA's inference optimiser. Highest throughput on NVIDIA GPUs. [[Website](https://developer.nvidia.com/tensorrt)]
- **OpenVINO**: Intel's toolkit for optimising and deploying on Intel CPUs, iGPUs, and VPUs. [[Website](https://docs.openvino.ai)] | [[Github](https://github.com/openvinotoolkit/openvino)] *(recommended for Intel hardware)*
- **TensorFlow Lite (TFLite)**: Lightweight TF runtime for mobile and embedded devices. [[Website](https://www.tensorflow.org/lite)]
- **CoreML**: Apple's framework for deploying models on iOS/macOS devices. [[Website](https://developer.apple.com/documentation/coreml)]
- **NCNN**: Tencent's high-performance inference framework optimised for mobile ARM CPUs. [[Github](https://github.com/Tencent/ncnn)]


---

## Container Management

> Tools for packaging and running containerised workloads.

- **Docker**: The standard for containerising ML training and inference environments. [[Website](https://www.docker.com)] *(recommended)*
- **Kubernetes**: Container orchestration for scaling and managing inference services. [[Website](https://kubernetes.io)] *(recommended)*
- **Podman**: Daemonless, rootless Docker-compatible container engine. [[Github](https://github.com/containers/podman)]
- **Buildah**: Tool for building OCI container images without a daemon. Often paired with Podman. [[Github](https://github.com/containers/buildah)]
- **Incus**: Lightweight Linux container and VM manager. [[Github](https://github.com/lxc/incus)]
- **container**: Apple's lightweight container runtime for macOS. [[Github](https://github.com/apple/container)]

---

## Cloud Computing Providers

> Major cloud platforms for managed GPU training and inference.

- **AWS (SageMaker, EC2)**: Broadest service catalog; SageMaker offers managed training, endpoints, and pipelines. [[Website](https://aws.amazon.com)] *(recommended for enterprise)*
- **Google Cloud (Vertex AI, GKE)**: Strong TPU access and tight integration with BigQuery and GCS. [[Website](https://cloud.google.com)]
- **Azure (ML Studio, AKS)**: Best for Microsoft-heavy enterprises; strong MLOps tooling. [[Website](https://azure.microsoft.com)]

---

## Cheap GPU Training Providers

> Cost-effective alternatives to major cloud providers for GPU compute.

- **Vast.ai**: Marketplace for renting consumer and datacenter GPUs at low cost. [[Website](https://vast.ai)] *(recommended)*
- **RunPod**: On-demand GPU cloud with persistent storage and serverless options. [[Website](https://www.runpod.io)]
- **Lambda Cloud**: GPU cloud with straightforward per-hour pricing, popular in the research community. [[Website](https://lambdalabs.com/service/gpu-cloud)]
- **Paperspace (Gradient)**: Notebook-first GPU environment with free tier. [[Website](https://www.paperspace.com)]
- **Google Colab Pro**: Hosted Jupyter notebooks with T4/A100 access. Best for experimentation. [[Website](https://colab.research.google.com/signup)]

---

## Storage

> Databases and storage systems commonly used in CV pipelines.

- **PostgreSQL** `SQL`: Robust relational database for metadata, annotations, and job queues. [[Website](https://www.postgresql.org)] *(recommended)*
- **MongoDB** `NoSQL`: Document store well-suited for variable-length annotation data. [[Website](https://www.mongodb.com)] *(recommended)*
- **Redis** `In-Memory`: Fast in-memory store for caching predictions, feature vectors, and job queues. [[Website](https://redis.io)] *(recommended)*
- **Kafka** `Streaming`: Distributed event stream platform for real-time video frame pipelines. [[Website](https://kafka.apache.org)]
- **MySQL** `SQL`: Widely used relational database for transactional metadata. [[Website](https://www.mysql.com)]
- **Cassandra** `NoSQL`: Distributed NoSQL database for high-write, high-availability use cases. [[Website](https://cassandra.apache.org)]
- **Memcached** `In-Memory`: Simple, high-performance distributed memory caching. [[Website](https://memcached.org)]

---

## API Tools


> Tools for building, testing, and documenting REST APIs for model endpoints.

- **Postman**: Full-featured API development environment with test suites and mocking. [[Website](https://www.postman.com)] *(recommended)*
- **Bruno**: Open-source, Git-friendly API client that stores collections as plain files. [[Github](https://github.com/usebruno/bruno)] *(recommended for teams)*
- **Hoppscotch**: Lightweight, open-source Postman alternative that runs in the browser. [[Github](https://github.com/hoppscotch/hoppscotch)]
- **Insomnia**: Clean REST and GraphQL client with environment variable support. [[Github](https://github.com/Kong/insomnia)]
- **Testfully**: Automated API testing with scheduling and monitoring. [[Website](https://testfully.io)]

---

## Application Development

> Frameworks for building interactive ML demos and internal tools.

- **Gradio**: Build shareable ML demos with a few lines of Python. Hosts natively on HF Spaces. [[Website](https://gradio.app)] | [[Github](https://github.com/gradio-app/gradio)] *(recommended)*
- **Streamlit**: Turn Python scripts into interactive web apps. Great for CV demos and dashboards. [[Website](https://streamlit.io)] | [[Github](https://github.com/streamlit/streamlit)] *(recommended)*
- **Dash**: React-based analytical web app framework from Plotly. [[Website](https://plotly.com/dash)] | [[Github](https://github.com/plotly/dash)]
- **Panel**: Flexible dashboarding for notebooks and scripts. [[Website](https://panel.holoviz.org)] | [[Github](https://github.com/holoviz/panel)]
- **Voila**: Turns Jupyter notebooks into standalone web apps. [[Website](https://voila.readthedocs.io)] | [[Github](https://github.com/voila-dashboards/voila)]
- **Autogluon**: AutoML toolkit for training accurate models with minimal code. [[Website](https://auto.gluon.ai)] | [[Github](https://github.com/autogluon/autogluon)]

---

## Web Hosting Platforms

> Platforms for hosting CV demos and model APIs publicly.

- **HuggingFace Spaces**: Best place to host Gradio and Streamlit CV demos. Free tier available. [[Website](https://huggingface.co/spaces)] *(recommended)*
- **Replicate**: Host and run models via API in the cloud. [[Website](https://replicate.com)]
- **Vercel**: Fast frontend hosting for lightweight CV apps. [[Website](https://vercel.com)]
- **Render**: Simple cloud hosting for APIs and web apps. [[Website](https://render.com)]
- **DigitalOcean App Platform**: Managed deployment for containerised apps. [[Website](https://www.digitalocean.com)]
- **Heroku**: Easy PaaS for small deployments. [[Website](https://www.heroku.com)]

---

## Application Testing

> Tools for testing web, mobile, and desktop CV applications.

- **Playwright** `web`: Reliable end-to-end browser testing from Microsoft. [[Website](https://playwright.dev)] | [[Github](https://github.com/microsoft/playwright)] *(recommended)*
- **Appium** `mobile | web | desktop`: Cross-platform UI automation framework. [[Website](http://appium.io)] | [[Github](https://github.com/appium/appium)]
- **Lighthouse** `web | desktop`: Automated auditing for performance and accessibility. [[Chrome Extension](https://chromewebstore.google.com/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk)] | [[Github](https://github.com/GoogleChrome/lighthouse)] *(recommended)*
- **Maestro** `mobile | web`: Simple mobile UI testing framework. [[Website](https://www.maestro.dev)] | [[Github](https://github.com/mobile-dev-inc/Maestro)]
- **axe DevTools** `web`: Accessibility testing toolkit. [[Chrome Extension](https://chromewebstore.google.com/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd)] | [[Github](https://github.com/dequelabs/axe-core)]
- **WAVE Evaluation Tool** `web`: Browser-based web accessibility evaluation tool. [[Chrome Extension](https://chromewebstore.google.com/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh)] | [[Website](https://wave.webaim.org)]
- **flashlight** `mobile`: Performance auditing tool for mobile apps. [[Website](https://docs.flashlight.dev)] | [[Github](https://github.com/bamlab/flashlight)]

---

## CI/CD

> Tools for automating testing and deployment pipelines.

- **GitHub Actions**: Tightly integrated with GitHub; free for public repos. [[Website](https://github.com/features/actions)] *(recommended)*
- **Jenkins**: Self-hosted, highly configurable CI/CD server. [[Website](https://www.jenkins.io)] | [[Github](https://github.com/jenkinsci/jenkins)]
- **CircleCI**: Cloud-native CI with strong Docker support. [[Website](https://circleci.com)]
- **Travis CI**: Simple CI for open-source projects. [[Website](https://travis-ci.org)]

---

## Error Monitoring & Logging
> Tools for tracking errors and logs in production CV applications.

- **Sentry**: Real-time error tracking and performance monitoring. [[Website](https://sentry.io)] | [[Github](https://github.com/getsentry/sentry)] *(recommended)*
- **Loguru**: Simplified, structured Python logging. [[Github](https://github.com/Delgan/loguru)] *(recommended)*
- **Countly**: Open-source product analytics and crash reporting. [[Website](https://countly.com)] | [[Github](https://github.com/Countly/countly-server)]
- **stackprinter**: Prints clean, readable Python stack traces. [[Github](https://github.com/cknd/stackprinter)]


---

## IDEs & Dev Tools

> Editors and remote access tools for CV development.

- **VSCode**: Most popular editor for Python/ML with a rich extension ecosystem. [[Website](https://code.visualstudio.com)] *(recommended)*
- **Zed**: Fast, modern code editor built in Rust. [[Website](https://zed.dev)] | [[Github](https://github.com/zed-industries/zed)] *(recommended)*
- **PyCharm**: Full-featured Python IDE from JetBrains. [[Website](https://www.jetbrains.com/pycharm)]
- **Eclipse**: Extensible open-source IDE with Python support via PyDev plugin. [[Website](https://www.eclipse.org)]
- **RustDesk**: Open-source, self-hostable remote desktop. [[Website](https://rustdesk.com)] | [[Github](https://github.com/rustdesk/rustdesk)] *(recommended)*
- **Chrome Remote Desktop**: Simple browser-based remote access. [[Website](https://remotedesktop.google.com)]
- **AnyDesk**: Fast remote desktop with low latency. [[Website](https://anydesk.com)]
- **TeamViewer**: Popular cross-platform remote desktop and support tool. [[Website](https://www.teamviewer.com)]

---

## Python Environment & Package Managers

> Tools for managing Python versions, dependencies, and virtual environments.

- **uv**: Extremely fast Python package and project manager. [[Website](https://docs.astral.sh/uv)] | [[Github](https://github.com/astral-sh/uv)] *(recommended)*
- **pipenv + pyenv**: Virtualenv and Python version management combo. [[Website-pipenv](https://pipenv.pypa.io/en/latest/)] | [[Github-pipenv](https://github.com/pypa/pipenv)] | [[Github-pyenv](https://github.com/pyenv/pyenv)] *(recommended)*
- **Poetry**: Dependency management with lock files and publishing support. [[Website](https://python-poetry.org)] | [[Github](https://github.com/python-poetry/poetry)]
- **Conda + Mamba**: Environment manager with binary package support; common in ML. [[Website-Conda](https://docs.conda.io/projects/conda/)] | [[Website-mamba](https://mamba.readthedocs.io/)] | [[Github-Conda](https://github.com/conda/conda)] | [[Github-mamba](https://github.com/mamba-org/mamba)]
- **pip**: The standard Python package installer. [[Website](https://pypi.org)] | [[Github](https://github.com/pypa/pip)]

---

## Data Formats Reference

> Common file formats used in CV data pipelines.

| Format | Best For |
|--------|----------|
| `XML` | Document storage, legacy web services (SOAP). |
| `JSON` | API communication, web apps, config files. |
| `YAML` | DevOps config (Docker Compose, Kubernetes). |
| `CSV` | Simple tabular data; human-readable but slow at scale. |
| `Pickle` | Python object serialisation; avoid for long-term or cross-language use. |
| `H5Py / HDF5` | Large scientific arrays and datasets. |
| `NumPy .npy` | Fast numerical array storage in Python. |
| `Optimized Row Columnar (ORC)` | Suitable for streaming large data with cross-language support. |
| `Parquet` | Columnar storage; fast analytics. Preferred over CSV / NumPy for large datasets. |
| `MessagePack` | Compact binary serialisation; preferred over Pickle for portability. |

---

## Contributing

Contributions are very welcome! Please read the [contribution guidelines](CONTRIBUTING.md) before opening a PR.

To add a new tool, open a pull request with:
1. The tool added under the correct category (alphabetically within the category)
2. Format: `**Tool Name**: One-sentence description. [[Website](url)] | [[Github](url)]`
3. If a tool is archived or discontinued, mark it with `*(discontinued)*` or `*(archived)*`

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Mohamed Wady](https://github.com/mawady) has waived all copyright and related rights to this work.
