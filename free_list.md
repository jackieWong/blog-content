free_list机制管理的内存是按照8字节的整数倍来进行管理的。每次划分出去的块大小一定是8字节的整数倍。但是在vector的管理中，vector也维护自身的