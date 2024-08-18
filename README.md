# Official implementation for TDiDA

Official pytorch implement for [Target-Discriminability-Induced Multi-Source-Free Domain Adaptation](https://doi.org/10.1109/ICIP49359.2023.10222016).

## Prerequisites (Python 3.9.12)

```
pip install -r requirements.txt
```

## Dataset

Please manually download the datasets [Office](https://www.dropbox.com/sh/vja4cdimm0k2um3/AACCKNKV8-HVbEZDPDCyAyf_a?dl=0), [Office-Home](https://www.dropbox.com/sh/vja4cdimm0k2um3/AACCKNKV8-HVbEZDPDCyAyf_a?dl=0), [Office-Caltech](https://www.dropbox.com/sh/vja4cdimm0k2um3/AACCKNKV8-HVbEZDPDCyAyf_a?dl=0) from the official websites, and modify the path of images in each '.txt' under the folder './data/'.

## Training

### Office-Home (for example)

#### Source pretraining

```
CUDA_VISIBLE_DEVICES=0 python image_source.py --trte val --output ckps/source/ --da uda --dset office-home --max_epoch 100 --s 0 > log_s0_office-home.txt
```

#### Target adaptation

```
CUDA_VISIBLE_DEVICES=0 python image_target_Multi_Src.py --da uda --dset office-home --t 0 --output_src ckps/source/ --output ckps/target_Multi_Src/ > log_t0_office-home.txt
```

## Citation

If you find this useful in your work, please consider citing our paper.

```
@inproceedings{li2023target,
  title={Target-Discriminability-Induced Multi-Source-Free Domain Adaptation},
  author={Li, Gang and Zhang, Qifei and Wang, Peizheng and He, Rui and Wu, Chao},
  booktitle={2023 IEEE International Conference on Image Processing (ICIP)},
  pages={76--80},
  year={2023},
  organization={IEEE}
}
```

## Acknowledgements

[TransDA](https://github.com/ygjwd12345/TransDA)

[DECISION](https://github.com/driptaRC/DECISION)

[KD3A](https://github.com/FengHZ/KD3A)
