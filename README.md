hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ bash TTCS-base/TTCS/src/script/run_with_gpus.sh 8
==============================================
  Self-evolving-Agent GPU Launcher
==============================================
Time: 2026-03-01 21:06:14

[INFO] 21:06:21 - Requested GPU count: 8

Current GPU Status:
----------------------------------------
GPU   Mem Used     Mem Total    Util       Status  
----------------------------------------
0     5MB          81920MB      0%         Idle    
1     5MB          81920MB      0%         Idle    
2     5MB          81920MB      0%         Idle    
3     5MB          81920MB      0%         Idle    
4     2MB          81920MB      0%         Idle    
5     2MB          81920MB      0%         Idle    
6     2MB          81920MB      0%         Idle    
7     2MB          81920MB      0%         Idle    
----------------------------------------
Idle threshold: Memory < 4000MB, Utilization < 5%

[INFO] 21:06:41 - Waiting for 8 idle GPUs...
[INFO] 21:06:47 - Check interval: 1800s, Max wait: 48h

[INFO] 21:07:20 - Current idle GPUs: 8 / Needed: 8
[INFO] 21:07:26 - GPU resources meet requirements!
[INFO] 21:08:13 - Selected GPUs: 0 1 2 3 4 5 6 7

GPU Allocation Config:
==============================================
Total GPUs:        8
Selected GPU IDs:  0,1,2,3,4,5,6,7

Challenger GPUs:   0,1,2,3 (total 4)
Reward GPUs:       4,5,6,7 (total 4)
Solver GPUs:       0,1,2,3,4,5,6,7 (total 8)
Gen Query GPUs:    0,1,2,3,4,5,6,7

Reward Ports:      5000,5001,5002,5003
Reward Base Port:  5000
==============================================

Path Config:
==============================================
Base Dir:          /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base
Project Name:      TTCS
Code Module:       src
Working Dir:       /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS
Model Dir:         /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05
Data Dir:          /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data
Results Dir:       /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results
Prompt Dir:        /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src
==============================================

[INFO] 21:08:20 - Starting training...

==============================================
  Starting main.sh
==============================================

+ export VLLM_WORKER_MULTIPROC_METHOD=spawn
+ VLLM_WORKER_MULTIPROC_METHOD=spawn
+ export PYTHONPATH=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/workdir:
+ PYTHONPATH=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/workdir:
+++ dirname /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script/main.sh
++ cd /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script
++ pwd
+ SCRIPT_DIR=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script
+ base_model_name=Qwen2.5-Math-1.5B
+ base_model_path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B
+ question_reward=TTCS
+ dataset=Minerva
+ real_data_ratio=5.0
+ temperature=0.6
+ dataset_batch_size_map=(['AIME24']='16' ['AIME25']='16' ['AMC23']='16' ['MATH500']='64' ['Minerva']='64' ['OlympiadBench']='64')
+ declare -A dataset_batch_size_map
+ dataset_rollout_n_map=(['AIME24']='16' ['AIME25']='16' ['AMC23']='16' ['MATH500']='8' ['Minerva']='8' ['OlympiadBench']='8')
+ declare -A dataset_rollout_n_map
+ train_file=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet
+ solver_batch_size=64
+ rollout_n=8
+ echo '[Config] dataset: Minerva, solver_batch_size: 64, rollout_n: 8, train_file: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet'
[Config] dataset: Minerva, solver_batch_size: 64, rollout_n: 8, train_file: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet
+ group_question_repetion_penalty=True
+ gen_question_func=ttrl_icl
+ hybrid_data=True
+ '[' 8 -eq 4 ']'
+ challenger_training_steps=5
+ solver_training_steps=15
+ variant=data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B
+ exp_name=data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1
+ solver_retrain_steps=15
+ solver_eval_step=15
+ solver_eval_temperature=0.6
+ solver_eval_num_iter=15
+ mkdir -p /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Solver_ttrl /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/tensorboard_log /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/logs
+ exec
+++ now
+++ date +%Y-%m-%d-%H-%M
++ tee -a /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/logs/train_data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-2026-03-01-21-08.log
+ cd /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS
+ echo 'Starting round 1 training...'
Starting round 1 training...
+ echo 'Training Challenger...'
Training Challenger...
+ bash /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script/challenger.sh data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1 /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B 5 TTCS True ttrl_icl /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/data/ttrl/Minerva.parquet
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
[exp_name]:data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1
[challenger_model_path]: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B
[solver_model_path]: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B
[challenger_training_steps]: 5
[Path Config] Working Dir: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS
[Path Config] Prompt Dir: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src
[Path Config] Storage Path: /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl/data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V1
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
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
/usr/local/lib/python3.12/dist-packages/torch/cuda/__init__.py:63: FutureWarning: The pynvml package is deprecated. Please install nvidia-ml-py instead. If you did not install pynvml directly, please report this to the maintainers of the package that installed pynvml for you.
  import pynvml  # type: ignore[import]
W0301 21:19:44.692000 14322 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:19:44.692000 14322 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
WARNING:2026-03-01 21:19:44,700:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-01 21:19:44,741:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-01 21:19:44,755:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-01 21:19:44,759:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
WARNING:2026-03-01 21:19:44,784:fused_indices_to_multihot has reached end of life. Please migrate to a non-experimental function.
W0301 21:19:47.835000 14322 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:19:47.835000 14322 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:19:50.082000 14323 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:19:50.082000 14323 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:19:52.437000 14339 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:19:52.437000 14339 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:19:54.872000 14324 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:19:54.872000 14324 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
W0301 21:19:55.579000 14321 torch/utils/cpp_extension.py:2425] TORCH_CUDA_ARCH_LIST is not set, all archs for visible cards are included for compilation. 
W0301 21:19:55.579000 14321 torch/utils/cpp_extension.py:2425] If this is not desired, please set os.environ['TORCH_CUDA_ARCH_LIST'] to specific architectures.
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-01 21:20:51 [__init__.py:216] Automatically detected platform cuda.
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-01 21:20:51 [__init__.py:216] Automatically detected platform cuda.
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-01 21:20:51 [__init__.py:216] Automatically detected platform cuda.
[idle_worker] GPU idle worker started.
[main] GPU idle worker thread started.
[init] Loading model...
[init] Pausing GPU idle worker for model initialization...
[idle_worker] Paused.
INFO 03-01 21:20:51 [__init__.py:216] Automatically detected platform cuda.
[2026-03-01 21:21:20,450 W 14339 14339] rpc_client.h:153: Failed to connect to GCS at address 10.148.45.68:54119 within 5 seconds.
[2026-03-01 21:21:50,451 W 14339 14339] gcs_client.cc:205: Failed to get cluster ID from GCS server: TimedOut: Timed out while waiting for GCS to become available.
INFO 03-01 21:22:16 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-01 21:22:18 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-01 21:22:18 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
INFO 03-01 21:22:26 [utils.py:233] non-default args: {'tokenizer': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B', 'gpu_memory_utilization': 0.95, 'disable_log_stats': True, 'model': '/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B'}
2026-03-01 21:22:53,029 ERROR services.py:1342 -- Failed to start the dashboard 
2026-03-01 21:22:53,029 ERROR services.py:1367 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-01 21:22:53,030 ERROR services.py:1377 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-01_21-21-15_411438_14339/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-01 21:22:53,030 ERROR services.py:1411 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-01_21-21-15_411438_14339/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-01 21:22:53,038 WARNING services.py:2137 -- WARNING: The object store is using /tmp instead of /dev/shm because /dev/shm has only 1073618944 bytes available. This will harm performance! You may be able to free up space by deleting files in /dev/shm. If you are inside a Docker container, you can increase /dev/shm size by passing '--shm-size=10.24gb' to 'docker run' (or add it to the run_options list in a Ray cluster config). Make sure to set this to more than 30% of available RAM.
2026-03-01 21:23:23,193 INFO node.py:362 -- Failed to get node info b'RPC error: Deadline Exceeded'
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
hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ Error: Round 1 Challenger training failed
+ exit 1
INFO 03-01 21:25:50 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-01 21:25:50 [model.py:1510] Using max model len 4096
INFO 03-01 21:25:50 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-01 21:25:57 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-01 21:25:57 [model.py:1510] Using max model len 4096
INFO 03-01 21:25:57 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
INFO 03-01 21:26:00 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-01 21:26:00 [model.py:1510] Using max model len 4096
INFO 03-01 21:26:00 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
^C
hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ ^C
hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ INFO 03-01 21:26:13 [model.py:547] Resolved architecture: Qwen2ForCausalLM
`torch_dtype` is deprecated! Use `dtype` instead!
INFO 03-01 21:26:13 [model.py:1510] Using max model len 4096
INFO 03-01 21:26:13 [scheduler.py:205] Chunked prefill is enabled with max_num_batched_tokens=16384.
^C
hadoop-ai-search@psx3eevxria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ ^C
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
