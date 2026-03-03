(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 

export RAY_raylet_start_wait_time_s=60



INFO 03-03 23:03:17 model_runner.py:1115] Loading model weights took 2.8797 GB
INFO 03-03 23:03:17 model_runner.py:1110] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
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
INFO 03-03 23:03:18 cuda.py:230] Using Flash Attention backend.
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.22it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  2.22it/s]

[rank0]:[W303 23:03:18.079178563 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
INFO 03-03 23:03:18 model_runner.py:1115] Loading model weights took 2.8797 GB
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
[rank0]:[W303 23:03:19.228261566 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
INFO 03-03 23:03:20 model_runner.py:1110] Starting to load model /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B...
Loading safetensors checkpoint shards:   0% Completed | 0/1 [00:00<?, ?it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.87it/s]
Loading safetensors checkpoint shards: 100% Completed | 1/1 [00:00<00:00,  1.87it/s]

INFO 03-03 23:03:21 model_runner.py:1115] Loading model weights took 2.8797 GB
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
[rank0]:[W303 23:03:22.398538105 ProcessGroupNCCL.cpp:1496] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
[idle_worker] GPU idle worker started.
