(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 

export RAY_raylet_start_wait_time_s=60


(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 zhangyuchao05]$ rm -rf /tmp/ray
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 zhangyuchao05]$ export RAY_raylet_start_wait_time_s=300
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 zhangyuchao05]$ export RAY_gcs_rpc_server_reconnect_timeout_s=120
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 zhangyuchao05]$ ray start --head --include-dashboard=false --num-cpus=4

Enable usage stats collection? This prompt will auto-proceed in 10 seconds to avoid blocking cluster startup. Confirm [Y/n]:                                                                                                               Invalid answer: ray status. Expected y/yes/true/1 or n/no/false/0
                                                                                                              Confirm [Y/n]: Usage stats collection is enabled. To disable this, add `--disable-usage-stats` to the command that starts the cluster, or run the following command: `ray disable-usage-stats` before starting the cluster. See https://docs.ray.io/en/master/cluster/usage-stats.html for more details.

Local node IP: 10.166.176.28
2026-03-04 14:10:51,595 ERROR services.py:1357 -- Failed to start the dashboard 
2026-03-04 14:10:51,595 ERROR services.py:1382 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-04 14:10:51,595 ERROR services.py:1392 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-04_14-10-26_302680_258613/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-04 14:10:51,595 ERROR services.py:1426 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-04_14-10-26_302680_258613/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues

--------------------
Ray runtime started.
--------------------

Next steps
  To add another node to this Ray cluster, run
    ray start --address='10.166.176.28:6379'
  
  To connect to this Ray cluster:
    import ray
    ray.init()
  
  To terminate the Ray runtime, run
    ray stop
  
  To view the status of the cluster, use
    ray status
(base) [hadoop-ai-search@psx3z03xriad1qir-worker-0 zhangyuchao05]$ 
