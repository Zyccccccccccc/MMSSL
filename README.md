(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ python3 -c "import ray; ray.init(address='auto'); print('Ray is alive:', ray.is_initialized())"

Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/client_mode_hook.py", line 104, in wrapper
    return func(*args, **kwargs)
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/worker.py", line 1768, in init
    bootstrap_address = services.canonicalize_bootstrap_address(address, _temp_dir)
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/services.py", line 523, in canonicalize_bootstrap_address
    addr = get_ray_address_from_environment(addr, temp_dir)
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/services.py", line 410, in get_ray_address_from_environment
    raise ConnectionError(
ConnectionError: Could not find any running Ray instance. Please specify the one to connect to by setting `--address` flag or `RAY_ADDRESS` environment variable.
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ 
