# prase-IDXformat
# MNIST数据集:
# train-images.idx3-ubyte.gz
# train-labels.idx1-ubyte.gz
# t10k-images.idx3-ubyte.gz
# t10k-labels.idx1-ubyte.gz
解压后发现里面每个压缩包里有一个idx-ubyte文件，没有图片文件在里面。
查阅官网后发现原来这是IDX文件格式，是一种用来存储向量与多维度矩阵的文件格式。

THE IDX FILE FORMAT

the IDX file format is a simple format for vectors and multidimensional matrices of various numerical types.

The basic format is

magic number
size in dimension 0
size in dimension 1
size in dimension 2
.....
size in dimension N
data
The magic number is an integer (MSB first). The first 2 bytes are always 0.

The third byte codes the type of the data:

0x08: unsigned byte
0x09: signed byte
0x0B: short (2 bytes)
0x0C: int (4 bytes)
0x0D: float (4 bytes)
0x0E: double (8 bytes)
The 4-th byte codes the number of dimensions of the vector/matrix: 1 for vectors, 2 for matrices....

The sizes in each dimension are 4-byte integers (MSB first, high endian, like in most non-Intel processors).

The data is stored like in a C array, i.e. the index in the last dimension changes the fastest.
