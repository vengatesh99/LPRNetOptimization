# LPRNetOptimization
Environment Setup and Testing: Download the .ipynb file and run the cells sequentially in Google Colab.
#### Note: Since we have used Tensorrt optimization, it would require a GPU. Please connect to the T4 GPU runtime provided by colab while executing Tensorrt optimization. Other techniques can be executed in CPU itself

#### Folder Structure:
/\
|---lprnet_optimization_notebook.ipynb \
|---report.pdf\
|---README.md \
##### How to test \
To test the model, we have to invoke test() with appropriate flags that corresponds to each optimizations. To combine any optimization set the required flags to True. When invoked, this function will give you the Test Accuracy(%), Inference Speed(s), Model Size(MB). \
Example testing: \
test(jit_autotune = True, weight_quantize_flag = True)
