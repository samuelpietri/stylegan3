
# General Information

### Multi class  labeling 
Found info [here](https://github.com/NVlabs/stylegan2-ada-pytorch/issues/111)

## Create Labels
```bash
python make_json_labels.py --input_folder=/path-to-stylegan/multiclass-images-directory \
 --output_folder=/path-to-stylegan/path-to-output-dataset
```
**Rembemer to check the path into the json file, replace any "\\" wihth "/"**
**TODO**
**Modify make_json_lables.py to accomodate for that**
 
### Create Dataset
```bash
python dataset_tool.py --source=/run/user/1000/gvfs/smb-share:server=rockstationfuse.local,share=fuse/Delivery/Catalogue/Falin\ Mynd/_PRODUCTION/datasets/helsinki/helsinki_cathedral_1024 
--dest=/home/kobe/DL/gan/stylegan3-custom/datasets/countryside.zip helsinki_cathedral.zip
```

### Training
**Training. Rtx 3090 -  STYLEGAN3**
```bash
python train.py --outdir=~/training-runs --cfg=stylegan3-r --data=~/datasets/metfacesu-1024x1024.zip \
    --gpus=1 --batch=32 --gamma=6.6 --mirror=1 --kimg=5000 --snap=2 \
    --resume=ffhqu1024
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan3-r --data=./datasets/helsinki_cathedral.zip \
    --batch=32  --gpus=1 --batch-gpu=4 --gamma=0.5 --mirror=1 --kimg=5000 --snap=2   \
    --resume=ffhqu1024 --aug=noaug --img-snap=1
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan3-r --data=d:/DL/stylegan3/repository/stylegan3/dataset/AB_test_003.zip \
    --batch=32  --gpus=1 --batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=5000 --snap=2   \
    --aug=noaug --img-snap=1 --metrics=none --dlr=0.004 --glr=0.0001 --resume=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00006-stylegan3-r-AB_test_003-gpus1-batch32-gamma6.6-no_resume/network-snapshot-000040.pkl
```
**Training. Rtx 3090 -  STYLEGAN2-ADA**
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./datasets/countryside.zip  --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \     
--resume=/home/kobe/DL/gan/stylegan3-custom/~/training-runs/00009-stylegan2-countryside-gpus1-batch32-gamma6.6/network-snapshot-000232.pkl  --metrics=none 
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./datasets/aldrovandi_illustrations_001.zip  --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=/home/kobe/DL/gan/stylegan3-custom/stylegan3-nvidia-models/stylegan2_1/stylegan2-ffhq-1024x1024.pkl --metrics=none
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./dataset/AB_SD_composition.zip  --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/pretrained/stylegan2-ffhq-1024x1024.pkl --metrics=none
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./dataset/AB_test_003.zip  --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00002-stylegan2-AB_test_002-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000568.pkl --metrics=none --aug=noaug --img-snap=1
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./dataset/AB_test_004_leaves_autumn.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00009-stylegan2-AB_test_003-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000296.pkl --metrics=none --aug=noaug --img-snap=1
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./dataset/AB_test_005_autumn.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00009-stylegan2-AB_test_003-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000296.pkl --metrics=none --aug=noaug --img-snap=1
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./dataset/AB_test_flowers_mix.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00014-stylegan2-AB_test_006_flowers-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000032.pkl --metrics=none --aug=noaug --img-snap=1
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=./dataset/AB_test_autumn_mix.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00013-stylegan2-AB_test_005_autumn-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000040.pkl --metrics=none --aug=noaug --img-snap=1
```
Artificial Botany - Stable Diffusion 
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=d:/DL/stylegan3/repository/stylegan3/dataset/AB_SD_nft_test.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/pretrained/stylegan2-ffhq-1024x1024.pkl --metrics=none --aug=noaug --img-snap=1
```

```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=d:/DL/stylegan3/repository/stylegan3/dataset/1024_AB_mix_001.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/pretrained/stylegan2-ffhq-1024x1024.pkl --metrics=none --aug=noaug --img-snap=1
```

with labels
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=d:/DL/stylegan3/data/AB_light_background/1024 --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--metrics=none --aug=noaug --img-snap=1 --cond=True
```
```bash
python train.py --outdir=~/training-runs --cfg=stylegan2 \
--data=d:/DL/stylegan3/repository/stylegan3/dataset/square_botany.zip --batch=32  --gpus=1 \
--batch-gpu=4 --gamma=6.6 --mirror=1 --kimg=10000 --snap=2 \
--resume=d:/DL/stylegan3/repository/stylegan3/pretrained/stylegan2-ffhq-1024x1024.pkl --metrics=none --aug=noaug --img-snap=1
```



### Generation
```bash
python gen_video.py --network=/d/DL/stylegan2/models/ada_models/00013-waves-res1024-11gb-gpu-ada-bgc-resumecustom/network-snapshot-000112.pkl \
 --w-frames=480 --trunc=0.5 --output=waves_002_slow.mp4 --seeds=1000-1050
```
```bash
python gen_video.py --network=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00002-stylegan2-AB_test_002-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000576.pkl \
 --w-frames=240 --trunc=0.8 --output=AB_SD_composition_001.mp4 --seeds=1000-1050
```
```bash
python gen_video.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/Aldrovandi/models/stylegan2-ADA/Illustrations/network-snapshot-000496.pkl \
--w-frames=300 --trunc=0.9 \
--output=Aldro_Illustration_002.mp4 --seeds=1000-1083
```

python gen_video.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/stylegan_models/Botanical_Forest/final/network-snapshot-010990.pkl \
 --w-frames=240 --trunc=0.8 --output=AB_Botanical_forest_composition_001.mp4 --seeds=1000-1010

Aldrovandi - Marignana video
```bash
python gen_video.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/Aldrovandi/models/stylegan2-ADA/Illustrations/network-snapshot-000496.pkl \
--w-frames=300 --trunc=0.9 \
--output=Aldro_Illustration_002.mp4 --seeds=182,197,208,242,105,391,266,334,76,300,384,165,58,147,214,126,76,361,275,259,38,106,102,336,133,349,274,236,358,274,298,100,288,342,131,85,35,287,196,219,303,365,333,172,245,306,346,377,224,132,787,708,530,420,504,491,637,526,585,720,670,419,719,487,572,600,463,646,771,775,429,501,667,762,614,442,598,755,555,517,700,412,468,547,719,543,524,800,715,463
```

```bash
python gen_video.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/Aldrovandi/models/stylegan2-ADA/Erbario_Illustrations_Transfer/network-snapshot-000016.pkl \
--w-frames=300 --trunc=0.9 \
--output=Aldro_Illustration_003.mp4 --seeds=182,197,208,242,105,391,266,334,76,300,384,165,58,147,214,126,76,361,275,259,38,106,102,336,133,349,274,236,358,274,298,100,288,342,131,85,35,287,196,219,303,365,333,172,245,306,346,377,224,132,787,708,530,420,504,491,637,526,585,720,670,419,719,487,572,600,463,646,771,775,429,501,667,762,614,442,598,755,555,517,700,412,468,547,719,543,524,800,715,463
```


```bash
python gen_video.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/Aldrovandi/models/stylegan2-ADA/Erbario/network-snapshot-000432.pkl \
--w-frames=300 --trunc=0.9 \
--output=Aldro_Illustration_004.mp4 --seeds=182,197,208,242,105,391,266,334,76,300,384,165,58,147,214,126,76,361,275,259,38,106,102,336,133,349,274,236,358,274,298,100,288,342,131,85,35,287,196,219,303,365,333,172,245,306,346,377,224,132,787,708,530,420,504,491,637,526,585,720,670,419,719,487,572,600,463,646,771,775,429,501,667,762,614,442,598,755,555,517,700,412,468,547,719,543,524,800,715,463
```

python gen_video.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/stylegan_models/Aldrovandi/stylegan2-ada/selected/erbario_secco_network-snapshot-000416.pkl \
--w-frames=60 --trunc=1.0 \
--output=Aldro_Illustration_Secco_infinite_001.mp4 --seeds=495,517,582,564,337,731,282,676,621,415,495


### Custom Export Multiple videos at once
```bash
python gen_video_custom.py --network=d:/DL/stylegan3/repository/stylegan3/~/training-runs/00009-stylegan2-AB_SD_nft_test-gpus1-batch32-gamma6.6-resume_custom/network-snapshot-000424.pkl --w-frames=300 --trunc=1.2 --num-keyframes=36 --num_video=413
```
SEOUL
```bash
python gen_video_custom.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/stylegan_models/Botanical_Forest/final/network-snapshot-010990.pkl --w-frames=400 --num_seeds=162 --num_seeds_step=27  --trunc=0.8 --num_video=11 --output=ehy.mp4
```

UNSEEN FLORA CHINA
```bash
python gen_video_custom.py --network=//192.168.1.31/fuse/Delivery/Catalogue/Artificial\ Botany/_PRODUCTION/stylegan_models/botany/network-snapshot-010597.pkl  --w-frames=300 --num_seeds=30 --num_seeds_step=27  --trunc=0.8 --num_video=4 --output=Unseen_Flora_.mp4
```
