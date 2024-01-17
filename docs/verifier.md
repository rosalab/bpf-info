# BPF Verifier
When a BPF program is loaded, it is verified to be safe by an in-kernel verifier.
The verifier uses two passes.

## Two Verifier Passes
The first pass the verifier checks that the program is a [DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph), as well as place some constraints on the length.
The verifier will reject a BPF program at this point if
1. Larger than `BPF_MAXINSNS`
2. Has a loop (in the form of a backedge on the [CFG](https://en.wikipedia.org/wiki/Control-flow_graph)
3. Unreachable instructions exist
4. Malformed or out of bounds jumps are present

If the program is not rejected then the verifier begins the second pass, which is an all possible paths descent through the program.

### BPF Verifier Types
The BPF verifier has a notion of types.
Each register has a type associated with it, defined in `enum bpf_reg_type` in `bpf.h`. 
There are also types associated with function arguments, `enum bpf_arg_type`, and return values, `enum bpf_ret_type`.

## Second Pass
As the verifier explores all possible paths, it keeps track of the state of the registers and stack.
Each instruction causes the register/stack state to change.
The verifier knows the effect that each instruction has on the state, so it can keep track of this. 
