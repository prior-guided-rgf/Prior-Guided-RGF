# Improving Black-box Adversarial Attacks with a Transfer-based Prior

This repository contains the code for reproducing the experimental results of attacking Inception-v3 model, of our submission: *Improving Black-box Adversarial Attacks with a Transfer-based Prior*.

## Reproducing the results

The results can be reproduced using the following command:

```
mkdir outputs
python attack.py --input_dir=images --output_dir=outputs --checkpoint_path=inception_v3.ckpt --norm=[l2 | linfty] --method=[uniform | biased | fixed_biased] [--dataprior] [--show_loss]
```

Here, `method=[uniform | biased | fixed_biased]` corresponds to U-RGF, P-RGF (\\lambda^\*), P-RGF (\\lambda=0.5) in the paper respectively. We also prepared a script `run_attack.sh` for convenience.

Note that before running the command above, the user needs to download the model checkpoints of Inception-v3 and ResNet-v2-152 first, which are located at https://github.com/tensorflow/models/tree/master/research/slim. Then the user needs to put `inception_v3.ckpt` and `resnet_v2_152.ckpt` under this folder.

## Requirements

Python packages: tensorflow-gpu, opencv-python.

The code is tested with Python 3.6 and Tensorflow 1.13.1.
