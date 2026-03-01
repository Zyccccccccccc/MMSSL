# MMSSL: Multi-Modal Self-Supervised Learning for Recommendation

PyTorch implementation for WWW 2023 paper [Multi-Modal Self-Supervised Learning for Recommendation](https://arxiv.org/pdf/2302.10632.pdf).

<p align="center">
<img src="./MMSSL.png" alt="MMSSL" />
</p>

MMSSL is a new multimedia recommender system which integrates the generative modality-aware collaborative self-augmentation and the contrastive cross-modality dependency encoding. It achieves better performance than existing SOTA multi-model recommenders.


<h2>Dependencies </h2>

* Python >= 3.9.13
* [Pytorch](https://pytorch.org/) >= 1.13.0+cu116
* [dgl-cuda11.6](https://www.dgl.ai/) >= 0.9.1post1




<h2>Usage </h2>

Start training and inference as:

```
cd MMSSL
python ./main.py --dataset {DATASET}
```
Supported datasets:  `Amazon-Baby`, `Amazon-Sports`, `Tiktok`, `Allrecipes`


<h2> Datasets </h2>

  ```
  ├─ MMSSL/ 
      ├── data/
        ├── tiktok/
        ...
  ```
  |    Dataset   |   |  Amazon  |      |   |          |      |   |  Tiktok  |     |     |   | Allrecipes |    |
|:------------:|:-:|:--------:|:----:|:-:|:--------:|:----:|:-:|:--------:|:---:|:---:|:-:|:----------:|:--:|
|   Modality   |   |     V    |   T  |   |     V    |   T  |   |     V    |  A  |  T  |   |      V     |  T |
|   Embed Dim  |   |   4096   | 1024 |   |   4096   | 1024 |   |    128   | 128 | 768 |   |    2048    | 20 |
|     User     |   |   35598  |      |   |   19445  |      |   |   9319   |     |     |   |    19805   |    |
|     Item     |   |   18357  |      |   |   7050   |      |   |   6710   |     |     |   |    10067   |    |
| Interactions |   |  256308  |      |   |  139110  |      |   |   59541  |     |     |   |    58922   |    |
|   Sparsity   |   | 99.961\% |      |   | 99.899\% |      |   | 99.904\% |     |     |   |  99.970\%  |    |

- `2024.3.20 baselines LLATTICE and MICRO uploaded`: 📢📢📢📢🌹🔥🔥🚀🚀 Because baselines `LATTICE` and `MICRO` require some minor modifications, we provide code that can be easily run by simply modifying the dataset path.
- `2023.11.1 new multi-modal datastes uploaded`: 📢📢🔥🔥🌹🌹🌹🌹 We provide new multi-modal datasets `Netflix` and `MovieLens`  (i.e., CF training data, multi-modal data including `item text` and `posters`) of new multi-modal work [LLMRec](https://github.com/HKUDS/LLMRec) on Google Drive. 🌹We hope to contribute to our community and facilitate your research~

- `2023.3.23 update(all datasets uploaded)`: We provide the processed data at [Google Drive](https://drive.google.com/drive/folders/1AB1RsnU-ETmubJgWLpJrXd8TjaK_eTp0?usp=share_link). 
- `2023.3.24 update`: The official website of the `Tiktok` dataset has been closed. Thus, we also provide many other versions of preprocessed [Tiktok](https://drive.google.com/drive/folders/1hLvoS7F0R_K0HBixuS_OVXw_WbBxnshF?usp=share_link).  We spent a lot of time pre-processing this dataset, so if you want to use our preprocessed Tiktok in your work please cite.

🚀🚀 The provided dataset is compatible with multi-modal recommender models such as [MMSSL](https://github.com/HKUDS/MMSSL), [LATTICE](https://github.com/CRIPAC-DIG/LATTICE), and [MICRO](https://github.com/CRIPAC-DIG/MICRO) and requires no additional data preprocessing, including (1) basic user-item interactions and (2) multi-modal features.


<h3> Multi-modal Datasets </h3>
🌹🌹 Please cite our paper if you use the 'netflix' dataset~ ❤️  

We collected a multi-modal dataset using the original [Netflix Prize Data](https://www.kaggle.com/datasets/netflix-inc/netflix-prize-data) released on the [Kaggle](https://www.kaggle.com/) website. The data format is directly compatible with state-of-the-art multi-modal recommendation models like [LLMRec](https://github.com/HKUDS/LLMRec), [MMSSL](https://github.com/HKUDS/MMSSL), [LATTICE](https://github.com/CRIPAC-DIG/LATTICE), [MICRO](https://github.com/CRIPAC-DIG/MICRO), and others, without requiring any additional data preprocessing.

 `Textual Modality:` We have released the item information curated from the original dataset in the "item_attribute.csv" file. Additionally, we have incorporated textual information enhanced by LLM into the "augmented_item_attribute_agg.csv" file. (The following three images represent (1) information about Netflix as described on the Kaggle website, (2) textual information from the original Netflix Prize Data, and (3) textual information augmented by LLMs.)
<div style="display: flex; justify-content: center; align-items: flex-start;">
  <figure style="text-align: center; margin: 10px;">
   <img src="./image/textual_data1.png" alt="Image 1" style="width:270px;height:180px;">
<!--     <figcaption>Textual data in original 'Netflix Prize Data' on Kaggle.</figcaption> -->
  </figure>

  <figure style="text-align: center; margin: 10px;">
    <img src="./image/textual_data2.png" alt="Image 2" style="width:270px;height:180px;">
<!--     <figcaption>Textual data in original 'Netflix Prize Data'.</figcaption> -->
  </figure>

  <figure style="text-align: center; margin: 10px;">
    <img src="./image/textual_data3.png" alt="Image 2" style="width:270px;height:180px;">
<!--     <figcaption>LLM-augmented textual data.</figcaption> -->
  </figure>  
</div>
 
 `Visual Modality:` We have released the visual information obtained from web crawling in the "Netflix_Posters" folder. (The following image displays the poster acquired by web crawling using item information from the Netflix Prize Data.)
 <div style="display: flex; justify-content: center; align-items: flex-start;">
  <figure style="text-align: center; margin: 10px;">
   <img src="./image/visiual_data1.png" alt="Image 1" style="width:690px;height:590px;">
<!--     <figcaption>Textual data in original 'Netflix Prize Data' on Kaggle.</figcaption> -->
  </figure>
</div>
 

<h3> Original Multi-modal Datasets & Augmented Datasets </h3>
 <div style="display: flex; justify-content: center; align-items: flex-start;">
  <figure style="text-align: center; margin: 10px;">
   <img src="./image/datasets.png" alt="Image 1" style="width:480px;height:270px;">
<!--     <figcaption>Textual data in original 'Netflix Prize Data' on Kaggle.</figcaption> -->
  </figure>
</div>


<br>
<p>

<h3> Download the Netflix dataset. </h3>
🚀🚀
We provide the processed data (i.e., CF training data & basic user-item interactions, original multi-modal data including images and text of items, encoded visual/textual features and LLM-augmented text/embeddings).  🌹 We hope to contribute to our community and facilitate your research 🚀🚀 ~

- `netflix`: [Google Drive Netflix](https://drive.google.com/drive/folders/1BGKm3nO4xzhyi_mpKJWcfxgi3sQ2j_Ec?usp=drive_link).  [🌟(Image&Text)](https://drive.google.com/file/d/1euAnMYD1JBPflx0M86O2M9OsbBSfrzPK/view?usp=drive_link)



<h3> Encoding the Multi-modal Content. </h3>

We use [CLIP-ViT](https://huggingface.co/openai/clip-vit-base-patch32) and [Sentence-BERT](https://www.sbert.net/) separately as encoders for visual side information and textual side information.



<h1> Citing </h1>

If you find this work helpful to your research, please kindly consider citing our paper.


```
@inproceedings{wei2023multi,
  title={Multi-Modal Self-Supervised Learning for Recommendation},
  author={Wei, Wei and Huang, Chao and Xia, Lianghao and Zhang, Chuxu},
  booktitle={Proceedings of the ACM Web Conference 2023},
  pages={790--800},
  year={2023}
}
```
<!-- or -->

<!-- @inproceedings{wei2023multi,
  title={Multi-Modal Self-Supervised Learning for Recommendation},
  author={Wei, Wei and Huang, Chao and Xia, Lianghao and Zhang, Chuxu},
  booktitle={Proceedings of the Web Conference (WWW)},
  year={2023}
}
 -->


## Acknowledgement

The structure of this code is largely based on [LATTICE](https://github.com/CRIPAC-DIG/LATTICE), [MICRO](https://github.com/CRIPAC-DIG/MICRO). Thank them for their work.

adoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ ^C
hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ /usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
W0301 21:31:07.527000 16376 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:31:07.527000 16376 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
WARNING:2026-03-01 21:31:07,540:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-01 21:31:07,576:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-01 21:31:07,623:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
W0301 21:31:09.048000 16388 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:31:09.048000 16388 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:31:09.872000 16383 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:31:09.872000 16383 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:31:11.561000 16376 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:31:11.561000 16376 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:31:43.241000 16396 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:31:43.241000 16396 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
WARNING:2026-03-01 21:31:43,250:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
W0301 21:31:44.540000 16396 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:31:44.540000 16396 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
INFO 03-01 21:31:56 [__init__.py:216] Automatically detected platform cuda.
INFO 03-01 21:31:56 [__init__.py:216] Automatically detected platform cuda.
INFO 03-01 21:31:57 [__init__.py:216] Automatically detected platform cuda.
INFO 03-01 21:32:02 [__init__.py:216] Automatically detected platform cuda.
(EngineCore_DP0 pid=16388) INFO 03-01 21:32:49 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=16388) INFO 03-01 21:32:49 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=16388) INFO 03-01 21:32:52 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     self._init_executor()
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708]     raise ValueError(
(EngineCore_DP0 pid=16388) ERROR 03-01 21:32:52 [core.py:708] ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
(EngineCore_DP0 pid=16388) Process EngineCore_DP0:
(EngineCore_DP0 pid=16388) Traceback (most recent call last):
(EngineCore_DP0 pid=16388)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=16388)     self.run()
(EngineCore_DP0 pid=16388)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=16388)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=16388)     raise e
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16388)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16388)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16388)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16388)     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16388)                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16388)     self._init_executor()
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16388)     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16388)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16388)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16388)     return func(*args, **kwargs)
(EngineCore_DP0 pid=16388)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16388)     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16388)     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16388)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16388)     raise ValueError(
(EngineCore_DP0 pid=16388) ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
[rank0]:[W301 21:32:53.859304297 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
Traceback (most recent call last):
  File "<frozen runpy>", line 198, in _run_module_as_main
  File "<frozen runpy>", line 88, in _run_code
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
    initialize_model()
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
    model = vllm.LLM(
            ^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/llm.py", line 297, in __init__
    self.llm_engine = LLMEngine.from_engine_args(
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 177, in from_engine_args
    return cls(vllm_config=vllm_config,
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 114, in __init__
    self.engine_core = EngineCoreClient.make_client(
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 80, in make_client
    return SyncMPClient(vllm_config, executor_class, log_stats)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 602, in __init__
    super().__init__(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 448, in __init__
    with launch_core_engines(vllm_config, executor_class,
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/contextlib.py", line 144, in __exit__
    next(self.gen)
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 732, in launch_core_engines
    wait_for_engine_startup(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 785, in wait_for_engine_startup
    raise RuntimeError("Engine core initialization failed. "
RuntimeError: Engine core initialization failed. See root cause above. Failed core proc(s): {}
[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
(EngineCore_DP0 pid=16383) INFO 03-01 21:33:01 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=16383) INFO 03-01 21:33:02 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=16383) INFO 03-01 21:33:03 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     self._init_executor()
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708]     raise ValueError(
(EngineCore_DP0 pid=16383) ERROR 03-01 21:33:04 [core.py:708] ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
(EngineCore_DP0 pid=16383) Process EngineCore_DP0:
(EngineCore_DP0 pid=16383) Traceback (most recent call last):
(EngineCore_DP0 pid=16383)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=16383)     self.run()
(EngineCore_DP0 pid=16383)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=16383)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=16383)     raise e
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16383)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16383)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16383)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16383)     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16383)                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16383)     self._init_executor()
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16383)     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16383)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16383)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16383)     return func(*args, **kwargs)
(EngineCore_DP0 pid=16383)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16383)     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16383)     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16383)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16383)     raise ValueError(
(EngineCore_DP0 pid=16383) ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
[rank0]:[W301 21:33:04.753969599 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
Traceback (most recent call last):
  File "<frozen runpy>", line 198, in _run_module_as_main
  File "<frozen runpy>", line 88, in _run_code
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
    initialize_model()
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
    model = vllm.LLM(
            ^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/llm.py", line 297, in __init__
    self.llm_engine = LLMEngine.from_engine_args(
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 177, in from_engine_args
    return cls(vllm_config=vllm_config,
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 114, in __init__
    self.engine_core = EngineCoreClient.make_client(
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 80, in make_client
    return SyncMPClient(vllm_config, executor_class, log_stats)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 602, in __init__
    super().__init__(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 448, in __init__
    with launch_core_engines(vllm_config, executor_class,
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/contextlib.py", line 144, in __exit__
    next(self.gen)
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 732, in launch_core_engines
    wait_for_engine_startup(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 785, in wait_for_engine_startup
    raise RuntimeError("Engine core initialization failed. "
RuntimeError: Engine core initialization failed. See root cause above. Failed core proc(s): {}
(EngineCore_DP0 pid=16376) INFO 03-01 21:33:06 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=16376) INFO 03-01 21:33:06 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=16376) INFO 03-01 21:33:09 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     self._init_executor()
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708]     raise ValueError(
(EngineCore_DP0 pid=16376) ERROR 03-01 21:33:09 [core.py:708] ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
(EngineCore_DP0 pid=16376) Process EngineCore_DP0:
(EngineCore_DP0 pid=16376) Traceback (most recent call last):
(EngineCore_DP0 pid=16376)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=16376)     self.run()
(EngineCore_DP0 pid=16376)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=16376)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=16376)     raise e
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16376)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16376)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16376)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16376)     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16376)                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16376)     self._init_executor()
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16376)     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16376)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16376)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16376)     return func(*args, **kwargs)
(EngineCore_DP0 pid=16376)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16376)     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16376)     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16376)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16376)     raise ValueError(
(EngineCore_DP0 pid=16376) ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
[rank0]:[W301 21:33:10.319243835 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
(EngineCore_DP0 pid=16396) INFO 03-01 21:33:10 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=16396) INFO 03-01 21:33:10 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
Traceback (most recent call last):
  File "<frozen runpy>", line 198, in _run_module_as_main
  File "<frozen runpy>", line 88, in _run_code
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
    initialize_model()
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
    model = vllm.LLM(
            ^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/llm.py", line 297, in __init__
    self.llm_engine = LLMEngine.from_engine_args(
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 177, in from_engine_args
    return cls(vllm_config=vllm_config,
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 114, in __init__
    self.engine_core = EngineCoreClient.make_client(
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 80, in make_client
    return SyncMPClient(vllm_config, executor_class, log_stats)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 602, in __init__
    super().__init__(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 448, in __init__
    with launch_core_engines(vllm_config, executor_class,
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/contextlib.py", line 144, in __exit__
    next(self.gen)
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 732, in launch_core_engines
    wait_for_engine_startup(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 785, in wait_for_engine_startup
    raise RuntimeError("Engine core initialization failed. "
RuntimeError: Engine core initialization failed. See root cause above. Failed core proc(s): {}
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=16396) INFO 03-01 21:33:11 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     self._init_executor()
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708]     raise ValueError(
(EngineCore_DP0 pid=16396) ERROR 03-01 21:33:12 [core.py:708] ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
(EngineCore_DP0 pid=16396) Process EngineCore_DP0:
(EngineCore_DP0 pid=16396) Traceback (most recent call last):
(EngineCore_DP0 pid=16396)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=16396)     self.run()
(EngineCore_DP0 pid=16396)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=16396)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=16396)     raise e
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=16396)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=16396)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=16396)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 83, in __init__
(EngineCore_DP0 pid=16396)     self.model_executor = executor_class(vllm_config)
(EngineCore_DP0 pid=16396)                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/executor_base.py", line 54, in __init__
(EngineCore_DP0 pid=16396)     self._init_executor()
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 54, in _init_executor
(EngineCore_DP0 pid=16396)     self.collective_rpc("init_device")
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=16396)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=16396)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=16396)     return func(*args, **kwargs)
(EngineCore_DP0 pid=16396)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/worker/worker_base.py", line 259, in init_device
(EngineCore_DP0 pid=16396)     self.worker.init_device()  # type: ignore
(EngineCore_DP0 pid=16396)     ^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=16396)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 187, in init_device
(EngineCore_DP0 pid=16396)     raise ValueError(
(EngineCore_DP0 pid=16396) ValueError: Free memory on device (13.91/79.33 GiB) on startup is less than desired GPU memory utilization (0.95, 75.36 GiB). Decrease GPU memory utilization or reduce GPU memory used by other processes.
[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
[rank0]:[W301 21:33:12.786859149 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
Traceback (most recent call last):
  File "<frozen runpy>", line 198, in _run_module_as_main
  File "<frozen runpy>", line 88, in _run_code
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
    initialize_model()
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
    model = vllm.LLM(
            ^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/llm.py", line 297, in __init__
    self.llm_engine = LLMEngine.from_engine_args(
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 177, in from_engine_args
    return cls(vllm_config=vllm_config,
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/llm_engine.py", line 114, in __init__
    self.engine_core = EngineCoreClient.make_client(
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 80, in make_client
    return SyncMPClient(vllm_config, executor_class, log_stats)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 602, in __init__
    super().__init__(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 448, in __init__
    with launch_core_engines(vllm_config, executor_class,
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/contextlib.py", line 144, in __exit__
    next(self.gen)
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 732, in launch_core_engines
    wait_for_engine_startup(
  File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 785, in wait_for_engine_startup
    raise RuntimeError("Engine core initialization failed. "
RuntimeError: Engine core initialization failed. See root cause above. Failed core proc(s): {}
[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ 
