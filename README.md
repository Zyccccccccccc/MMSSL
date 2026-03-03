(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 

export RAY_raylet_start_wait_time_s=60

(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 docker]$ bash user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script/run_with_gpus.sh 8
==============================================
  Self-evolving-Agent GPU Launcher
==============================================
Time: 2026-03-03 21:05:35

[INFO] 21:05:35 - Requested GPU count: 8

Current GPU Status:
----------------------------------------
GPU   Mem Used     Mem Total    Util       Status  
----------------------------------------
0     2MB          81920MB      0%         Idle    
1     2MB          81920MB      0%         Idle    
2     2MB          81920MB      0%         Idle    
3     2MB          81920MB      0%         Idle    
4     2MB          81920MB      0%         Idle    
5     2MB          81920MB      0%         Idle    
6     2MB          81920MB      0%         Idle    
7     2MB          81920MB      0%         Idle    
----------------------------------------
Idle threshold: Memory < 4000MB, Utilization < 5%

[INFO] 21:05:35 - Waiting for 8 idle GPUs...
[INFO] 21:05:35 - Check interval: 1800s, Max wait: 48h

[INFO] 21:05:35 - Current idle GPUs: 8 / Needed: 8
[INFO] 21:05:35 - GPU resources meet requirements!
[INFO] 21:05:35 - Selected GPUs: 0 1 2 3 4 5 6 7

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

[INFO] 21:05:35 - Starting training...

==============================================
  Starting main.sh
==============================================

+ export VLLM_WORKER_MULTIPROC_METHOD=spawn
+ VLLM_WORKER_MULTIPROC_METHOD=spawn
+ export PYTHONPATH=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/opt/eps/python/:/opt/fluentllm/python:/opt/flashmla/build/lib.linux-x86_64-cpython-310:/opt/rh/devtoolset-7/root/usr/lib64/python2.7/site-packages:/opt/rh/devtoolset-7/root/usr/lib/python2.7/site-packages:/workdir:/opt/rh/devtoolset-7/root/usr/lib64/python2.7/site-packages:/opt/rh/devtoolset-7/root/usr/lib/python2.7/site-packages:/opt/eps/python/:/opt/fluentllm/python:/opt/flashmla/build/lib.linux-x86_64-cpython-310:
+ PYTHONPATH=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS:/opt/eps/python/:/opt/fluentllm/python:/opt/flashmla/build/lib.linux-x86_64-cpython-310:/opt/rh/devtoolset-7/root/usr/lib64/python2.7/site-packages:/opt/rh/devtoolset-7/root/usr/lib/python2.7/site-packages:/workdir:/opt/rh/devtoolset-7/root/usr/lib64/python2.7/site-packages:/opt/rh/devtoolset-7/root/usr/lib/python2.7/site-packages:/opt/eps/python/:/opt/fluentllm/python:/opt/flashmla/build/lib.linux-x86_64-cpython-310:
+++ dirname /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script/main.sh
++ cd /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script
++ pwd
+ SCRIPT_DIR=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/src/script
+ export RAY_gcs_rpc_server_reconnect_timeout_s=60
+ RAY_gcs_rpc_server_reconnect_timeout_s=60
+ export RAY_raylet_start_wait_time_s=60
+ RAY_raylet_start_wait_time_s=60
+ base_model_name=Qwen2.5-Math-1.5B
+ base_model_path=/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/Qwen2.5-Math-1.5B
+ export RAY_gcs_rpc_server_reconnect_timeout_s=60
+ RAY_gcs_rpc_server_reconnect_timeout_s=60
+ question_reward=TTCS
+ dataset=Minerva
+ real_data_ratio=5.0
+ temperature=0.6
+ dataset_batch_size_map=(["AIME24"]=16 ["AIME25"]=16 ["AMC23"]=16 ["MATH500"]=64 ["Minerva"]=64 ["OlympiadBench"]=64)
+ declare -A dataset_batch_size_map
+ dataset_rollout_n_map=(["AIME24"]=16 ["AIME25"]=16 ["AMC23"]=16 ["MATH500"]=8 ["Minerva"]=8 ["OlympiadBench"]=8)
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
+ exp_name=data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-V2
+ solver_retrain_steps=15
+ solver_eval_step=15
+ solver_eval_temperature=0.6
+ solver_eval_num_iter=15
+ mkdir -p /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Synthesizer_ttrl /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/Solver_ttrl /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/saved_results/tensorboard_log /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/logs
+ exec
+++ now
+++ date +%Y-%m-%d-%H-%M
++ tee -a /mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/logs/train_data_Minerva_TTCS_gqttrl_icl_Qwen2.5-Math-1.5B-2026-03-03-21-05.log
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
INFO 03-03 21:10:53 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 21:10:54 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 21:10:54 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 21:10:54 __init__.py:190] Automatically detected platform cuda.
[2026-03-03 21:11:28,876 W 46008 46008] gcs_rpc_client.h:155: Failed to connect to GCS at address 10.166.176.28:50737 within 5 seconds.
2026-03-03 21:11:51,429 ERROR services.py:1357 -- Failed to start the dashboard 
2026-03-03 21:11:51,429 ERROR services.py:1382 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-03 21:11:51,430 ERROR services.py:1392 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_21-11-23_834911_46008/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-03 21:11:51,430 ERROR services.py:1426 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_21-11-23_834911_46008/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-03 21:12:16,599 INFO worker.py:1951 -- Started a local Ray instance.
[2026-03-03 21:12:46,736 E 46008 46008] core_worker_process.cc:232: Failed to register worker to Raylet: IOError: Failed to read data from the socket: End of file worker_id=01000000ffffffffffffffffffffffffffffffffffffffffffffffff

+ echo 'Error: Round 1 Challenger training failed'
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 docker]$ Error: Round 1 Challenger training failed
+ exit 1
^C
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 21:18:31,687 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'memory': 894437232640.0, 'CPU': 56.0, 'node:10.166.176.28': 1.0, 'GPU': 8.0, 'object_store_memory': 102005473280.0, 'accelerator_type:A800': 1.0}
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 docker]$ 
