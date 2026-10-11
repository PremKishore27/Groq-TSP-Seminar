# Groq Tensor Streaming Multiprocessor (TSP)

**A complete overview of Groq's Tensor Streaming Processor and a comparative study with Google's TPU**

Seminar paper and presentation by **Prem Kishore V**
AI Engineering of Autonomous Systems, Technische Hochschule Ingolstadt (THI), Germany

---

## Overview

Deep learning has driven demand for specialised hardware that goes beyond what CPUs and GPUs offer. This project studies the **Groq Tensor Streaming Processor (TSP)**, a processor architecture that rethinks how a chip is organised and how it executes instructions, and compares it with **Google's Tensor Processing Unit (TPU)**, a well-known systolic-array accelerator.

The work was prepared for a scientific seminar at THI.

## Repository Contents

| Path | Description |
|------|-------------|
| [`paper/Groq_Tensor_Streaming_Multiprocessor.pdf`](paper/Groq_Tensor_Streaming_Multiprocessor.pdf) | Seminar paper (IEEE-style, ~6 pages) |
| [`slides/GROQppt1.pptx`](slides/GROQppt1.pptx) | Seminar presentation slides |

## Topics Covered

1. **Groq TSP architecture**: a single large processor whose functional units (INT, FP, MEM, matrix, switch/stream) are organised into vertical **functional slices** instead of a mesh of identical cores
2. **Instruction execution model**: each slice is controlled by its own tailored instruction set, which removes the need for complex decoders and control logic
3. **Memory and data movement**: large on-chip SRAM and a stream-oriented data flow between slices
4. **Deterministic execution**: software-scheduled execution gives predictable latency, simplifies debugging, and helps resist timing side-channel attacks
5. **Potential applications**: real-time AI, LLM inference, autonomous vehicles and robotics, scientific computing, datacenters, and edge/IoT
6. **Challenges**: software ecosystem, programmability and portability, power and thermal management, interconnect scalability, and competition
7. **Comparison with Google TPU**: architecture, performance, scalability, programmability, and ecosystem

## Key Takeaways

| Aspect | Groq TSP | Google TPU |
|--------|----------|------------|
| Design philosophy | Deterministic, software-defined hardware | Domain-specific ASIC for neural networks |
| Core architecture | Functional slicing, stream programming model | Systolic array (256×256 8-bit MAC matrix unit) |
| Execution | Statically scheduled by the compiler | Instructions received from a host CPU over PCIe |
| Memory | Large single-level on-chip SRAM scratchpad | On-chip unified buffer plus accumulators |
| Software ecosystem | Young, built around Groq's own toolchain | Mature, integrated with TensorFlow and other frameworks |

The paper concludes that the TSP's functional slicing and deterministic execution are a promising approach, but that adoption depends on software ecosystem development, programmability, and integration. Head-to-head benchmarking is still needed for a conclusive comparison.

## Main References

- D. Abts et al., *Think Fast: A Tensor Streaming Processor (TSP) for Accelerating Deep Learning Workloads*, ISCA 2020.
- D. Abts et al., *A Software-Defined Tensor Streaming Multiprocessor for Large-Scale Machine Learning*, ISCA 2022.
- D. Abts et al., *The Groq Software-defined Scale-out Tensor Streaming Multiprocessor*, Hot Chips 34, 2022.
- N. Jouppi et al., *In-Datacenter Performance Analysis of a Tensor Processing Unit*, ISCA 2017.

The full reference list is in the paper.

## How to Use

- Read the paper directly on GitHub (click the PDF) or download it.
- Open the `.pptx` slides in PowerPoint, Keynote, or LibreOffice Impress.

## Disclaimer

This is a student seminar project for educational purposes. Performance figures are taken from the cited sources and vendor claims; they are not independently verified. Figures and images belong to their respective owners and are used for academic illustration.

## License

Original text and slides: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) *(change if you prefer another license)*.
Third-party figures and images remain under their original copyright.

## Contact

Prem Kishore V, Technische Hochschule Ingolstadt
GitHub: *[add your profile link]* · LinkedIn: *[optional]*
