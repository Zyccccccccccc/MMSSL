(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'

2026-03-03 19:37:18,953 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'node:__internal_head__': 1.0, 'node:10.148.63.41': 1.0, 'memory': 900424326758.0, 'CPU': 56.0, 'GPU': 8.0, 'accelerator_type:A800': 1.0, 'object_store_memory': 102005465497.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ RAY_gcs_rpc_server_reconnect_timeout_s=60 python -c 'import ray; ray.init(include_dashboard=False); print("Ray init success", ray.cluster_resources()); ray.shutdown()'
2026-03-03 19:47:23,421 INFO worker.py:1951 -- Started a local Ray instance.
Ray init success {'CPU': 56.0, 'accelerator_type:A800': 1.0, 'node:__internal_head__': 1.0, 'object_store_memory': 102005465497.0, 'node:10.148.63.41': 1.0, 'memory': 900423188070.0, 'GPU': 8.0}
(base) [hadoop-ai-search@psx3gw6xria5rpsd-worker-0 docker]$ 

export RAY_raylet_start_wait_time_s=60


Waiting for vLLM service to start...
Starting main training process...
Using GPU: 0,1,2,3, total 4
INFO 03-03 22:40:18 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 22:40:18 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 22:40:18 __init__.py:190] Automatically detected platform cuda.
INFO 03-03 22:40:18 __init__.py:190] Automatically detected platform cuda.
Traceback (most recent call last):
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/utils.py", line 220, in run_and_report
    return func()
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/utils.py", line 458, in <lambda>
    lambda: hydra.run(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/hydra.py", line 105, in run
    cfg = self.compose_config(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/hydra.py", line 594, in compose_config
    cfg = self.config_loader.load_configuration(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/config_loader_impl.py", line 142, in load_configuration
    return self._load_configuration_impl(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/config_loader_impl.py", line 253, in _load_configuration_impl
    defaults_list = create_defaults_list(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 745, in create_defaults_list
    defaults, tree = _create_defaults_list(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 715, in _create_defaults_list
    defaults_tree = _create_defaults_tree(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 356, in _create_defaults_tree
    ret = _create_defaults_tree_impl(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 457, in _create_defaults_tree_impl
    return _expand_virtual_root(repo, root, overrides, skip_missing)
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 280, in _expand_virtual_root
    subtree = _create_defaults_tree_impl(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 573, in _create_defaults_tree_impl
    add_child(children, new_root)
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 520, in add_child
    subtree_ = _create_defaults_tree_impl(
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 466, in _create_defaults_tree_impl
    update_package_header(repo=repo, node=parent)
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/defaults_list.py", line 262, in update_package_header
    loaded = repo.load_config(config_path=node.get_config_path())
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/config_repository.py", line 348, in load_config
    ret = self.delegate.load_config(config_path=config_path)
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/config_repository.py", line 91, in load_config
    ret = source.load_config(config_path=config_path)
  File "/usr/local/conda/lib/python3.10/site-packages/hydra/_internal/core_plugins/file_config_source.py", line 31, in load_config
    cfg = OmegaConf.load(f)
  File "/usr/local/conda/lib/python3.10/site-packages/omegaconf/omegaconf.py", line 192, in load
    obj = yaml.load(file_, Loader=get_yaml_loader())
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/__init__.py", line 81, in load
    return loader.get_single_data()
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/constructor.py", line 49, in get_single_data
    node = self.get_single_node()
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/composer.py", line 36, in get_single_node
    document = self.compose_document()
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/composer.py", line 55, in compose_document
    node = self.compose_node(None, None)
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/composer.py", line 84, in compose_node
    node = self.compose_mapping_node(anchor)
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/composer.py", line 133, in compose_mapping_node
    item_value = self.compose_node(node, item_key)
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/composer.py", line 84, in compose_node
    node = self.compose_mapping_node(anchor)
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/composer.py", line 127, in compose_mapping_node
    while not self.check_event(MappingEndEvent):
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/parser.py", line 98, in check_event
    self.current_event = self.state()
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/parser.py", line 428, in parse_block_mapping_key
    if self.check_token(KeyToken):
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/scanner.py", line 116, in check_token
    self.fetch_more_tokens()
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/scanner.py", line 223, in fetch_more_tokens
    return self.fetch_value()
  File "/usr/local/conda/lib/python3.10/site-packages/yaml/scanner.py", line 577, in fetch_value
    raise ScannerError(None, None,
yaml.scanner.ScannerError: mapping values are not allowed here
  in "/mnt/dolphinfs/ssd_pool/docker/user/hadoop-ai-search/zhangyuchao05/TTCS-base/TTCS/verl/trainer/config/ppo_trainer.yaml", line 324, column 30
+ echo 'Error: Round 1 Challenger training failed'
Error: Round 1 Challenger training failed
