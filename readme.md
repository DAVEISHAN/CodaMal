## CODAMAL: CONTRASTIVE DOMAIN ADAPTATION FOR MALARIA FOR LOW-COST MICROSCOPES

### Dataset

You can download the dataset at https://drive.google.com/drive/folders/1k2GuIu6obj3Nz--dOTLuwQnJ2qs1sXxE
Additional information on the dataset is available at https://github.com/intelligentMachines-ITU/LowCostMalariaDetection_CVPR_2022

Set path of downloaded folder in data/m5_400x.yaml

### Training

The model is trained on HCM images and validated on LCM images

The model is trained and validated on the same zoom resolution (100/400/1000x)

To train on 400x scale:
```
python train_contrastive.py --data m5_400x.yaml --epochs 60 --weights yolov5m.pt --img 640 --cfg yolov5m.yaml --cache disk  --batch-size 32 --hyp config.yaml
```
To train without using the contrastive loss:

```
python train.py --data m5_400x.yaml --epochs 60 --weights yolov5m.pt --img 640 --cfg yolov5m.yaml --cache disk  --batch-size 32 --hyp config.yaml
```

Change --data m5_400x.yaml to m5_100x.yaml/m5_1000x.yaml to try other resolutions

### Results

The output of training will finish with:
Results saved to runs\detect\train
Navigate to folder to see prediction on both training and validation data