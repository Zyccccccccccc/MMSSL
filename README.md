这是使用verl0.5的docker镜像的输出：1.1.0 (from bleach[css]!=5.0.0->nbconvert->jupyter)
  Downloading http://pip.sankuai.com/packages/e6/34/ebdc18bae6aa14fbee1a08b63c015c72b64868ff7dae68808ab500c492e2/tinycss2-1.4.0-py3-none-any.whl (26 kB)
Collecting fastjsonschema>=2.15 (from nbformat>=5.3.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter)
  Downloading http://pip.sankuai.com/packages/cb/a8/20d0723294217e47de6d9e2e40fd4a9d2f7c4b6ef974babd482a59743694/fastjsonschema-2.21.2-py3-none-any.whl (24 kB)
Requirement already satisfied: charset-normalizer<4,>=2 in /usr/local/conda/lib/python3.10/site-packages (from requests>=2.31->jupyterlab-server<3,>=2.28.0->jupyterlab->jupyter) (3.3.2)
Requirement already satisfied: urllib3<3,>=1.21.1 in /usr/local/conda/lib/python3.10/site-packages (from requests>=2.31->jupyterlab-server<3,>=2.28.0->jupyterlab->jupyter) (2.3.0)
Requirement already satisfied: cffi>=1.0.1 in /usr/local/conda/lib/python3.10/site-packages (from argon2-cffi-bindings->argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (1.17.1)
Requirement already satisfied: pycparser in /usr/local/conda/lib/python3.10/site-packages (from cffi>=1.0.1->argon2-cffi-bindings->argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (2.21)
Collecting soupsieve>=1.6.1 (from beautifulsoup4->nbconvert->jupyter)
  Downloading http://pip.sankuai.com/packages/46/2c/1462b1d0a634697ae9e55b3cecdcb64788e8b7d63f54d923fcd0bb140aed/soupsieve-2.8.3-py3-none-any.whl (37 kB)
Collecting arrow>=0.15.0 (from isoduration->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter)
  Downloading http://pip.sankuai.com/packages/ed/c9/d7977eaacb9df673210491da99e6a247e93df98c715fc43fd136ce1d3d33/arrow-1.4.0-py3-none-any.whl (68 kB)
Requirement already satisfied: tzdata in /usr/local/conda/lib/python3.10/site-packages (from arrow>=0.15.0->isoduration->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (2025.2)
Requirement already satisfied: executing>=1.2.0 in /usr/local/conda/lib/python3.10/site-packages (from stack_data->ipython>=7.23.1->ipykernel->jupyter) (2.2.1)
Requirement already satisfied: asttokens>=2.1.0 in /usr/local/conda/lib/python3.10/site-packages (from stack_data->ipython>=7.23.1->ipykernel->jupyter) (3.0.0)
Requirement already satisfied: pure-eval in /usr/local/conda/lib/python3.10/site-packages (from stack_data->ipython>=7.23.1->ipykernel->jupyter) (0.2.3)
Installing collected packages: webencodings, fastjsonschema, widgetsnbextension, websocket-client, webcolors, uri-template, tornado, tinycss2, soupsieve, send2trash, rfc3986-validator, rfc3339-validator, python-json-logger, pandocfilters, overrides, mistune, jupyterlab_widgets, jupyterlab-pygments, jupyter-core, json5, fqdn, defusedxml, debugpy, comm, bleach, babel, terminado, jupyter-client, beautifulsoup4, arrow, argon2-cffi-bindings, jupyter-server-terminals, jsonschema, isoduration, ipywidgets, ipykernel, argon2-cffi, nbformat, jupyter-console, nbclient, jupyter-events, nbconvert, jupyter-server, notebook-shim, jupyterlab-server, jupyter-lsp, jupyterlab, notebook, jupyter

Successfully installed argon2-cffi-25.1.0 argon2-cffi-bindings-25.1.0 arrow-1.4.0 babel-2.18.0 beautifulsoup4-4.14.3 bleach-6.3.0 comm-0.2.3 debugpy-1.8.20 defusedxml-0.7.1 fastjsonschema-2.21.2 fqdn-1.5.1 ipykernel-7.2.0 ipywidgets-8.1.8 isoduration-20.11.0 json5-0.13.0 jsonschema-4.24.1 jupyter-1.1.1 jupyter-client-8.8.0 jupyter-console-6.6.3 jupyter-core-5.9.1 jupyter-events-0.12.0 jupyter-lsp-2.3.0 jupyter-server-2.17.0 jupyter-server-terminals-0.5.4 jupyterlab-4.5.5 jupyterlab-pygments-0.3.0 jupyterlab-server-2.28.0 jupyterlab_widgets-3.0.16 mistune-3.2.0 nbclient-0.10.4 nbconvert-7.17.0 nbformat-5.10.4 notebook-7.5.4 notebook-shim-0.2.4 overrides-7.7.0 pandocfilters-1.5.1 python-json-logger-4.0.0 rfc3339-validator-0.1.4 rfc3986-validator-0.1.1 send2trash-2.1.0 soupsieve-2.8.3 terminado-0.18.1 tinycss2-1.4.0 tornado-6.5.4 uri-template-1.3.0 webcolors-25.10.0 webencodings-0.5.1 websocket-client-1.9.0 widgetsnbextension-4.0.15


这是原先使用verl0.7的镜像的输出：schema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (20.11.0)
Requirement already satisfied: jsonpointer>1.13 in /usr/local/lib/python3.12/dist-packages (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (3.0.0)
Requirement already satisfied: rfc3987-syntax>=1.1.0 in /usr/local/lib/python3.12/dist-packages (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (1.1.0)
Requirement already satisfied: uri-template in /usr/local/lib/python3.12/dist-packages (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (1.3.0)
Requirement already satisfied: webcolors>=24.6.0 in /usr/local/lib/python3.12/dist-packages (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (25.10.0)
Requirement already satisfied: beautifulsoup4 in /usr/local/lib/python3.12/dist-packages (from nbconvert->jupyter) (4.14.3)
Requirement already satisfied: bleach!=5.0.0 in /usr/local/lib/python3.12/dist-packages (from bleach[css]!=5.0.0->nbconvert->jupyter) (6.3.0)
Requirement already satisfied: defusedxml in /usr/local/lib/python3.12/dist-packages (from nbconvert->jupyter) (0.7.1)
Requirement already satisfied: jupyterlab-pygments in /usr/local/lib/python3.12/dist-packages (from nbconvert->jupyter) (0.3.0)
Requirement already satisfied: mistune<4,>=2.0.3 in /usr/local/lib/python3.12/dist-packages (from nbconvert->jupyter) (3.2.0)
Requirement already satisfied: nbclient>=0.5.0 in /usr/local/lib/python3.12/dist-packages (from nbconvert->jupyter) (0.10.4)
Requirement already satisfied: pandocfilters>=1.4.1 in /usr/local/lib/python3.12/dist-packages (from nbconvert->jupyter) (1.5.1)
Requirement already satisfied: webencodings in /usr/local/lib/python3.12/dist-packages (from bleach!=5.0.0->bleach[css]!=5.0.0->nbconvert->jupyter) (0.5.1)
Requirement already satisfied: tinycss2<1.5,>=1.1.0 in /usr/local/lib/python3.12/dist-packages (from bleach[css]!=5.0.0->nbconvert->jupyter) (1.4.0)
Requirement already satisfied: fastjsonschema>=2.15 in /usr/local/lib/python3.12/dist-packages (from nbformat>=5.3.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (2.21.2)
Requirement already satisfied: charset_normalizer<4,>=2 in /usr/local/lib/python3.12/dist-packages (from requests>=2.31->jupyterlab-server<3,>=2.28.0->jupyterlab->jupyter) (2.1.1)
Requirement already satisfied: urllib3<3,>=1.21.1 in /usr/local/lib/python3.12/dist-packages (from requests>=2.31->jupyterlab-server<3,>=2.28.0->jupyterlab->jupyter) (2.6.3)
Requirement already satisfied: lark>=1.2.2 in /usr/local/lib/python3.12/dist-packages (from rfc3987-syntax>=1.1.0->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (1.2.2)
Requirement already satisfied: cffi>=1.0.1 in /usr/local/lib/python3.12/dist-packages (from argon2-cffi-bindings->argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (2.0.0)
Requirement already satisfied: pycparser in /usr/local/lib/python3.12/dist-packages (from cffi>=1.0.1->argon2-cffi-bindings->argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (3.0)
Requirement already satisfied: soupsieve>=1.6.1 in /usr/local/lib/python3.12/dist-packages (from beautifulsoup4->nbconvert->jupyter) (2.8.3)
Requirement already satisfied: arrow>=0.15.0 in /usr/local/lib/python3.12/dist-packages (from isoduration->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (1.4.0)
Requirement already satisfied: tzdata in /usr/local/lib/python3.12/dist-packages (from arrow>=0.15.0->isoduration->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->jupyterlab->jupyter) (2025.3)
Refresh (1 sec) http://10.166.166.99:8420/lab?token=
eb9ed7fbccd72cc400b49cf0e9266ae656f59daa5d8f951e

This page should redirect you to a Jupyter application. If it doesn't, click
here to go to Jupyter.

为什么verl0.5的镜像不启动jupyrter了？

这是hope：# 表示作业的基本信息，自动填充，请勿修改
[base]
afo.app.name = "verl0.5"
type = ml-easy-job

[resource]
# usergroup = hadoop-dj-zproject
usergroup = hadoop-ai-search
queue = root.zw05_training_cluster.hadoop-djst.gpu_h

[roles]
workers = 1
worker.memory = 960000
worker.vcore = 64
worker.gcores80g = 8
# worker启动后执行的脚本，一般为训练作业的执行命令
worker.script = bash ./jupyter.sh

# worker端python脚本的输入参数
[user_args]

[am]
afo.app.am.resource.mb = 4096

[tensorboard]
with.tensor.board = false

# docker环境配置
[docker]
# registry-offlinebiz.sankuai.com/custom_prod/com.sankuai.phxmlp.mtjupyter.singleuser/mtsearch-assistant_training_cuda12.4.0_python3.10_flashatt_1.0.0_a35e60d6
afo.docker.image.name = registry-offlinebiz.sankuai.com/custom_prod/com.sankuai.data.hadoop.gpu/friday-llm/training_cuda12.4_python3.10_glibc2.31_torch2.6_fluentllm_vllm0.7.3_verl0.5_e60dce83:v1.2.0
# registry-offlinebiz.sankuai.com/custom_prod/com.sankuai.data.hadoop.gpu/friday-llm/training_cuda12.4_python3.10_glibc2.31_torch2.6_fluentllm_vllm0.7.3_verl0.5_e60dce83:v1.2.0
# registry-offlinebiz.sankuai.com/custom_prod/com.sankuai.data.hadoop.gpu/ai-search/training_ubuntu22_cuda12.8_python3.12_swift3.12.3_verl0.7.0_83a4cb59:v1.1.0
[data]
afo.data.prefetch=false

# 是否支持容错
[failover]
afo.app.support.engine.failover=false

[conda]
# afo.conda.env.name =
# afo.conda.env.path = 

[config]
# config.file =

[others]
# pytorch dataloader可能会用到共享内存，配置需要的共享内存（单位为B）
afo.app.env.YARN_CONTAINER_RUNTIME_DOCKER_SHM_SIZE_BYTES= 107374182400
afo.dolphinfs.otherusers = hadoop-mtsearch-assistant

with_requirements = false


这是jupyter，sh：#!/bin/bash
# http_proxy=http://172.18.130.72:8420
# https_proxy=http://172.18.130.72:8420

export PATH=$HOME/.local/bin:$PATH

IPS=`ifconfig -a|grep inet|grep -v 127.0.0.1|grep -v inet6|awk '{print $2}'|tr -d "addr:"`
array_=(${IPS})
IP=${array_[0]}

cd /mnt/dolphinfs/ssd_pool/docker
echo "Setting up jupyter ..."

which pip
which pip3
pip3 -V
python3 -m pip -V
python3 -V
which python3
python3 -m pip install jupyter -i http://pip.sankuai.com/simple --trusted-host pip.sankuai.com

pip3 list | grep

python3 -m jupyter lab --port 8420 --ip $IP

wait

我只换了afo.docker.image.name


