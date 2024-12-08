# LPRNetOptimization
Environment Setup and Testing: Download the .ipynb file and run the cells sequentially in Google Colab.
#### Note: Since we have used Tensorrt optimization, it would require a GPU. Please connect to the T4 GPU runtime provided by colab while executing Tensorrt optimization. Other techniques can be executed in CPU itself
The model and weights are in this github repo : https://github.com/sirius-ai/LPRNet_Pytorch/tree/master. Please download the data and weights and upload it to google drive. In your google colab notebook, while running, mount it to google drive and change the parameters args.test_img_dirs and args.pretrained_model to match the location of test data directory and pretrained model.\
Example: \
args.test_img_dirs = "drive/MyDrive/.../data/test" \
args.pretrained_model = "drive/MyDrive/.../Final_LPRNet_model.pth"

#### Folder Structure:
/\
|---lprnet_optimization_notebook.ipynb \
|---report.pdf\
|---README.md
#### How to test
To test the model, we have to invoke test() with appropriate flags that corresponds to each optimizations. To combine any optimization set the required flags to True. When invoked, this function will give you the Test Accuracy(%), Inference Speed(s), Model Size(MB). \
Example testing: \
```python
test(jit_autotune = True, weight_quantize_flag = True)
```


#### Existing flags to set for the experiments
normal_flag  = to set testing for baseline model \
quantize_flag = Set this to perform static quantization \
weight_quantize_flag= Set this to perform Weight Based Quantization \
fuse_flag= To perform fusing \
sparsity_flag= To perform 1:4 Sparsity Pruning \
prune_flag= To Perform Channel Based Pruning \
jit_compile= To Perform TorchScript JIT Optimization \
torch_compile= To perform Ahead of time MLC Optimization \
tensorrt_compile= To perform Tensorrt optimization \
jit_autotune = To perform Autotuning using Relay and JIT \
quant_tensorrt_compile_flag= To Perform Weight Quantization and Tensorrt optimization together

