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

<img width="422" height="236" alt="Snipaste_2025-07-24_22-27-02" src="https://github.com/user-attachments/assets/e4855003-36ca-45b1-9f37-10ef04a0d5c1" />

But it is very close to the issue result.

issue：https://github.com/lin-tianyu/Stable-Diffusion-Seg/issues/32

##### Training process monitoring（Tensorboard）

<img width="766" height="334" alt="Snipaste_2025-07-26_18-00-22" src="https://github.com/user-attachments/assets/bd720153-570f-477d-981e-0d98f88a801e" />

<img width="754" height="332" alt="Snipaste_2025-07-26_18-01-02" src="https://github.com/user-attachments/assets/6d98d7ab-92b6-4583-96d4-68168b7dd8eb" />

<img width="754" height="333" alt="Snipaste_2025-07-26_18-01-29" src="https://github.com/user-attachments/assets/3750511f-5b01-4ee4-92e9-694d7b40a5eb" />

<img width="749" height="333" alt="Snipaste_2025-07-26_18-01-55" src="https://github.com/user-attachments/assets/559c2b8f-45c6-40c7-ae18-6f3d445c8fc3" />

#### BTCV

The best model was obtained at epoch=162, step=89999.

train: Slice data for training (.png + .npy)

val: Validation set (slice level)

test_vol: Volume data for testing phase (.nii.gz)

[Dataset]: Synapse with 2 classes, in test_vol mode，The test set consists of 12 volume files，Test Results：

[Mean Dice][cls 1]: 0.9216991539533574

[Mean  IoU][cls 1]: 0.85579289234439

The reproduction results are very close to the paper results：

<img width="422" height="236" alt="Snipaste_2025-07-24_22-27-02" src="https://github.com/user-attachments/assets/890fcd89-2bf9-41ef-ab04-c30df677a137" />

##### Training process monitoring（Tensorboard）

<img width="749" height="337" alt="Snipaste_2025-07-26_18-06-11" src="https://github.com/user-attachments/assets/2cde4aa0-2f3c-46bd-9087-9297f4d6c4f0" />

<img width="753" height="336" alt="Snipaste_2025-07-26_18-06-51" src="https://github.com/user-attachments/assets/50e55ae1-467c-4cbb-a741-ae3c1ed71b86" />

<img width="752" height="333" alt="Snipaste_2025-07-26_18-07-20" src="https://github.com/user-attachments/assets/8fd9489f-786c-4bdb-a4c7-20f525b265e0" />

<img width="755" height="333" alt="Snipaste_2025-07-26_18-08-06" src="https://github.com/user-attachments/assets/14fecb23-872a-44bf-99d0-137211bcd67b" />
