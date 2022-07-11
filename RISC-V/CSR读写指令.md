### CSR读写指令

#### 1.  伪指令

**`CSRS csr, rs1`**:   将rs1中每个为1的位，对应的将csr给置位

**`CSRW csr, rs1`**:   将rs1中的值写入csr

**`CSRR rd, csr`**:     读取csr的值并写入rd

