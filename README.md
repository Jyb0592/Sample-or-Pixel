Project Name
Sample-Centric Multi-Task Learning for Industrial Surface Defect Detection and Segmentation

Brief
To address pixel bias (extreme foreground-background imbalance, easy miss of small defects) in industrial defect segmentation, this work provides:

Sample-level metrics: Sample_mIoU, Seg_Accuracy, Seg_Recall

Sample-centric multi-task learning (MTL) network with a classifier-as-plugin (CaP) branch on the shared encoder.

Key Methods
Sample_mIoU: macro-average IoU only over samples that contain defects or have predictions.

Seg_Accuracy / Seg_Recall: sample-level decision accuracy and recall derived from segmentation masks.

MTL + CaP: classification branch shares encoder with segmentation; loss = 0.5*L_seg + 0.5*L_cls.

Usage
bash
# Train example
python train.py --model unet --dataset ksdd2 --use_cap

# Evaluate
python eval.py --checkpoint model.pth --metrics sample_miou seg_recall
Citation
If you find this work useful, please cite:

bibtex
@article{dong2025samplecentric,
  title={Sample-Centric Multi-Task Learning for Detection and Segmentation of Industrial Surface Defects},
  author={Dong, Hang-Cheng and Jiao, Yibo and Wei, Fupeng and Liu, Guodong and Ye, Dong and Liu, Bingguo},
  journal={...},
  year={2025}
}

