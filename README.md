# Pose estimation project for RAAI summer school's CV track

Baseline for this project is entirely based on [AlphaPose multi-person pose estimator](https://github.com/MVIG-SJTU/AlphaPose).

## Instructions

- Clone AlphaPose into `baselines` directory **before building docker image**: 
    ```shell
    cd baselines/
    git clone https://github.com/MVIG-SJTU/AlphaPose.git
    cd AlphaPose/
    git pull origin pull/592/head
    ```

- **Manually fix** `baselines/AlphaPose/setup.py`: remove pycocotools installation (lines 171-172).

- Download the object detection model manually: **yolov3-spp.weights**([Google Drive](https://drive.google.com/open?id=1D47msNOOiJKvPOXlnpyzdKA3k6E97NTC) | [Baidu pan](https://pan.baidu.com/s/1Zb2REEIk8tcahDa8KacPNA)). Place it into `baselines/AlphaPose/detector/yolo/data`.

- Configure paths to datasets in `start.sh` script.

- Modify `baselines/AlphaPose/scripts/train.py`: train DataLoader (`line 201`) parameter `pin_memory=True`.

- Modify `baselines/AlphaPose/scripts/train.sh` script: add `CUDA_VISIBLE_DEVICES=` before `python3` command. 

- Other info in [AlphaPose documentation](https://github.com/MVIG-SJTU/AlphaPose/blob/master/README.md)
