We use the FederatedScope framework, so first follow https://tianchi.aliyun.com/forum/postDetail?spm=5176.12281978.0.0.555e3ab4aJfzJs&postId=402279 to set up the FederatedScope, the contest data can be downloaded from https://tianchi.aliyun.com/competition/entrance/532008/information:

# To run the code

TODO: 

git clone https://github.com/chen0405/cikm.git

cd cikm

conda create -n fs python=3.9

conda activate fs

conda install -y pytorch=1.10.1 torchvision=0.11.2 torchaudio=0.10.1 cudatoolkit=11.3 -c pytorch -c conda-forge

python setup.py install

bash environment/extra_dependencies_torch1.10-application.sh

mkdir data

unzip -d ./data/ ${YOUR_OWN_PATH}/CIKM22Competition.zip

python federatedscope/main.py --cfg federatedscope/gfl/baseline/cfg.yaml --client_cfg federatedscope/gfl/baseline/client_cfg.yaml

# Brief introduction of the developed algorithm
Our method is based on the "isolated" baseline, we set hidden to 1024, batch_size to 16, weight_decay to 0.00005, total_round_num to 30, and modified some client's lr to prevent gradient explosion, more detail can be seen in federatedscope/gfl/baseline/cfg.yaml and federatedscope/gfl/baseline/client_cfg.yaml.
