(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ cd user/hadoop-ai-search/zhangyuchao05/
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 zhangyuchao05]$ ray start --head --num-cpus=4
Enable usage stats collection? This prompt will auto-proceed in 10 seconds to avoid blocking cluster startup. Confirm [Y/n]: 
Usage stats collection is enabled. To disable this, add `--disable-usage-stats` to the command that starts the cluster, or run the following command: `ray disable-usage-stats` before starting the cluster. See https://docs.ray.io/en/master/cluster/usage-stats.html for more details.

Local node IP: 10.148.63.41
[2026-03-02 01:05:59,269 W 30610 30610] gcs_rpc_client.h:155: Failed to connect to GCS at address 10.148.63.41:6379 within 5 seconds.
2026-03-02 01:06:22,126 ERROR services.py:1357 -- Failed to start the dashboard 
2026-03-02 01:06:22,126 ERROR services.py:1382 -- Error should be written to 'dashboard.log' or 'dashboard.err'. We are printing the last 20 lines for you. See 'https://docs.ray.io/en/master/ray-observability/user-guides/configure-logging.html#logging-directory-structure' to find where the log file is.
2026-03-02 01:06:22,127 ERROR services.py:1392 -- Couldn't read dashboard.log file. Error: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-02_01-05-54_248905_30610/logs/dashboard.log'. It means the dashboard is broken even before it initializes the logger (mostly dependency issues). Reading the dashboard.err file which contains stdout/stderr.
2026-03-02 01:06:22,127 ERROR services.py:1426 -- Failed to read dashboard.err file: [Errno 2] No such file or directory: '/tmp/ray/session_2026-03-02_01-05-54_248905_30610/logs/dashboard.err'. It is unexpected. Please report an issue to Ray github. https://github.com/ray-project/ray/issues
