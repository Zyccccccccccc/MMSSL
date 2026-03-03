ray stop --force && rm -rf /tmp/ray /dev/shm/ray ~/.ray && ray start --head --node-ip-address=10.148.63.41 --port=6379 --num-cpus=4 --include-dashboard=false
