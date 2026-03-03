(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ss -tlnp | grep 6379
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ss -tlnp | grep 59374
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ray stop --force && rm -rf /tmp/ray/ && python -c "import ray; ray.init(_system_config={'gcs_rpc_server_reconnect_timeout_s': 60}); print('Ray init success!', ray.cluster_resources()); ray.shutdown()"
bash: !',: event not found
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ray stop --force && rm -rf /tmp/ray/ && python -c "import ray; ray.init(_system_config={'gcs_rpc_server_reconnect_timeout_s': 60}); print('Ray init success!', ray.cluster_resources()); ray.shutdown()"
bash: !',: event not found
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$  
