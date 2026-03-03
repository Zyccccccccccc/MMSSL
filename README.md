(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 



[idle_worker] Paused.
INFO 03-03 20:02:05 [__init__.py:216] Automatically detected platform cuda.
[2026-03-03 20:02:40,466 W 41024 41024] rpc_client.h:153: Failed to connect to GCS at address 10.166.166.106:48057 within 5 seconds.
[2026-03-03 20:03:10,467 W 41024 41024] gcs_client.cc:205: Failed to get cluster ID from GCS server: TimedOut: Timed out while waiting for GCS to become available.
INFO 03-03 20:03:19 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 20:03:20 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 20:03:20 [model.py:1510] Using max model len 4096
INFO 03-03 20:03:20 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-03 20:03:21 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 20:03:22 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 20:03:22 [model.py:1510] Using max model len 4096
INFO 03-03 20:03:22 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-03 20:03:26 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 20:03:26 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 20:03:26 [model.py:1510] Using max model len 4096
INFO 03-03 20:03:26 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-03 20:03:27 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-03 20:03:28 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-03 20:03:28 [model.py:1510] Using max model len 4096
INFO 03-03 20:03:28 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
2026-03-03 20:04:13,890 ERROR services.py:1342 -- Failed to start the dashboard 
2026-03-03 20:04:13,890 ERROR services.py:1367 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-03 20:04:13,890 ERROR services.py:1377 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_20-02-35_431925_41024/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-03 20:04:13,890 ERROR services.py:1411 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_20-02-35_431925_41024/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-03 20:04:44,051 INFO node.py:362 -- Failed to get node info b'GCS cannot find the node with node ID 9e817062a975ef3b3ef0f18ca757bb0bd42dc0e5848491bd6876bda5. The node registration may not be complete yet before the timeout. Try increase the RAY_raylet_start_wait_time_s config.'
ray init kwargs: {'num_cpus': None, 'runtime_env': {'env_vars': {'TOKENIZERS_PARALLELISM': 'true', 'NCCL_DEBUG': 'WARN', 'VLLM_LOGGING_LEVEL': 'WARN', 'VLLM_ALLOW_RUNTIME_LORA_UPDATING': 'true', 'CUDA_DEVICE_MAX_CONNECTIONS': '1', 'NCCL_CUMEM_ENABLE': '0'}, 'working_dir': None}}
Error executing job with overrides: ['algorithm.adv_estimator=grpo', 'data.train_batch_size=32', 'data.max_prompt_length=3072', 'data.max_response_length=1024', 'data.num_querys=160', '+data.get_prompts_func=ttrl_icl', '+data.gen_question_func=ttrl_icl', '+data.prompt_path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src', 'data.filter_overlong_prompts=True', 'data.dynamic_topics=False', 'data.truncation=error', '+data.ttrl_icl_files=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet', 'actor_rollout_ref.model.path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'actor_rollout_ref.actor.optim.lr=1e-6', "actor_rollout_ref.actor.checkpoint.save_contents=['hf_model']", 'actor_rollout_ref.model.use_remove_padding=True', 'actor_rollout_ref.actor.ppo_mini_batch_size=8', 'actor_rollout_ref.actor.ppo_micro_batch_size_per_gpu=2', 'actor_rollout_ref.actor.use_kl_loss=True', 'actor_rollout_ref.actor.kl_loss_coef=0.01', 'actor_rollout_ref.actor.kl_loss_type=low_var_kl', 'actor_rollout_ref.actor.entropy_coeff=0', 'actor_rollout_ref.model.enable_gradient_checkpointing=True', 'actor_rollout_ref.actor.fsdp_config.param_offload=False', 'actor_rollout_ref.actor.fsdp_config.optimizer_offload=False', 'actor_rollout_ref.rollout.log_prob_micro_batch_size_per_gpu=2', 'actor_rollout_ref.rollout.tensor_model_parallel_size=1', 'actor_rollout_ref.rollout.name=vllm', 'actor_rollout_ref.rollout.temperature=1.0', 'actor_rollout_ref.rollout.top_p=0.99', 'actor_rollout_ref.rollout.top_k=-1', 'actor_rollout_ref.rollout.gpu_memory_utilization=0.60', 'actor_rollout_ref.rollout.n=4', 'actor_rollout_ref.ref.log_prob_micro_batch_size_per_gpu=2', 'actor_rollout_ref.ref.fsdp_config.param_offload=True', 'algorithm.use_kl_in_reward=False', 'reward_model.reward_manager=challenger', 'reward_model.reward_kwargs.storage_path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl/data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1', '+reward_model.reward_kwargs.question_reward=TTCS', '+reward_model.reward_kwargs.group_question_repetion_penalty=True', '+reward_model.reward_kwargs.gen_question_func=ttrl_icl', 'trainer.critic_warmup=0', 'trainer.logger=["console","tensorboard"]', 'trainer.project_name=TTCS', 'trainer.experiment_name=Challenger-data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1', 'trainer.n_gpus_per_node=4', 'trainer.total_training_steps=5', 'trainer.nnodes=1', 'trainer.val_before_train=False', 'trainer.default_local_dir=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl/data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1/ckpts/', 'trainer.save_freq=5', 'trainer.test_freq=-1', 'trainer.total_epochs=15']
Traceback (most recent call last):
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/main_challenger.py", line 44, in main
    run_ppo(config)
  File "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/main_challenger.py", line 68, in run_ppo
    ray.init(**OmegaConf.to_container(ray_init_kwargs))
  File "/usr/local/lib/python3.12/dist-packages/ray/_private/client_mode_hook.py", line 104, in wrapper
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/_private/worker.py", line 1902, in init
    _global_node = ray._private.node.Node(
                   ^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/_private/node.py", line 364, in __init__
    raise Exception(
Exception: The current node timed out during startup. This could happen because some of the raylet failed to startup or the GCS has become overloaded.

Set the environment variable HYDRA_FULL_ERROR=1 for a complete stack trace.
+ echo 'Error: Round 1 Challenger training failed'
hadoop-ai-search@psx3g5axria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ Error: Round 1 Challenger training failed
+ exit 1
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia
