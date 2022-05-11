# SSformer

SSformer is A Lightweight Transformer for Semantic Segmentation.

We use [MMSegmentation v0.24.1](https://github.com/open-mmlab/mmsegmentation/tree/v0.24.1) as the codebase.

## Installation

For install and data preparation, please refer to the guidelines in [MMSegmentation v0.24.1](https://github.com/open-mmlab/mmsegmentation/tree/v0.24.1).

An example (works for me): ```CUDA 11.3``` and  ```pytorch 1.10.0``` 
```
pip install mmcv-full==1.4.3
cd SSFormer && pip install -e . --user
```
## Evaluation
Download [trained weights]().
Example: evaluate ```SSformer``` on ```ADE20K```:
```
# Single-gpu testing
python tools/test.py configs/SSformer/SSformer_swin_512x512_160k_ADE20K.py /path/to/checkpoint_file
```
## Training
Download [weights]() pretrained on ImageNet-22K, and put them in a folder ```pretrained/```.
Example: train ```SSFormer``` on ```ADE20K```:
```
# Single-gpu training
python tools/train.py configs/SSformer/SSformer_swin_512x512_160k_ADE20K.py
```
## Visualize
Here is a demo script to test a single image. More details refer to [MMSegmentation's Doc](https://mmsegmentation.readthedocs.io/en/latest/get_started.html).
```shell
python demo/image_demo.py ${IMAGE_FILE} ${CONFIG_FILE} ${CHECKPOINT_FILE} [--device ${DEVICE_NAME}] [--palette-thr ${PALETTE}]
```

Example: visualize ```SSformer``` on ```CityScapes```: 

```shell
python demo/image_demo.py demo/demo.png configs/SSformer/SSformer_swin_512x512_160k_ADE20K.py \
/path/to/checkpoint_file --device cuda:0 --palette cityscapes
```





## License
Please check the LICENSE file. 