# Awesome-Deep-Learning-Inference

# Top Deep Learning Inference Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Model Optimization, Hardware Acceleration & Production Serving*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Deep Learning Inference**. These tools enable developers to transform trained models into optimized, production-ready artifacts—from graph compilers that fuse operators and quantize weights to runtime engines that execute models efficiently across CPUs, GPUs, and specialized accelerators.

**Examples** include NVIDIA TensorRT, Intel OpenVINO, ONNX Runtime, Apache TVM, TensorFlow Lite, Apple Core ML, Qualcomm QNN, AWS Neuron, Arm NN, and Google MediaPipe (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, cross-platform compilation, and open inference infrastructure—ideal for ML engineers, platform teams, and organizations seeking transparent, vendor-independent model deployment.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **NVIDIA TensorRT (Commercial Support)**
  **SDK for high-performance deep learning inference on NVIDIA GPUs**. The repository contains the **open-source components**—the core builder and runtime are distributed as pre-built binaries with commercial support available. **The reference for NVIDIA GPU inference**—takes an ONNX model, compiles it into a hardware-specific engine, and picks the fastest available GPU kernel for each layer. **Build prerequisites**: TensorRT v10.7.0.23, CUDA 12.6 or 11.8, cuDNN 8.9, Python 3.8–3.10 .

- **Apple Core ML**
  **Apple's framework for on-device inference on iPhone, iPad, and Mac**. **Note**: The compiler and runtime are **closed-source**—you convert models using `coremltools` (open-source Python package) and deploy through Xcode. **The on-device choice** for Apple platforms—optimizes for the Neural Engine (ANE) and GPU. **`coremltools` 9.0** supports converting from TensorFlow, PyTorch, and scikit-learn to the `.mlmodel` format .

- **Qualcomm QNN (Neural Processing SDK)**
  **Qualcomm's SDK for inference on Snapdragon mobile and edge platforms**. **Note**: Proprietary—requires Qualcomm developer account. **The Snapdragon choice** for Android and IoT deployments. **QNN execution provider** enables ONNX Runtime inference on **Hexagon NPUs** in Snapdragon processors with **exceptional power efficiency** for battery-powered devices .

- **AWS Neuron**
  **SDK for inference on AWS Inferentia and Trainium chips**. **Note**: Compiler and runtime are **closed-source**—you use the Neuron SDK to compile models for AWS silicon. **The AWS-specific choice** for cost-optimized inference on Inferentia instances. **NKI Compiler** is open-source (MLIR-based) and provides visibility into the compilation pipeline .

## Open-Source GitHub Projects

- **ONNX Runtime**
  **Cross-platform, high-performance scoring engine for Open Neural Network Exchange (ONNX) models** (MIT) — **the most widely deployed open-source inference runtime** . **Supports CPU, GPU, and specialized execution providers** including **OpenVINO, QNN (Qualcomm), DirectML, TensorRT, and CoreML** . **Microsoft services like Bing, Office, and Azure AI use ONNX Runtime** with an average **2x performance gain on CPU** . **The portability choice**—one model format runs across platforms and hardware. **Best for**: teams wanting **broad hardware support without rewriting models** per platform.

- **Intel OpenVINO**
  **Open Visual Inference and Neural Network Optimization toolkit** (Apache-2.0) — **the Intel hardware choice** . **Optimizes inference across Intel CPUs, integrated GPUs, and VPUs**. **Convert and optimize models from TensorFlow and PyTorch** and deploy across a mix of Intel hardware, on-premise, on-device, in browser, or in cloud . **The trade-off**: vendor-specific optimization—**best performance on Intel, no CUDA dependency**. **Best for**: teams deploying on **Intel hardware** who want **vendor-optimized inference**.

- **NVIDIA TensorRT (Open-Source Components)**
  **High-performance deep learning inference on NVIDIA GPUs** (Apache-2.0 for the open components) — **the open-source parsers, plugins, and samples** that accompany the proprietary TensorRT core . **The TensorRT ecosystem** includes ONNX parsing, plugins, and runtime APIs. **`pytorch/TensorRT`** provides a PyTorch/TorchScript compiler for NVIDIA GPUs using TensorRT . **Best for**: teams already committed to NVIDIA GPUs who want **maximum inference performance**.

- **Apache TVM**
  **Open Machine Learning Compiler Framework** (Apache-2.0) — **the most comprehensive fully open-source DL compiler** . **Python-first development** enables quick customization; **universal deployment** brings models into minimum deployable modules . **Cross-level design** with **TensorIR** for tensor-level representation and **Relax** for graph-level representation—jointly optimizing computational graphs, tensor programs, and libraries . **Targets CPUs, GPUs, and specialized accelerators**. **Best for**: teams wanting **a fully open, hackable compiler stack** that targets diverse hardware without vendor lock-in.

- **TensorFlow Lite**
  **TensorFlow's lightweight solution for mobile and embedded devices** (Apache-2.0) — **the mobile deployment standard**. **Converts TensorFlow models to a compact FlatBuffer format** optimized for on-device inference. **Supports Android, iOS, and embedded Linux** with hardware acceleration via **GPU delegates, NNAPI, and Core ML delegates**. **TensorFlow Lite for Microcontrollers** runs on devices with **only a few kilobytes of memory**—the core runtime fits in **16 KB on an Arm Cortex M3** and requires no OS support .

- **Arm NN**
  **The most performant ML inference engine for Android and Linux** (MIT) — **accelerating ML on Arm Cortex-A CPUs and Arm Mali GPUs** . **Utilizes Arm Compute Library (ACL)** for architecture-specific optimizations (e.g., SVE2). **Arm NN TF Lite Delegate** provides the widest operator support—unsupported operators fall back to reference TF Lite runtime . **Android NN Driver** integrates with NNAPI for automatic acceleration on Arm devices . **Best for**: teams deploying on **Arm-based Android or Linux devices** needing CPU/GPU acceleration.

- **Google MediaPipe**
  **A suite of libraries and tools for applying AI/ML techniques in applications** (Apache-2.0) — **the on-device solution framework** . **MediaPipe Tasks** provides cross-platform APIs for deploying solutions; **MediaPipe Models** provides pre-trained, ready-to-run models . **Available solutions** include face detection, hand landmark detection, pose landmark detection, image segmentation, and object detection across Android, iOS, Web, and Python . **Best for**: teams wanting **ready-to-use on-device ML solutions** for common vision and perception tasks.

### Additional Strong Open-Source Options

- **vLLM** — **High-throughput LLM inference engine** (Apache-2.0) — **the production default for LLM serving**. **PagedAttention** for KV cache management, **continuous batching**, and **OpenAI-compatible API**. **Best for**: serving LLMs at scale on GPU.
- **llama.cpp** — **CPU, GPU, and Metal inference** (MIT) — **the reference for quantized CPU serving**. **Widest model support** and **full control over quantization and threading**. **Best for**: edge, embedded, and CPU-only deployments.
- **Triton Inference Server** — **Cloud inferencing solution optimized for both CPUs and GPUs** (BSD-3-Clause) — **the serving layer**. **Provides HTTP/gRPC endpoints** for any model managed by the server. **Supports TensorRT, PyTorch, ONNX, vLLM, and Python backends**. **Best for**: teams needing **a production serving layer**.
- **OpenVINO Model Server (OVMS)** — **Scalable inference server for models optimized with OpenVINO** (Apache-2.0) — **the Intel serving layer** for deploying OpenVINO-optimized models .
- Community **n8n** workflows for model compilation pipeline automation and inference alerting.

**Frameworks for building custom systems**: Combine **Apache TVM** for cross-hardware compilation with **ONNX Runtime** for portability, **TensorRT** for NVIDIA GPU performance, **OpenVINO** for Intel optimization, **Arm NN** for Arm devices, and **Triton Inference Server** for production serving—creating a comprehensive inference stack that spans development to deployment.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Deep learning inference tools must be evaluated for **hardware target coverage**, **model format support**, **quantization capabilities**, and **licensing** (fully open vs. open components around proprietary cores).
- **The "compiler vs. runtime vs. server" distinction matters.** **Compilers** (TVM, TensorRT, OpenVINO) transform models into optimized executables for specific hardware. **Runtimes** (ONNX Runtime, Arm NN, TensorFlow Lite) execute models. **Servers** (Triton, OVMS) provide HTTP/gRPC endpoints for production serving. **Most production stacks combine all three**.
- **ONNX Runtime is the portability standard.** **Auto EP Selection** simplifies choosing the right execution provider per model. **Microsoft's production services average 2x performance gain on CPU** . **The trade-off**: broad hardware coverage, but **not always the absolute peak performance** that a vendor-specific compiler tuned for one chip can deliver.
- **Vendor-specific compilers deliver peak performance at the cost of lock-in.** **TensorRT** picks the fastest GPU kernel per layer but only runs on NVIDIA GPUs . **OpenVINO** optimizes for Intel hardware . **Core ML** targets Apple silicon exclusively . **Arm NN** optimizes for Arm Cortex-A and Mali . **Choose vendor compilers when you've committed to that hardware**—use TVM or ONNX Runtime when you need to hedge.
- **TensorFlow Lite for Microcontrollers is for the extreme edge.** The core runtime fits in **16 KB** and requires **no operating system or dynamic memory allocation** . **But operator support is limited**—it's for sensor inference, keyword spotting, and simple vision on microcontrollers, not general-purpose model deployment.
- Self-hosted open-source solutions require proper GPU/hardware provisioning, model validation, and ongoing maintenance. **Compiler optimizations can introduce numerical differences**—validate outputs against the reference implementation before production deployment.

---

**Made for ML engineers, platform teams, and organizations building transparent inference solutions.**  
Let's make Deep Learning Inference more open, data-driven, and hardware-aware.
