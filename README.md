python3 -c "import ray; ray.init(address='auto'); print('Ray is alive:', ray.is_initialized())"

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
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ray start --head --num-cpus=4 --include-dashboard=false
Usage stats collection is enabled. To disable this, add `--disable-usage-stats` to the command that starts the cluster, or run the following command: `ray disable-usage-stats` before starting the cluster. See https://docs.ray.io/en/master/cluster/usage-stats.html for more details.

Local node IP: 10.148.63.41
Traceback (most recent call last):
  File "/usr/local/conda/bin/ray", line 8, in <module>
    sys.exit(main())
  File "/usr/local/conda/lib/python3.10/site-packages/ray/scripts/scripts.py", line 2759, in main
    return cli()
  File "/usr/local/conda/lib/python3.10/site-packages/click/core.py", line 1442, in __call__
    return self.main(*args, **kwargs)
  File "/usr/local/conda/lib/python3.10/site-packages/click/core.py", line 1363, in main
    rv = self.invoke(ctx)
  File "/usr/local/conda/lib/python3.10/site-packages/click/core.py", line 1830, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/usr/local/conda/lib/python3.10/site-packages/click/core.py", line 1226, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/usr/local/conda/lib/python3.10/site-packages/click/core.py", line 794, in invoke
    return callback(*args, **kwargs)
  File "/usr/local/conda/lib/python3.10/site-packages/ray/autoscaler/_private/cli_logger.py", line 823, in wrapper
    return f(*args, **kwargs)
  File "/usr/local/conda/lib/python3.10/site-packages/ray/scripts/scripts.py", line 939, in start
    node = ray._private.node.Node(
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/node.py", line 333, in __init__
    self.start_head_processes()
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/node.py", line 1350, in start_head_processes
    self._write_cluster_info_to_kv()
  File "/usr/local/conda/lib/python3.10/site-packages/ray/_private/node.py", line 1312, in _write_cluster_info_to_kv
    assert curr_val == self._session_name.encode("utf-8"), (
AssertionError: Session name session_2026-03-02_01-23-13_532597_47601 does not match persisted value b'session_2026-03-02_01-05-54_248905_30610'. Perhaps there was an error connecting to Redis.
