# Block-Sparse library

> Copyright 2019 Graphcore Ltd.

## Dependencies:

SDK released by Graphcore of version 1.2 or later

## Quick start guide

### Prepare the environment

##### 1) Download the Poplar SDK

  Install the `poplar-sdk` following the README provided. Make sure to source the `enable.sh`
  scripts for poplar, gc_drivers (if running on hardware) and popART.

##### 2) Python

Create a virtualenv and install the required packages:

```bash
virtualenv venv -p python3.6
source venv/bin/activate
pip install -r requirements.txt
```

### Create custom_ops.so with provided makefile
```bash
make all
```

### Test out basic examples
```bash
# To list all tests:
pytest --co examples/test_block_sparse.py

# Run the first example
pytest examples/test_block_sparse.py -k tag_tr_0
```

### Test out MNIST examples
#### Download MNIST database
```bash
cd examples/mnist
bash get_mnist.sh
```
#### Run MNIST model training example
```bash
python3 bs_mnist.py --batch-size 32 --batches-per-step 4 --num-ipus 1 --hidden-size 16 --sparsity-level 0.7 ./data
```

### Test out sparse attention examples
```
python3 examples/sparse_attention/short_demo.py 
```