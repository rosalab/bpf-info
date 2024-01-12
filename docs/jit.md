# JIT
As part of BPF program loading, there is an in-kernel jit compiler that converts BPF bytecode into native executable code.
Work has been done to formally verify the corectness of the BPF jit: [Specification and verification in the field: Applying formal methods to BPF just-in-time compilers in the Linux kernel](https://www.usenix.org/conference/osdi20/presentation/nelson).
