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

python federatedscope/main.py --cfg federatedscope/gfl/baseline/isolated_gin_minibatch_on_cikmcup.yaml --client_cfg federatedscope/gfl/baseline/isolated_gin_minibatch_on_cikmcup_per_client.yaml

# Brief introduction of the developed algorithm
