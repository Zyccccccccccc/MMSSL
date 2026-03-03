(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 

export RAY_raylet_start_wait_time_s=60

++ date +%Y-%m-%d-%H-%M
++ tee -a /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/logs/train_data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-2026-03-03-21-51.log
+ ray stop --force
Did not find any active Ray processes.
+ sleep 3
+ cd /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS
+ echo 'Starting round 1 training...'
Starting round 1 training...
+ echo 'Training Challenger...'
Training Challenger...
+ bash /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script/challenger.sh data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V2 /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B 5 TTCS True ttrl_icl /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet
Force cleaning up vLLM processes and ports before starting...
  Force cleaning up all vLLM related processes...
    vLLM process status before cleanup:
      No vLLM processes found
    No vLLM processes to clean up
    Cleaning up vLLM multiprocess child processes...
    No vLLM child processes to clean up
    vLLM process status after cleanup:
      No vLLM processes found
      No vLLM child processes found
    Port usage status after cleanup:
      Port 5000 is free
      Port 5001 is free
      Port 5002 is free
      Port 5003 is free
  vLLM process force cleanup completed
[exp_name]:data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V2
[challenger_model_path]: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B
[solver_model_path]: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B
[challenger_training_steps]: 5
[Path Config] Working Dir: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS
[Path Config] Prompt Dir: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src
[Path Config] Storage Path: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl/data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V2
[GPU Config] Challenger GPUs: 0,1,2,3 (total 4)
[GPU Config] Reward GPUs: 4,5,6,7
[GPU Config] Reward Ports: 5000,5001,5002,5003
[Reward Server] GPU Config: 4,5,6,7
[Reward Server] Port Config: 5000,5001,5002,5003
Starting vLLM reward server...
Launching Reward Server: GPU=4, Port=5000
Launching Reward Server: GPU=5, Port=5001
Launching Reward Server: GPU=6, Port=5002
Launching Reward Server: GPU=7, Port=5003
Waiting for vLLM service to start...
Starting main training process...
Using GPU: 0,1,2,3, total 4
INFO 03-03 21:55:24 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 21:55:24 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 21:55:39 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 21:55:40 __init__.py:190] Automatically detected platform cuda.
[2026-03-03 21:56:14,398 W 102844 102844] gcs_rpc_client.h:155: Failed to connect to GCS at address 10.166.176.28:54866 within 5 seconds.
2026-03-03 21:56:42,162 ERROR services.py:1357 -- Failed to start the dashboard 
2026-03-03 21:56:42,162 ERROR services.py:1382 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-03 21:56:42,162 ERROR services.py:1392 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_21-56-09_365640_102844/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-03 21:56:42,162 ERROR services.py:1426 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_21-56-09_365640_102844/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-03 21:57:11,331 INFO worker.py:1951 -- Started a local Ray instance.
[2026-03-03 21:57:48,712 E 102844 102844] core_worker_process.cc:232: Failed to register worker to Raylet: IOError: Failed to read data from the socket: End of file worker_id=01000000ffffffffffffffffffffffffffffffffffffffffffffffff
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 TTCS]$ + echo 'Error: Round 1 Challenger training failed'
Error: Round 1 Challenger training failed
+ exit 1
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-03 21:58:15 config.py:542] This model supports multiple tasks: {'generate', 'reward', 'embed', 'classify', 'score'}. Defaulting to 'generate'.
INFO 03-03 21:58:15 llm_engine.py:234] Initializing a V0 LLM engine (v0.7.3.dev0+g0408efc6d.d20250904) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, override_neuron_config=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto,  device_config=cuda, decoding_config=DecodingConfig(guided_decoding_backend='xgrammar'), observability_config=ObservabilityConfig(otlp_traces_endpoint=None, collect_model_forward_time=False, collect_model_execute_time=False), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, num_scheduler_steps=1, multi_step_stream_outputs=True, enable_prefix_caching=False, chunked_prefill_enabled=False, use_async_output_proc=True, disable_mm_preprocessor_cache=False, mm_processor_kwargs=None, pooler_config=None, compilation_config={"splitting_ops":[],"compile_sizes":[],"cudagraph_capture_sizes":[256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"max_capture_size":256}, use_cached_outputs=False, 
INFO 03-03 21:58:17 cuda.py:230] Using Flash Attention backend.
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-03 21:58:19 config.py:542] This model supports multiple tasks: {'embed', 'generate', 'reward', 'classify', 'score'}. Defaulting to 'generate'.
INFO 03-03 21:58:19 llm_engine.py:234] Initializing a V0 LLM engine (v0.7.3.dev0+g0408efc6d.d20250904) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, override_neuron_config=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto,  device_config=cuda, decoding_config=DecodingConfig(guided_decoding_backend='xgrammar'), observability_config=ObservabilityConfig(otlp_traces_endpoint=None, collect_model_forward_time=False, collect_model_execute_time=False), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, num_scheduler_steps=1, multi_step_stream_outputs=True, enable_prefix_caching=False, chunked_prefill_enabled=False, use_async_output_proc=True, disable_mm_preprocessor_cache=False, mm_processor_kwargs=None, pooler_config=None, compilation_config={"splitting_ops":[],"compile_sizes":[],"cudagraph_capture_sizes":[256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"max_capture_size":256}, use_cached_outputs=False, 
INFO 03-03 21:58:20 cuda.py:230] Using Flash Attention backend.
INFO 03-03 21:58:24 model_runner.py:1110] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.01it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.01it/s]

INFO 03-03 21:58:25 model_runner.py:1115] Loading model weights took 2.8797 GB
[rank0]: Traceback (most recent call last):
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 196, in _run_module_as_main
[rank0]:     return _run_code(code, main_globals, None,
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 86, in _run_code
[rank0]:     exec(code, run_globals)
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
[rank0]:     initialize_model()
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
[rank0]:     model = vllm.LLM(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 1051, in inner
[rank0]:     return fn(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/entrypoints/llm.py", line 242, in __init__
[rank0]:     self.llm_engine = self.engine_class.from_engine_args(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 484, in from_engine_args
[rank0]:     engine = cls(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 276, in __init__
[rank0]:     self._initialize_kv_caches()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 416, in _initialize_kv_caches
[rank0]:     self.model_executor.determine_num_available_blocks())
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/executor_base.py", line 101, in determine_num_available_blocks
[rank0]:     results = self.collective_rpc("determine_num_available_blocks")
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/uniproc_executor.py", line 51, in collective_rpc
[rank0]:     answer = run_method(self.driver_worker, method, args, kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 2220, in run_method
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/worker.py", line 229, in determine_num_available_blocks
[rank0]:     self.model_runner.profile_run()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1235, in profile_run
[rank0]:     self._dummy_run(max_num_batched_tokens, max_num_seqs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1346, in _dummy_run
[rank0]:     self.execute_model(model_input, kv_caches, intermediate_tensors)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1719, in execute_model
[rank0]:     hidden_or_intermediate_states = model_executable(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 486, in forward
[rank0]:     hidden_states = self.model(input_ids, positions, kv_caches,
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/compilation/decorators.py", line 172, in __call__
[rank0]:     return self.forward(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 348, in forward
[rank0]:     hidden_states, residual = layer(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 247, in forward
[rank0]:     hidden_states = self.self_attn(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 176, in forward
[rank0]:     qkv, _ = self.qkv_proj(hidden_states)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 382, in forward
[rank0]:     output_parallel = self.quant_method.apply(self, input_, bias)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 142, in apply
[rank0]:     return F.linear(x, layer.weight, bias)
[rank0]: RuntimeError: CUDA error: no kernel image is available for execution on the device
[rank0]: CUDA kernel errors might be asynchronously reported at some other API call, so the stacktrace below might be incorrect.
[rank0]: For debugging consider passing CUDA_LAUNCH_BLOCKING=1
[rank0]: Compile with `TORCH_USE_CUDA_DSA` to enable device-side assertions.

[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
INFO 03-03 21:58:25 model_runner.py:1110] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
[rank0]:[W303 21:58:26.733661272 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.20it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.20it/s]

INFO 03-03 21:58:26 model_runner.py:1115] Loading model weights took 2.8797 GB
[rank0]: Traceback (most recent call last):
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 196, in _run_module_as_main
[rank0]:     return _run_code(code, main_globals, None,
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 86, in _run_code
[rank0]:     exec(code, run_globals)
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
[rank0]:     initialize_model()
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
[rank0]:     model = vllm.LLM(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 1051, in inner
[rank0]:     return fn(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/entrypoints/llm.py", line 242, in __init__
[rank0]:     self.llm_engine = self.engine_class.from_engine_args(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 484, in from_engine_args
[rank0]:     engine = cls(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 276, in __init__
[rank0]:     self._initialize_kv_caches()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 416, in _initialize_kv_caches
[rank0]:     self.model_executor.determine_num_available_blocks())
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/executor_base.py", line 101, in determine_num_available_blocks
[rank0]:     results = self.collective_rpc("determine_num_available_blocks")
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/uniproc_executor.py", line 51, in collective_rpc
[rank0]:     answer = run_method(self.driver_worker, method, args, kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 2220, in run_method
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/worker.py", line 229, in determine_num_available_blocks
[rank0]:     self.model_runner.profile_run()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1235, in profile_run
[rank0]:     self._dummy_run(max_num_batched_tokens, max_num_seqs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1346, in _dummy_run
[rank0]:     self.execute_model(model_input, kv_caches, intermediate_tensors)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1719, in execute_model
[rank0]:     hidden_or_intermediate_states = model_executable(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 486, in forward
[rank0]:     hidden_states = self.model(input_ids, positions, kv_caches,
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/compilation/decorators.py", line 172, in __call__
[rank0]:     return self.forward(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 348, in forward
[rank0]:     hidden_states, residual = layer(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 247, in forward
[rank0]:     hidden_states = self.self_attn(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 176, in forward
[rank0]:     qkv, _ = self.qkv_proj(hidden_states)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 382, in forward
[rank0]:     output_parallel = self.quant_method.apply(self, input_, bias)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 142, in apply
[rank0]:     return F.linear(x, layer.weight, bias)
[rank0]: RuntimeError: CUDA error: no kernel image is available for execution on the device
[rank0]: CUDA kernel errors might be asynchronously reported at some other API call, so the stacktrace below might be incorrect.
[rank0]: For debugging consider passing CUDA_LAUNCH_BLOCKING=1
[rank0]: Compile with `TORCH_USE_CUDA_DSA` to enable device-side assertions.

[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
[rank0]:[W303 21:58:28.743198732 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-03 21:58:46 config.py:542] This model supports multiple tasks: {'reward', 'score', 'embed', 'generate', 'classify'}. Defaulting to 'generate'.
INFO 03-03 21:58:46 llm_engine.py:234] Initializing a V0 LLM engine (v0.7.3.dev0+g0408efc6d.d20250904) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, override_neuron_config=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto,  device_config=cuda, decoding_config=DecodingConfig(guided_decoding_backend='xgrammar'), observability_config=ObservabilityConfig(otlp_traces_endpoint=None, collect_model_forward_time=False, collect_model_execute_time=False), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, num_scheduler_steps=1, multi_step_stream_outputs=True, enable_prefix_caching=False, chunked_prefill_enabled=False, use_async_output_proc=True, disable_mm_preprocessor_cache=False, mm_processor_kwargs=None, pooler_config=None, compilation_config={"splitting_ops":[],"compile_sizes":[],"cudagraph_capture_sizes":[256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"max_capture_size":256}, use_cached_outputs=False, 
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-03 21:58:46 config.py:542] This model supports multiple tasks: {'generate', 'embed', 'classify', 'score', 'reward'}. Defaulting to 'generate'.
INFO 03-03 21:58:46 llm_engine.py:234] Initializing a V0 LLM engine (v0.7.3.dev0+g0408efc6d.d20250904) with config: model='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', speculative_config=None, tokenizer='/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, override_neuron_config=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.bfloat16, max_seq_len=4096, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, disable_custom_all_reduce=False, quantization=None, enforce_eager=False, kv_cache_dtype=auto,  device_config=cuda, decoding_config=DecodingConfig(guided_decoding_backend='xgrammar'), observability_config=ObservabilityConfig(otlp_traces_endpoint=None, collect_model_forward_time=False, collect_model_execute_time=False), seed=0, served_model_name=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B, num_scheduler_steps=1, multi_step_stream_outputs=True, enable_prefix_caching=False, chunked_prefill_enabled=False, use_async_output_proc=True, disable_mm_preprocessor_cache=False, mm_processor_kwargs=None, pooler_config=None, compilation_config={"splitting_ops":[],"compile_sizes":[],"cudagraph_capture_sizes":[256,248,240,232,224,216,208,200,192,184,176,168,160,152,144,136,128,120,112,104,96,88,80,72,64,56,48,40,32,24,16,8,4,2,1],"max_capture_size":256}, use_cached_outputs=False, 
INFO 03-03 21:58:48 cuda.py:230] Using Flash Attention backend.
INFO 03-03 21:58:48 cuda.py:230] Using Flash Attention backend.
INFO 03-03 21:58:50 model_runner.py:1110] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
INFO 03-03 21:58:51 model_runner.py:1110] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.22it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.22it/s]

Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.85it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.85it/s]

INFO 03-03 21:58:52 model_runner.py:1115] Loading model weights took 2.8797 GB
INFO 03-03 21:58:52 model_runner.py:1115] Loading model weights took 2.8797 GB
[rank0]: Traceback (most recent call last):
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 196, in _run_module_as_main
[rank0]:     return _run_code(code, main_globals, None,
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 86, in _run_code
[rank0]:     exec(code, run_globals)
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
[rank0]:     initialize_model()
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
[rank0]:     model = vllm.LLM(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 1051, in inner
[rank0]:     return fn(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/entrypoints/llm.py", line 242, in __init__
[rank0]:     self.llm_engine = self.engine_class.from_engine_args(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 484, in from_engine_args
[rank0]:     engine = cls(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 276, in __init__
[rank0]:     self._initialize_kv_caches()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 416, in _initialize_kv_caches
[rank0]:     self.model_executor.determine_num_available_blocks())
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/executor_base.py", line 101, in determine_num_available_blocks
[rank0]:     results = self.collective_rpc("determine_num_available_blocks")
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/uniproc_executor.py", line 51, in collective_rpc
[rank0]:     answer = run_method(self.driver_worker, method, args, kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 2220, in run_method
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/worker.py", line 229, in determine_num_available_blocks
[rank0]:     self.model_runner.profile_run()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1235, in profile_run
[rank0]:     self._dummy_run(max_num_batched_tokens, max_num_seqs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1346, in _dummy_run
[rank0]:     self.execute_model(model_input, kv_caches, intermediate_tensors)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1719, in execute_model
[rank0]:     hidden_or_intermediate_states = model_executable(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 486, in forward
[rank0]:     hidden_states = self.model(input_ids, positions, kv_caches,
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/compilation/decorators.py", line 172, in __call__
[rank0]:     return self.forward(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 348, in forward
[rank0]:     hidden_states, residual = layer(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 247, in forward
[rank0]:     hidden_states = self.self_attn(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 176, in forward
[rank0]:     qkv, _ = self.qkv_proj(hidden_states)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 382, in forward
[rank0]:     output_parallel = self.quant_method.apply(self, input_, bias)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 142, in apply
[rank0]:     return F.linear(x, layer.weight, bias)
[rank0]: RuntimeError: CUDA error: no kernel image is available for execution on the device
[rank0]: CUDA kernel errors might be asynchronously reported at some other API call, so the stacktrace below might be incorrect.
[rank0]: For debugging consider passing CUDA_LAUNCH_BLOCKING=1
[rank0]: Compile with `TORCH_USE_CUDA_DSA` to enable device-side assertions.

[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
[rank0]: Traceback (most recent call last):
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 196, in _run_module_as_main
[rank0]:     return _run_code(code, main_globals, None,
[rank0]:   File "/usr/local/conda/lib/python3.10/runpy.py", line 86, in _run_code
[rank0]:     exec(code, run_globals)
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 288, in <module>
[rank0]:     initialize_model()
[rank0]:   File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/start_vllm_server.py", line 67, in initialize_model
[rank0]:     model = vllm.LLM(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 1051, in inner
[rank0]:     return fn(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/entrypoints/llm.py", line 242, in __init__
[rank0]:     self.llm_engine = self.engine_class.from_engine_args(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 484, in from_engine_args
[rank0]:     engine = cls(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 276, in __init__
[rank0]:     self._initialize_kv_caches()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/engine/llm_engine.py", line 416, in _initialize_kv_caches
[rank0]:     self.model_executor.determine_num_available_blocks())
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/executor_base.py", line 101, in determine_num_available_blocks
[rank0]:     results = self.collective_rpc("determine_num_available_blocks")
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/executor/uniproc_executor.py", line 51, in collective_rpc
[rank0]:     answer = run_method(self.driver_worker, method, args, kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/utils.py", line 2220, in run_method
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/worker.py", line 229, in determine_num_available_blocks
[rank0]:     self.model_runner.profile_run()
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1235, in profile_run
[rank0]:     self._dummy_run(max_num_batched_tokens, max_num_seqs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1346, in _dummy_run
[rank0]:     self.execute_model(model_input, kv_caches, intermediate_tensors)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
[rank0]:     return func(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/worker/model_runner.py", line 1719, in execute_model
[rank0]:     hidden_or_intermediate_states = model_executable(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 486, in forward
[rank0]:     hidden_states = self.model(input_ids, positions, kv_caches,
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/compilation/decorators.py", line 172, in __call__
[rank0]:     return self.forward(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 348, in forward
[rank0]:     hidden_states, residual = layer(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 247, in forward
[rank0]:     hidden_states = self.self_attn(
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/models/qwen2.py", line 176, in forward
[rank0]:     qkv, _ = self.qkv_proj(hidden_states)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1739, in _wrapped_call_impl
[rank0]:     return self._call_impl(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/torch/nn/modules/module.py", line 1750, in _call_impl
[rank0]:     return forward_call(*args, **kwargs)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 382, in forward
[rank0]:     output_parallel = self.quant_method.apply(self, input_, bias)
[rank0]:   File "/usr/local/conda/lib/python3.10/site-packages/vllm/model_executor/layers/linear.py", line 142, in apply
[rank0]:     return F.linear(x, layer.weight, bias)
[rank0]: RuntimeError: CUDA error: no kernel image is available for execution on the device
[rank0]: CUDA kernel errors might be asynchronously reported at some other API call, so the stacktrace below might be incorrect.
[rank0]: For debugging consider passing CUDA_LAUNCH_BLOCKING=1
[rank0]: Compile with `TORCH_USE_CUDA_DSA` to enable device-side assertions.

[init] Resuming GPU idle worker...
[idle_worker] GPU idle worker stopped.
[main] Application shutdown complete.
[rank0]:[W303 21:58:53.170622958 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
[rank0]:[W303 21:58:53.310702803 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
^C
