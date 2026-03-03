(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ env | grep -i ray
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ cat ~/.ray/ray-client.cfg 2>/dev/null; cat /tmp/ray_bootstrap_config.yaml 2>/dev/null; find ~ -name ".ray" 2>/dev/null
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ python -c 'import ray; ray.init(address="local", include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'python -c 'import ray; ray.init(address="local", include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'^C
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ python -c 'import ray; ray.init(address="local", include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
[2026-03-03 19:22:00,869 W 98087 98087] gcs_rpc_client.h:155: Failed to connect to GCS at address 10.148.63.41:64979 within 5 seconds.
2026-03-03 19:22:24,200 ERROR services.py:1357 -- Failed to start the dashboard 
2026-03-03 19:22:24,201 ERROR services.py:1382 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-03 19:22:24,201 ERROR services.py:1392 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_19-21-55_856125_98087/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-03 19:22:24,201 ERROR services.py:1426 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_19-21-55_856125_98087/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-03 19:22:55,914 INFO node.py:355 -- Failed to get node info b'GCS cannot find the node with node ID 83b79a0f5772c70e9783c20b64a50b45edfdec5b385a197085614eee. The node registration may not be complete yet before the timeout. Try increase the RAY_raylet_start_wait_time_s config.'
Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/client_mode_hook.py", line 104, in wrapper
    return func(*args, **kwargs)
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/worker.py", line 1849, in init
    _global_node = ray._private.node.Node(
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/node.py", line 357, in __init__
    raise Exception(
Exception: The current node timed out during startup. This could happen because some of the raylet failed to startup or the GCS has become overloaded.
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ 
