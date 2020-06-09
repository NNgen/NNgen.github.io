
NNgen Tutorial on Ultra96 v2 and PYNQ
========================================

This tutorial provides to the basic development flow for DNN acceleration system based on NNgen on Ultra96 v2 and PYNQ.


Software versions used in this tutorial
========================================

- nngen: v1.3.0
- veriloggen: 1.8.2
- pyverilog: 1.2.1

- Pillow: 7.1.2
- onnx: 1.7.0
- torch: 1.5.0
- torchvision: 0.6.0


Install NNgen
========================================

```
mkdir tutorial_nngen
cd tutorial_nngen
git clone https://github.com/NNgen/nngen.git
virtualenv --python=python3 python3
source python3/bin/activate
cd nngen
python3 setup.py install
pip3 install pillow torch torchvision
```


Create DNN Hardware by example
========================================

```
cd examples/torchvision_onnx_vgg11
```

Edit the data bit-width.
The example uses 16-bit for activations (act_dtype=ng.int16) and 8-bit for weights (weight_dtype=ng.int8).
Let's change the data type of activations to "ng.int8".

```
vi torchvision_onnx_vgg11.py
```

```python
def run(act_dtype=ng.int8, weight_dtype=ng.int8,
        bias_dtype=ng.int32, scale_dtype=ng.int8,
        with_batchnorm=True, disable_fusion=False,
        conv2d_par_ich=1, conv2d_par_och=1, conv2d_par_col=1, conv2d_par_row=1,
        conv2d_concur_och=None, conv2d_stationary='filter',
        pool_par=1, elem_par=1,
        chunk_size=64, axi_datawidth=32, silent=False,
        filename=None,
        # simtype='iverilog',
        # simtype='verilator',
        simtype=None,  # no RTL simulation
        outputfile=None):
```

Generate a DNN hardware by executing script.

```
python3 torchvision_onnx_vgg11.py
```


Synthesize FPGA bitstream on Vivado
========================================


Setup PYNQ
========================================

Download the PYNQ image file.


Execute the synthesized bitstream on PYNQ
========================================

