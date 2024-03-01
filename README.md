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
If you're on ROCm 6 I recommend pytorch nightly. 
Once you have that, install flash attention to the environment with
```sh
pip install -U git+https://github.com/ROCm/flash-attention@howiejay/navi_support
```
and wait a minute for it to compile. From other user comments it appears this only works on Navi 3 GPUs for now.
### Step 3
#### `--use-pytorch-cross-attention`
This patch only works when launching ComfyUI with the `--use-pytorch-cross-attention` flag. If this is done correctly you should see
```sh
Using pytorch cross attention
```
appear in the console log.
### Step 4
[go fast](https://youtu.be/u_FRDqHT5y0)
