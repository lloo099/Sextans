# Sextans

Sextans is an accelerator for general-purpose Sparse-Matrix Dense-Matrix Multiplication (SpMM). One exciting feature is that we only need to prototype Sextans once, and the hardware supports an arbitrary SpMM. Following are software and hardware dependencies.

+ Xilinx Vitis 2020.2
+ Alveo U280 HBM FPGA
+ Alveo U250 FPGA

To learn more about the techinqual details, please see [this link](https://arxiv.org/abs/2109.11081).

U200 implementation:
```
source /opt/xilinx/xrt/setup.sh
source /tools/Xilinx/Vitis/2020.1/settings64.sh
make all TARGET=hw DEVICE=xilinx_u200_xdma_201830_2 HOST_ARCH=x86

./host sextans.xclbin p2p-Gnutella04/p2p-Gnutella04.mtx 16 0.85 -2.5

```

If you find this code useful, please cite:

    @inproceedings{song2022sextans,
    author = {Linghao Song and Yuze Chi and Atefeh Sohrabizadeh and Young-kyu Choi and Jason Lau and Jason Cong},
    title = {Sextans: A Streaming Accelerator for General-Purpose Sparse-Matrix Dense-Matrix Multiplication},
    booktitle={The 2022 ACM/SIGDA International Symposium on Field-Programmable Gate Arrays},
    year = {2022}
    }
