hadoop-ai-search@psx3g5axria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ ray start --head --num-cpus=4
Enable usage stats collection? This prompt will auto-proceed in 10 seconds to avoid blocking cluster startup. Confirm [Y/n]: 
Usage stats collection is enabled. To disable this, add `--disable-usage-stats` to the command that starts the cluster, or run the following command: `ray disable-usage-stats` before starting the cluster. See https://docs.ray.io/en/master/cluster/usage-stats.html for more details.

Local node IP: 10.166.166.106
[2026-03-01 22:48:01,851 W 6578 6578] rpc_client.h:153: Failed to connect to GCS at address 10.166.166.106:6379 within 5 seconds.
2026-03-01 22:49:06,144 ERROR services.py:1342 -- Failed to start the dashboard 
2026-03-01 22:49:06,144 ERROR services.py:1367 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-01 22:49:06,144 ERROR services.py:1377 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-01_22-47-56_833396_6578/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-01 22:49:06,144 ERROR services.py:1411 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-01_22-47-56_833396_6578/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
2026-03-01 22:49:40,889 INFO node.py:362 -- Failed to get node info b'GCS cannot find the node with node ID eb463be6bdb38f6c9d2b2e1d23912b0934a81ee920ac23e91b01a6bc. The node registration may not be complete yet before the timeout. Try increase the RAY_raylet_start_wait_time_s config.'
Traceback (most recent call last):
  File "/usr/local/bin/ray", line 7, in <module>
    sys.exit(main())
             ^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/scripts/scripts.py", line 2758, in main
    return cli()
           ^^^^^
  File "/usr/local/lib/python3.12/dist-packages/click/core.py", line 1485, in __call__
    return self.main(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/click/core.py", line 1406, in main
    rv = self.invoke(ctx)
         ^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/click/core.py", line 1873, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/click/core.py", line 1269, in invoke
    return ctx.invoke(self.callback, **ctx.params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/click/core.py", line 824, in invoke
    return callback(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/autoscaler/_private/cli_logger.py", line 823, in wrapper
    return f(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/scripts/scripts.py", line 946, in start
    node = ray._private.node.Node(
           ^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/dist-packages/ray/_private/node.py", line 364, in __init__
    raise Exception(
Exception: The current node timed out during startup. This could happen because some of the raylet failed to startup or the GCS has become overloaded.
hadoop-ai-search@psx3g5axria5um28-worker-0:/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05$ 
