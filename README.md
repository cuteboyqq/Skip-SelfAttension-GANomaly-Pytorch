### Skip-SelfAttension-GANomaly-Pytorch
[(Back to top)](#table-of-contents)

Generator +  Discriminator model 


### Table of contents

<!-- After you have introduced your project, it is a good idea to add a **Table of contents** or **TOC** as **cool** people say it. This would make it easier for people to navigate through your README and find exactly what they are looking for.

Here is a sample TOC(*wow! such cool!*) that is actually the TOC for this README. -->

- [Skip-SelfAttension-GANomaly-Pytorch](#Skip-SelfAttension-GANomaly-Pytorch)
- [Requirement](#Requirement)
- [implement](#implement)
- [Unet-Network](#Unet-Network)
- [Train-on-custom-dataset](#Train-on-custom-dataset)
- [Train](#Train)
- [Test](#Test)
- [Lose-value-distribution](#Lose-value-distribution)
- [Reference](#Reference)
   
### Requirement
```
pip install -r requirements.txt
```

### implement 
[(Back to top)](#table-of-contents)

1. Encoder-Decoder use Unet
2. Use self-Attension

![image](https://user-images.githubusercontent.com/58428559/196458673-9a46b77c-623c-4079-b8cb-876107318f26.png)


### Unet-Network
[(Back to top)](#table-of-contents)
![image](https://user-images.githubusercontent.com/58428559/195968671-a287ecae-67b0-41e2-9bfc-7283014c8c3b.png)


![image](https://user-images.githubusercontent.com/58428559/196595324-9c2e584d-7202-4786-9812-062e10fd295f.png)


### Train-on-custom-dataset
[(Back to top)](#table-of-contents)

```
Custom Dataset
├── test
│   ├── 0.normal
│   │   └── normal_tst_img_0.png
│   │   └── normal_tst_img_1.png
│   │   ...
│   │   └── normal_tst_img_n.png
│   ├── 1.abnormal
│   │   └── abnormal_tst_img_0.png
│   │   └── abnormal_tst_img_1.png
│   │   ...
│   │   └── abnormal_tst_img_m.png
├── train
│   ├── 0.normal
│   │   └── normal_tst_img_0.png
│   │   └── normal_tst_img_1.png
│   │   ...
│   │   └── normal_tst_img_t.png


```

### Train
[(Back to top)](#table-of-contents)
```
python train.py --img-dir "[train dataset dir]" --batch-size 64 --img-size 32 --epoch 20
```
### Test
[(Back to top)](#table-of-contents)
```
python test.py --nomal-dir "[test normal dataset dir]" --abnormal-dir "[test abnormal dataset dir]" --view-img --img-size 32
```
Example :
Train dataset : factory line only

dataset :factory line , top: input images, bottom: reconstruct images

![infer_normal1](https://user-images.githubusercontent.com/58428559/196492251-ca80117e-848a-43bb-95fb-510ec1c284ca.jpg)

dataset :factory noline , top: input images, bottom: reconstruct images

![infer_abnormal1](https://user-images.githubusercontent.com/58428559/196492292-0aeb749f-8400-4d31-b964-d3d5dd597c40.jpg)

### Lose-value-distribution
[(Back to top)](#table-of-contents)

Blue : normal dataset

Orange : abnormal dataset

![loss_distribution](https://user-images.githubusercontent.com/58428559/196492187-8fdbf2e8-6473-4ed6-98c4-22f890482e08.jpg)

### Reference 
[(Back to top)](#table-of-contents)

https://arxiv.org/abs/1805.06725

https://arxiv.org/pdf/1901.08954.pdf

