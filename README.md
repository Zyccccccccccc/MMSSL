<div align=center>
<h1> 🧪 MixKV: Mixing Importance with Diversity for KV Cache Compression in Large Vision-Language Models </h1>
</div>

## 📌 Highlights

- **🔌 Seamless Integration:** MixKV is a plug-and-play framework that directly enhances existing KV cache compression methods (SnapKV, PyramidKV, AdaKV, SparseMM) without modifying their core architecture—only the scoring function is replaced.
- **📈 Consistent Performance Gains:** MixKV universally improves all baselines across 3 LVLMs and 5 benchmarks. Under extreme compression (budget=64), MixKV boosts baselines by an average of **5.1%**.
- **⚙️ Parameter-Free Adaptation:** The head-wise mixing weight is derived directly from quantified semantic redundancy—no additional hyperparameters or tuning required. High-redundancy heads automatically emphasize diversity while low-redundancy heads prioritize importance.
- **⚡ High Efficiency:** All additional operations (key normalization, mean computation, redundancy quantification, diversity scoring) scale linearly in $O(T \cdot D)$, adding **<1% latency overhead** with zero extra memory footprint.

## 📊 Baselines

We integrate MixKV with the following KV cache compression methods:

| Method | Description | Repository |
|--------|-------------|------------|
| **SnapKV** | Attention-based importance with kernel pooling, uniform budget | [FasterDecoding/SnapKV](https://github.com/FasterDecoding/SnapKV) |
| **PyramidKV** | Layer-wise pyramidal budget allocation | [Zefan-Cai/PyramidKV](https://github.com/Zefan-Cai/PyramidKV) |
| **AdaKV** | Head-wise adaptive budget allocation | [FFY0/AdaKV](https://github.com/FFY0/AdaKV) |
| **SparseMM** | Sparse multimodal KV cache compression | [CR400AF-A/SparseMM](https://github.com/CR400AF-A/SparseMM) |

## 📂 Evaluation Benchmarks

We evaluate on five multi-modal understanding benchmarks:

| Benchmark | Task | Link |
|-----------|------|------|
| **DocVQA** | Document Visual QA | [docvqa.org](https://www.docvqa.org/) |
| **OCRBench** | OCR Evaluation | [Yuliang-Liu/MultimodalOCR](https://github.com/Yuliang-Liu/MultimodalOCR) |
| **TextVQA** | Text-based Visual QA | [textvqa.org](https://textvqa.org/) |
| **ChartQA** | Chart Understanding QA | [vis-nlp/ChartQA](https://github.com/vis-nlp/ChartQA) |
| **TextCaps** | Text-aware Image Captioning | [textvqa.org/textcaps](https://textvqa.org/textcaps/) |

All evaluations are conducted using the [**lmms-eval**](https://github.com/EvolvingLMMs-Lab/lmms-eval) toolkit.

## 🛠 Preparation

1. Clone this repository:
```bash 
cd MixKV
```

2. Create and activate the environment:
```bash
conda create -n mixkv python=3.10 -y
conda activate mixkv
```

3. Install packages:

Compile CUDA code for Flatten Cache Storage. If you encounter a CUDA compile error, please check your [GPU Virtual Architecture](https://docs.nvidia.com/cuda/cuda-compiler-driver-nvcc/index.html#virtual-architecture-feature-list) and [GPU Feature](https://docs.nvidia.com/cuda/cuda-compiler-driver-nvcc/index.html#gpu-feature-list), then change the corresponding compile flag in [csrc/build.py](https://github.com/xuyang-liu16/MixKV/blob/main/csrc/build.py#L20).
```bash
pip install packaging torch==2.5.1
pip uninstall ninja && pip cache purge && pip install ninja --no-cache-dir
cd csrc && make
cd ..
```

Install other packages:
```bash
pip install -e .
pip install flash-attn==2.4.1 --no-build-isolation
pip install qwen-vl-utils
```

4. Install [lmms-eval](https://github.com/EvolvingLMMs-Lab/lmms-eval) for evaluation:

```bash
cd lmms-eval
pip install -e . 
```

## 🚀 Performance Evaluation

<p align="center"> <img src="assets/performance.png" width="1000" align="center"> </p>

To evaluate LLaVA-NeXT-Mistral-7B, InternVL3-8B, and Qwen2-VL-7B:

```bash
bash scripts/eval/mistral.sh
bash scripts/eval/internvl2.sh
bash scripts/eval/qwen.sh
```

Key environment variables:
- `METHOD`: compression method (`snapkv`, `pyramidkv`, `adakv`, `mixsparsemm`)
- `BUDGET`: KV budget per head (`64`, `128`, `256`)
- `SELECT_METHOD`: scoring method (`attn` for baseline, `headwisemixkv` for MixKV)

## ⚡ Efficiency Analysis

<p align="center"> <img src="assets/efficiency.png" width="1000" align="center"> </p>

To evaluate the latency and peak memory under different settings:

```bash
bash scripts/others/speed_and_memory.sh
```

## 📌 Citation

Please consider citing our paper in your publications, if our findings help your research.

```bibtex
@article{liu2025mixkv,
  title={Mixing Importance with Diversity: Joint Optimization for KV Cache Compression in Large Vision-Language Models},
  author={Liu, Xuyang and Gui, Xiyan and Zhang, Yuchao and Zhang, Linfeng},
  journal={arXiv preprint arXiv:2510.20707},
  year={2025}
}
```

## 👍 Acknowledgment

Our codebase is built upon [SparseMM](https://github.com/CR400AF-A/SparseMM) and we extend our gratitude to the open-source efforts. We also thank the developers of [SnapKV](https://github.com/FasterDecoding/SnapKV), [PyramidKV](https://github.com/Zefan-Cai/PyramidKV), [AdaKV](https://github.com/FFY0/AdaKV), and [lmms-eval](https://github.com/EvolvingLMMs-Lab/lmms-eval).
