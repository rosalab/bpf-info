# BPF Program
A BPF program is a safe kernel extension.

## Program Type
Every BPF program has an associated program type.
The list of all program types can be found in the `uapi/linux/bpf.h`.

The program type determines 4 things about the kernel extensions interface to the kernel:

1. Where the program can be attached
2. What helper functions it can call
3. Whether network packet data can be accessed directly
4. The kind of object that is passed to the bpf program (context)
