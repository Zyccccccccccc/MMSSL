NFO 03-03 19:25:00 [__init__.py:216] Automatically detected platform cuda.
ray init kwargs: {'num_cpus': None, 'runtime_env': {'env_vars': {'TOKENIZERS_PARALLELISM': 'true', 'NCCL_DEBUG': 'WARN', 'VLLM_LOGGING_LEVEL': 'WARN', 'VLLM_ALLOW_RUNTIME_LORA_UPDATING': 'true', 'CUDA_DEVICE_MAX_CONNECTIONS': '1', 'NCCL_CUMEM_ENABLE': '0'}, 'working_dir': None}}
Error executing job with overrides: ['algorithm.adv_estimator=grpo', 'data.train_batch_size=32', 'data.max_prompt_length=3072', 'data.max_response_length=1024', 'data.num_querys=160', '+data.get_prompts_func=ttrl_icl', '+data.gen_question_func=ttrl_icl', '+data.prompt_path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src', 'data.filter_overlong_prompts=True', 'data.dynamic_topics=False', 'data.truncation=error', '+data.ttrl_icl_files=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet', 'actor_rollout_ref.model.path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'actor_rollout_ref.actor.optim.lr=1e-6', "actor_rollout_ref.actor.checkpoint.save_contents=['hf_model']", 'actor_rollout_ref.model.use_remove_padding=True', 'actor_rollout_ref.actor.ppo_mini_batch_size=8', 'actor_rollout_ref.actor.ppo_micro_batch_size_per_gpu=2', 'actor_rollout_ref.actor.use_kl_loss=True', 'actor_rollout_ref.actor.kl_loss_coef=0.01', 'actor_rollout_ref.actor.kl_loss_type=low_var_kl', 'actor_rollout_ref.actor.entropy_coeff=0', 'actor_rollout_ref.model.enable_gradient_checkpointing=True', 'actor_rollout_ref.actor.fsdp_config.param_offload=False', 'actor_rollout_ref.actor.fsdp_config.optimizer_offload=False', 'actor_rollout_ref.rollout.log_prob_micro_batch_size_per_gpu=2', 'actor_rollout_ref.rollout.tensor_model_parallel_size=1', 'actor_rollout_ref.rollout.name=vllm', 'actor_rollout_ref.rollout.temperature=1.0', 'actor_rollout_ref.rollout.top_p=0.99', 'actor_rollout_ref.rollout.top_k=-1', 'actor_rollout_ref.rollout.gpu_memory_utilization=0.60', 'actor_rollout_ref.rollout.n=4', 'actor_rollout_ref.ref.log_prob_micro_batch_size_per_gpu=2', 'actor_rollout_ref.ref.fsdp_config.param_offload=True', 'algorithm.use_kl_in_reward=False', 'reward_model.reward_manager=challenger', 'reward_model.reward_kwargs.storage_path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl/data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1', '+reward_model.reward_kwargs.question_reward=TTCS', '+reward_model.reward_kwargs.group_question_repetion_penalty=True', '+reward_model.reward_kwargs.gen_question_func=ttrl_icl', 'trainer.critic_warmup=0', 'trainer.logger=["console","tensorboard"]', 'trainer.project_name=TTCS', 'trainer.experiment_name=Challenger-data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1', 'trainer.n_gpus_per_node=4', 'trainer.total_training_steps=5', 'trainer.nnodes=1', 'trainer.val_before_train=False', 'trainer.default_local_dir=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl/data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1/ckpts/', 'trainer.save_freq=5', 'trainer.test_freq=-1', 'trainer.total_epochs=15']
Traceback (most recent call last):
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/main_challenger.py", line 44, in main
    run_ppo(config)
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/main_challenger.py", line 68, in run_ppo
    ray.init(
  File "/usr/local/lib/python3.12/dist-packages/ray/_private/client_mode_hook.py", line 104, in wrapper
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/_private/worker.py", line 1737, in init
    raise RuntimeError(f"Unknown keyword argument(s): {unknown}")
RuntimeError: Unknown keyword argument(s): gcs_rpc_server_connect_timeout_seconds, gcs_server_connect_timeout_seconds

Set the environment variable HYDRA_FULL_ERROR=1 for a complete stack trace.
+ echo 'Error: Round 1 Challenger training failed'
Error: Round 1 Challenger training failed
hadoop-ai-search@psx3g5axria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ + exit 1
INFO 03-03 19:26:04 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 19:26:05 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 19:26:05 [model.py:1510] Using max model len 4096
INFO 03-03 19:26:05 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-03 19:26:06 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 19:26:07 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 19:26:07 [model.py:1510] Using max model len 4096
INFO 03-03 19:26:07 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-03 19:26:11 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 19:26:11 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 19:26:11 [model.py:1510] Using max model len 4096
INFO 03-03 19:26:11 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-03 19:26:17 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 19:26:17 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 19:26:17 [model.py:1510] Using max model len 4096
INFO 03-03 19:26:17 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
W0303 19:31:37.780000 39544 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0303 19:31:37.780000 39544 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
WARNING:2026-03-03 19:31:37,790:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-03 19:31:37,862:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-03 19:31:37,869:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-03 19:31:37,884:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
W0303 19:31:38.883000 39544 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0303 19:31:38.883000 39544 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0303 19:31:40.429000 39549 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0303 19:31:40.429000 39549 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0303 19:31:41.239000 39535 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0303 19:31:41.239000 39535 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0303 19:31:41.628000 39539 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0303 19:31:41.628000 39539 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
INFO 03-03 19:32:18 [__init__.py:216] Automatically detected platform cuda.
INFO 03-03 19:32:18 [__init__.py:216] Automatically detected platform cuda.
INFO 03-03 19:32:18 [__init__.py:216] Automatically detected platform cuda.
INFO 03-03 19:32:18 [__init__.py:216] Automatically detected platform cuda.
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:19 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:19 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:20 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:20 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:23 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:23 [topk_topp_sampler.py:55] Using FlashInfer for top-p & top-k sampling.
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:23 [gpu_model_runner.py:2602] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:23 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:23 [gpu_model_runner.py:2634] Loading model from scratch...
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:23 [topk_topp_sampler.py:55] Using FlashInfer for top-p & top-k sampling.
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:23 [cuda.py:366] Using Flash Attention backend on V1 engine.
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:23 [gpu_model_runner.py:2602] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:24 [gpu_model_runner.py:2634] Loading model from scratch...
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:24 [cuda.py:366] Using Flash Attention backend on V1 engine.
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.62it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.62it/s]
(EngineCore_DP0 pid=39535) 
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:24 [default_loader.py:267] Loading weights took 0.69 seconds
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.87it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.87it/s]
(EngineCore_DP0 pid=39544) 
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:25 [default_loader.py:267] Loading weights took 0.61 seconds
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:25 [gpu_model_runner.py:2653] Model loading took 2.8798 GiB and 0.980978 seconds
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:25 [gpu_model_runner.py:2653] Model loading took 2.8798 GiB and 0.852156 seconds
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:29 [backends.py:546] vLLM's torch.compile cache is disabled.
(EngineCore_DP0 pid=39535) INFO 03-03 19:33:29 [backends.py:559] Dynamo bytecode transform time: 3.82 s
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:29 [backends.py:546] vLLM's torch.compile cache is disabled.
(EngineCore_DP0 pid=39544) INFO 03-03 19:33:29 [backends.py:559] Dynamo bytecode transform time: 3.78 s
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:32 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:32 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:37 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:37 [topk_topp_sampler.py:55] Using FlashInfer for top-p & top-k sampling.
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:37 [gpu_model_runner.py:2602] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:38 [gpu_model_runner.py:2634] Loading model from scratch...
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:38 [cuda.py:366] Using Flash Attention backend on V1 engine.
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.73it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.73it/s]
(EngineCore_DP0 pid=39549) 
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:39 [default_loader.py:267] Loading weights took 0.65 seconds
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:39 [gpu_model_runner.py:2653] Model loading took 2.8798 GiB and 0.934149 seconds
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:40 [core.py:644] Waiting for init message from front-end.
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:40 [core.py:77] Initializing a V1 LLM engine (v0.11.0) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser=''), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, enable_prefix_caching=True, chunked_prefill_enabled=True, pooler_config=None, compilation_config={"level":3,"debug_dump_path":"","cache_dir":"","backend":"","custom_ops":[],"splitting_ops":["vllm.unified_attention","vllm.unified_attention_with_output","vllm.mamba_mixer2","vllm.mamba_mixer","vllm.short_conv","vllm.linear_attention","vllm.plamo2_mamba_mixer","vllm.gdn_attention","vllm.sparse_attn_indexer"],"use_inductor":true,"compile_sizes":[],"inductor_compile_config":{"enable_auto_functionalized_v2":false},"inductor_passes":{},"cudagraph_mode":[2,1],"use_cudagraph":true,"cudagraph_num_of_warmups":1,"cudagraph_capture_sizes":[512,504,496,488,480,472,464,456,448,440,432,424,416,408,400,392,384,376,368,360,352,344,336,328,320,312,304,296,288,280,272,264,256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"cudagraph_copy_inputs":false,"full_cuda_graph":false,"use_inductor_graph_partition":false,"pass_config":{},"max_capture_size":512,"local_cache_dir":null}
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:43 [backends.py:546] vLLM's torch.compile cache is disabled.
(EngineCore_DP0 pid=39549) INFO 03-03 19:33:43 [backends.py:559] Dynamo bytecode transform time: 3.81 s
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
[Gloo] Rank 0 is connected to 0 peer ranks. Expected number of connected peer ranks is : 0
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:45 [parallel_state.py:1208] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, TP rank 0, EP rank 0
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:45 [topk_topp_sampler.py:55] Using FlashInfer for top-p & top-k sampling.
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:45 [gpu_model_runner.py:2602] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:45 [gpu_model_runner.py:2634] Loading model from scratch...
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:46 [cuda.py:366] Using Flash Attention backend on V1 engine.
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.85it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.85it/s]
(EngineCore_DP0 pid=39539) 
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:47 [default_loader.py:267] Loading weights took 0.61 seconds
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:48 [gpu_model_runner.py:2653] Model loading took 2.8798 GiB and 1.686031 seconds
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:52 [backends.py:546] vLLM's torch.compile cache is disabled.
(EngineCore_DP0 pid=39539) INFO 03-03 19:33:52 [backends.py:559] Dynamo bytecode transform time: 3.81 s
(EngineCore_DP0 pid=39535) INFO 03-03 19:37:27 [backends.py:218] Compiling a graph for dynamic shape takes 237.52 s
(EngineCore_DP0 pid=39535) INFO 03-03 19:37:28 [monitor.py:34] torch.compile takes 241.34 s in total
(EngineCore_DP0 pid=39544) INFO 03-03 19:37:33 [backends.py:218] Compiling a graph for dynamic shape takes 243.83 s
(EngineCore_DP0 pid=39544) INFO 03-03 19:37:34 [monitor.py:34] torch.compile takes 247.60 s in total
(EngineCore_DP0 pid=39539) INFO 03-03 19:38:15 [backends.py:218] Compiling a graph for dynamic shape takes 263.47 s
(EngineCore_DP0 pid=39539) INFO 03-03 19:38:16 [monitor.py:34] torch.compile takes 267.28 s in total
(EngineCore_DP0 pid=39535) INFO 03-03 19:38:23 [gpu_worker.py:298] Available KV cache memory: 70.35 GiB
(EngineCore_DP0 pid=39535) INFO 03-03 19:38:23 [kv_cache_utils.py:1087] GPU KV cache size: 2,634,544 tokens
(EngineCore_DP0 pid=39535) INFO 03-03 19:38:23 [kv_cache_utils.py:1091] Maximum concurrency for 4,096 tokens per request: 643.20x
Capturing CUDA graphs (mixed prefill-decode, PIECEWISE): 100%|███████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:01<00:00, 34.39it/s]
Capturing CUDA graphs (decode, FULL): 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:02<00:00, 23.80it/s]
(EngineCore_DP0 pid=39535) INFO 03-03 19:38:29 [gpu_model_runner.py:3480] Graph capturing finished in 5 secs, took 3.49 GiB
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62912 has 494.00 MiB memory in use. Process 113443 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] 
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] 
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708]     raise RuntimeError(
(EngineCore_DP0 pid=39535) ERROR 03-03 19:38:29 [core.py:708] RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
(EngineCore_DP0 pid=39535) Process EngineCore_DP0:
(EngineCore_DP0 pid=39535) Traceback (most recent call last):
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39535)     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39535)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39535)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39535)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39535)     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39535)                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39535)     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39535)                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39535)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39535)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39535)     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39535)     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39535)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39535)     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39535)                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39535)     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39535)     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39535)                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535) torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62912 has 494.00 MiB memory in use. Process 113443 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39535) 
(EngineCore_DP0 pid=39535) The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39535) 
(EngineCore_DP0 pid=39535) Traceback (most recent call last):
(EngineCore_DP0 pid=39535)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=39535)     self.run()
(EngineCore_DP0 pid=39535)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=39535)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=39535)     raise e
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39535)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39535)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39535)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39535)     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39535)     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39535)     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39535)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39535)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39535)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39535)     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39535)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39535)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39535)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39535)     raise RuntimeError(
(EngineCore_DP0 pid=39535) RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
[rank0]:[W303 19:38:29.330772837 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
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
(EngineCore_DP0 pid=39544) INFO 03-03 19:38:31 [gpu_worker.py:298] Available KV cache memory: 70.35 GiB
[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
(EngineCore_DP0 pid=39544) INFO 03-03 19:38:31 [kv_cache_utils.py:1087] GPU KV cache size: 2,634,544 tokens
(EngineCore_DP0 pid=39544) INFO 03-03 19:38:31 [kv_cache_utils.py:1091] Maximum concurrency for 4,096 tokens per request: 643.20x
Capturing CUDA graphs (mixed prefill-decode, PIECEWISE): 100%|███████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:02<00:00, 22.76it/s]
Capturing CUDA graphs (decode, FULL):   0%|                                                                                                                   | 0/67 [00:00<?, ?it/s](EngineCore_DP0 pid=39549) INFO 03-03 19:38:35 [backends.py:218] Compiling a graph for dynamic shape takes 291.41 s
Capturing CUDA graphs (decode, FULL):  30%|███████████████████████████████▋                                                                          | 20/67 [00:00<00:01, 34.08it/s](EngineCore_DP0 pid=39549) INFO 03-03 19:38:35 [monitor.py:34] torch.compile takes 295.22 s in total
Capturing CUDA graphs (decode, FULL): 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:01<00:00, 34.30it/s]
(EngineCore_DP0 pid=39544) INFO 03-03 19:38:37 [gpu_model_runner.py:3480] Graph capturing finished in 6 secs, took 3.49 GiB
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62909 has 494.00 MiB memory in use. Process 114007 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] 
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] 
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708]     raise RuntimeError(
(EngineCore_DP0 pid=39544) ERROR 03-03 19:38:37 [core.py:708] RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
(EngineCore_DP0 pid=39544) Process EngineCore_DP0:
(EngineCore_DP0 pid=39544) Traceback (most recent call last):
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39544)     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39544)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39544)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39544)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39544)     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39544)                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39544)     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39544)                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39544)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39544)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39544)     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39544)     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39544)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39544)     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39544)                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39544)     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39544)     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39544)                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544) torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62909 has 494.00 MiB memory in use. Process 114007 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39544) 
(EngineCore_DP0 pid=39544) The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39544) 
(EngineCore_DP0 pid=39544) Traceback (most recent call last):
(EngineCore_DP0 pid=39544)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=39544)     self.run()
(EngineCore_DP0 pid=39544)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=39544)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=39544)     raise e
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39544)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39544)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39544)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39544)     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39544)     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39544)     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39544)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39544)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39544)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39544)     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39544)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39544)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39544)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39544)     raise RuntimeError(
(EngineCore_DP0 pid=39544) RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
[rank0]:[W303 19:38:38.805516994 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
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
(EngineCore_DP0 pid=39539) INFO 03-03 19:39:06 [gpu_worker.py:298] Available KV cache memory: 70.35 GiB
(EngineCore_DP0 pid=39539) INFO 03-03 19:39:06 [kv_cache_utils.py:1087] GPU KV cache size: 2,634,544 tokens
(EngineCore_DP0 pid=39539) INFO 03-03 19:39:06 [kv_cache_utils.py:1091] Maximum concurrency for 4,096 tokens per request: 643.20x
Capturing CUDA graphs (mixed prefill-decode, PIECEWISE): 100%|███████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:01<00:00, 35.00it/s]
Capturing CUDA graphs (decode, FULL): 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:02<00:00, 23.69it/s]
(EngineCore_DP0 pid=39539) INFO 03-03 19:39:12 [gpu_model_runner.py:3480] Graph capturing finished in 5 secs, took 3.49 GiB
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62910 has 494.00 MiB memory in use. Process 113506 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] 
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] 
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708]     raise RuntimeError(
(EngineCore_DP0 pid=39539) ERROR 03-03 19:39:12 [core.py:708] RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
(EngineCore_DP0 pid=39539) Process EngineCore_DP0:
(EngineCore_DP0 pid=39539) Traceback (most recent call last):
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39539)     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39539)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39539)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39539)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39539)     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39539)                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39539)     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39539)                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39539)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39539)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39539)     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39539)     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39539)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39539)     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39539)                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39539)     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39539)     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39539)                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539) torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62910 has 494.00 MiB memory in use. Process 113506 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39539) 
(EngineCore_DP0 pid=39539) The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39539) 
(EngineCore_DP0 pid=39539) Traceback (most recent call last):
(EngineCore_DP0 pid=39539)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=39539)     self.run()
(EngineCore_DP0 pid=39539)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=39539)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=39539)     raise e
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39539)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39539)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39539)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39539)     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39539)     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39539)     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39539)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39539)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39539)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39539)     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39539)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39539)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39539)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39539)     raise RuntimeError(
(EngineCore_DP0 pid=39539) RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
[rank0]:[W303 19:39:13.626322394 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
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
(EngineCore_DP0 pid=39549) INFO 03-03 19:39:21 [gpu_worker.py:298] Available KV cache memory: 70.35 GiB
(EngineCore_DP0 pid=39549) INFO 03-03 19:39:21 [kv_cache_utils.py:1087] GPU KV cache size: 2,634,544 tokens
(EngineCore_DP0 pid=39549) INFO 03-03 19:39:21 [kv_cache_utils.py:1091] Maximum concurrency for 4,096 tokens per request: 643.20x
Capturing CUDA graphs (mixed prefill-decode, PIECEWISE): 100%|███████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:02<00:00, 26.04it/s]
Capturing CUDA graphs (decode, FULL): 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████| 67/67 [00:01<00:00, 33.79it/s]
(EngineCore_DP0 pid=39549) INFO 03-03 19:39:26 [gpu_model_runner.py:3480] Graph capturing finished in 5 secs, took 3.49 GiB
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] EngineCore failed to start.
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62911 has 494.00 MiB memory in use. Process 114256 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] 
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] 
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] Traceback (most recent call last):
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     return func(*args, **kwargs)
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708]     raise RuntimeError(
(EngineCore_DP0 pid=39549) ERROR 03-03 19:39:26 [core.py:708] RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
(EngineCore_DP0 pid=39549) Process EngineCore_DP0:
(EngineCore_DP0 pid=39549) Traceback (most recent call last):
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3217, in _dummy_sampler_run
(EngineCore_DP0 pid=39549)     sampler_output = self.sampler(logits=logits,
(EngineCore_DP0 pid=39549)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39549)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39549)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 100, in forward
(EngineCore_DP0 pid=39549)     sampled, processed_logprobs = self.sample(logits, sampling_metadata)
(EngineCore_DP0 pid=39549)                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/sampler.py", line 180, in sample
(EngineCore_DP0 pid=39549)     random_sampled, processed_logprobs = self.topk_topp_sampler(
(EngineCore_DP0 pid=39549)                                          ^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1773, in _wrapped_call_impl
(EngineCore_DP0 pid=39549)     return self._call_impl(*args, **kwargs)
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/torch/nn/modules/module.py", line 1784, in _call_impl
(EngineCore_DP0 pid=39549)     return forward_call(*args, **kwargs)
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 122, in forward_cuda
(EngineCore_DP0 pid=39549)     return flashinfer_sample(logits.contiguous(), k, p, generators), None
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/sample/ops/topk_topp_sampler.py", line 289, in flashinfer_sample
(EngineCore_DP0 pid=39549)     next_token_ids = flashinfer.sampling.top_k_top_p_sampling_from_logits(
(EngineCore_DP0 pid=39549)                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 980, in top_k_top_p_sampling_from_logits
(EngineCore_DP0 pid=39549)     masked_logits = top_k_mask_logits(logits, top_k)
(EngineCore_DP0 pid=39549)                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 1300, in top_k_mask_logits
(EngineCore_DP0 pid=39549)     return get_sampling_module().top_k_mask_logits(
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/flashinfer/sampling.py", line 374, in top_k_mask_logits
(EngineCore_DP0 pid=39549)     mask_logits = torch.empty_like(logits)
(EngineCore_DP0 pid=39549)                   ^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549) torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 594.00 MiB. GPU 0 has a total capacity of 79.33 GiB of which 508.44 MiB is free. Process 62911 has 494.00 MiB memory in use. Process 114256 has 78.33 GiB memory in use. Of the allocated memory 74.24 GiB is allocated by PyTorch, with 57.88 MiB allocated in private pools (e.g., CUDA Graphs), and 185.89 MiB is reserved by PyTorch but unallocated. If reserved but unallocated memory is large try setting PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True to avoid fragmentation.  See documentation for Memory Management  (https://pytorch.org/docs/stable/notes/cuda.html#environment-variables)
(EngineCore_DP0 pid=39549) 
(EngineCore_DP0 pid=39549) The above exception was the direct cause of the following exception:
(EngineCore_DP0 pid=39549) 
(EngineCore_DP0 pid=39549) Traceback (most recent call last):
(EngineCore_DP0 pid=39549)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore_DP0 pid=39549)     self.run()
(EngineCore_DP0 pid=39549)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore_DP0 pid=39549)     self._target(*self._args, **self._kwargs)
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 712, in run_engine_core
(EngineCore_DP0 pid=39549)     raise e
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 699, in run_engine_core
(EngineCore_DP0 pid=39549)     engine_core = EngineCoreProc(*args, **kwargs)
(EngineCore_DP0 pid=39549)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 498, in __init__
(EngineCore_DP0 pid=39549)     super().__init__(vllm_config, executor_class, log_stats,
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 92, in __init__
(EngineCore_DP0 pid=39549)     self._initialize_kv_caches(vllm_config)
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 207, in _initialize_kv_caches
(EngineCore_DP0 pid=39549)     self.model_executor.initialize_from_config(kv_cache_configs)
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/executor/abstract.py", line 75, in initialize_from_config
(EngineCore_DP0 pid=39549)     self.collective_rpc("compile_or_warm_up_model")
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/executor/uniproc_executor.py", line 83, in collective_rpc
(EngineCore_DP0 pid=39549)     return [run_method(self.driver_worker, method, args, kwargs)]
(EngineCore_DP0 pid=39549)             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/utils/__init__.py", line 3122, in run_method
(EngineCore_DP0 pid=39549)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_worker.py", line 413, in compile_or_warm_up_model
(EngineCore_DP0 pid=39549)     self.model_runner._dummy_sampler_run(
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/torch/utils/_contextlib.py", line 120, in decorate_context
(EngineCore_DP0 pid=39549)     return func(*args, **kwargs)
(EngineCore_DP0 pid=39549)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore_DP0 pid=39549)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/worker/gpu_model_runner.py", line 3221, in _dummy_sampler_run
(EngineCore_DP0 pid=39549)     raise RuntimeError(
(EngineCore_DP0 pid=39549) RuntimeError: CUDA out of memory occurred when warming up sampler with 1024 dummy requests. Please try lowering `max_num_seqs` or `gpu_memory_utilization` when initializing the engine.
[rank0]:[W303 19:39:27.962901394 ProcessGroupNCCL.cpp:1538] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
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
