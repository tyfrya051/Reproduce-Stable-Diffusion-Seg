## Reproduce-Stable-Diffusion-Seg

This is my result of reproducing Stable-Diffusion-Seg on the CVC-ClinicDB dataset and BTCV dataset.

Stable-Diffusion-Seg：https://github.com/lin-tianyu/Stable-Diffusion-Seg

#### Equipment&Environment：AutoDL

PyTorch 1.11.0

Python 3.8(ubuntu20.04)

CUDA 11.3

GPU：vGPU-48GB-425W(48GB) * 1

CPU：20 vCPU Intel(R) Xeon(R) Platinum 8470Q

Memory：90GB

Hard disk：System disk：30 GB，Data disk：50GB

#### CVC-ClinicDB

The best model was obtained at epoch=829, step=101999.

There are 492 images in the training set, 60 images in the validation set, and 62 images in the test set.

[Dataset]: CVC with 2 classes，Test Results：
[Mean Dice][cls 1]: 0.8402074328258003
[Mean  IoU][cls 1]: 0.7526817825120945

There is a slight gap between the results of the reproduction and the results of the paper：

![Snipaste_2025-07-24_22-27-02](C:\Users\tyf\Desktop\Snipaste_2025-07-24_22-27-02.png)

But it is very close to the issue result.

issue：https://github.com/lin-tianyu/Stable-Diffusion-Seg/issues/32

##### Training process monitoring（Tensorboard）

![](C:\Users\tyf\Desktop\cvc\Snipaste_2025-07-26_18-00-22.png)

![Snipaste_2025-07-26_18-01-02](C:\Users\tyf\Desktop\cvc\Snipaste_2025-07-26_18-01-02.png)

![Snipaste_2025-07-26_18-01-29](C:\Users\tyf\Desktop\cvc\Snipaste_2025-07-26_18-01-29.png)

![Snipaste_2025-07-26_18-01-55](C:\Users\tyf\Desktop\cvc\Snipaste_2025-07-26_18-01-55.png)

#### BTCV

The best model was obtained at epoch=162, step=89999.

train: Slice data for training (.png + .npy)

val: Validation set (slice level)

test_vol: Volume data for testing phase (.nii.gz)

[Dataset]: Synapse with 2 classes, in test_vol mode，The test set consists of 12 volume files，Test Results：

[Mean Dice][cls 1]: 0.9216991539533574
[Mean  IoU][cls 1]: 0.85579289234439

The reproduction results are very close to the paper results：

![Snipaste_2025-07-24_22-27-02](C:\Users\tyf\Desktop\Snipaste_2025-07-24_22-27-02.png)

##### Training process monitoring（Tensorboard）

![](C:\Users\tyf\Desktop\BTCV\Snipaste_2025-07-26_18-06-11.png)

![Snipaste_2025-07-26_18-06-51](C:\Users\tyf\Desktop\BTCV\Snipaste_2025-07-26_18-06-51.png)

![Snipaste_2025-07-26_18-07-20](C:\Users\tyf\Desktop\BTCV\Snipaste_2025-07-26_18-07-20.png)

![Snipaste_2025-07-26_18-08-06](C:\Users\tyf\Desktop\BTCV\Snipaste_2025-07-26_18-08-06.png)