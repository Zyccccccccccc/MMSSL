ray stop --force && rm -rf /tmp/ray/ && python -c 'import ray; ray.init(_system_config={"gcs_rpc_server_reconnect_timeout_s": 60}); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
