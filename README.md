RAY_raylet_start_wait_time_s=60 python -c 'import ray; ray.init(address="local", include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
