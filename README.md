python -c 'import ray; ray.init(address="local", include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
