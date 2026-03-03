(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 



hadoop-ai-search@psx3g5axria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
[2026-03-03 20:19:22,723 W 43685 43685] rpc_client.h:153: Failed to connect to GCS at address 10.166.166.106:43696 within 5 seconds.
2026-03-03 20:20:27,854 ERROR services.py:1342 -- Failed to start the dashboard 
2026-03-03 20:20:27,854 ERROR services.py:1367 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-03 20:20:27,854 ERROR services.py:1377 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_20-19-17_708795_43685/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-03 20:20:27,854 ERROR services.py:1411 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_20-19-17_708795_43685/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-03 20:20:49,555 INFO worker.py:2007 -- Started a local Ray instance.
