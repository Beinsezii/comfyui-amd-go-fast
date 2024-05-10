# Installation
### Step 1
#### Get the file
Put `amd_go_fast.py` into your `custom_nodes` folder. If it picks up the patch correctly you should see
```sh
# # #
AMD GO FAST
# # #
```
appear in the console log.
### Step 2
#### Install Flash Attention for Navi 3.
Install the full ROCm SDK from your distro and ideally make sure it matches the version of ROCm used in your virtual environment.
I strongly recommend a minimum ROCm of 6.0 and PyTorch 2.3, but earlier versions back to 5.6/2.1 are known to possibly work.
Once you have that, install flash attention to the environment with
```sh
pip install -U git+https://github.com/ROCm/flash-attention@howiejay/navi_support
```
and wait a minute for it to compile. From other user comments it appears this only works on Navi 3 GPUs for now.

Additionally, I made some pre-compiled wheels for ROCm 6/Navi 31 which you can find for Python 3.11 and 3.12 [here.](https://github.com/Beinsezii/comfyui-amd-go-fast/issues/2#issuecomment-2103639275)
I would only recommend trying these if compiling the wheel yourself does not work properly.
### Step 3
#### `--use-pytorch-cross-attention`
This patch only works when launching ComfyUI with the `--use-pytorch-cross-attention` flag. If this is done correctly you should see
```sh
Using pytorch cross attention
```
appear in the console log.
### Step 4
[go fast](https://youtu.be/u_FRDqHT5y0)
