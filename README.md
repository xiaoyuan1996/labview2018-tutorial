The offical PyTorch code for paper "Exploring a Fine-grained Multiscale Method for Cross-modal Remote Sensing Image Retrieval", TGRS 2021.
The paper link : [paper](https://tgrs)

## INTRODUCTION
This is AMFMN, a cross-modal retrieval method for remote sensing images.
Here, you can get the benchmark of the image-text cross-modal retrieval method, which can be further modified to obtain higher retrieval accuracy. 
Next, we will publish the more fine-grained image-text RSITMD dataset, and welcome you to use the proposed dataset.

## AMFMN
### Architecture
![arch image](./figures/architecture.jpg)
Asymmetric multimodal feature matching network for RS image-text retrieval. AMFMN uses the MVSA module to obtain salient image features and uses salient features to guide the representation of text modalities. The network supports multiple retrieval methods and can adaptively fuse different modal text information.

![arch image](./figures/MVSA_module.jpg)
Multiscale Visual Self-Attention. We first use a multiscale feature fusion network to obtain the multilevel feature representation, then use a redundant feature filtering network to filter out useless feature expressions, and finally get the salient mask of the RS image.

![arch image](./figures/three_v2t.jpg)
Three different visual-guided attention mechanisms.

## RSITMD
### Features
![arch image](./figures/dataset_compare_line.jpg)
The similarity visualization results of six datasets, where the similarity score is weighted by the BLEU and METEOR indicators in the natural
language processing field. The ideal picture is a straight diagonal line from the upper left to the lower right, which means each sentence is only related to the
corresponding image.

![arch image](./figures/dataset_compare_number.jpg)
Quantitative comparison of the four datasets. (a) Comparison of sample number. (b) Comparison of average sentence length. (c) Comparison of
diversity score. (d) Comparison of average similarity. (e) Comparison of the total number of words. (f) Comparison of the number of categories.

## Citation
If you feel this code helpful or use this code or dataset, please cite it as
```
@article{yuan2019AMFMN,
  title={Exploring a Fine-grained Multiscale Method for Cross-modal Remote Sensing Image Retrieval},
  author={Zhiqiang Yuan},
  journal={arXiv preprint arXiv:190},
  year={2021}
}
```
