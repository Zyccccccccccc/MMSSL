(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ray stop --force && rm -rf /tmp/ray/ && python -c 'import ray; ray.init(_system_config={"gcs_rpc_server_reconnect_timeout_s": 60}); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

Did not find any active Ray processes.
[2026-03-03 19:15:27,458 W 91687 91687] gcs_rpc_client.h:155: Failed to connect to GCS at address 10.148.63.41:46101 within 5 seconds.
2026-03-03 19:15:50,985 ERROR services.py:1357 -- Failed to start the dashboard 
2026-03-03 19:15:50,986 ERROR services.py:1382 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-03 19:15:50,986 ERROR services.py:1392 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_19-15-22_444268_91687/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-03 19:15:50,986 ERROR services.py:1426 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-03_19-15-22_444268_91687/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
