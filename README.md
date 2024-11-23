# Any zkVM template
A rust template that allows any rust dev to easily develop an app made for a zkVM, but abstracting which one to use. also makes it possible to benchmark over every available zkVM

For now, proving and verification is in the same script, but it would great to have two different flow for both

## Getting started
You can write your code in `./lib/src/lib.rs`. 

You'll find a trait `Processor` with some function already implemented; let's go through every function and types to understand them better

### Processor::Input
This type represent the public inputs you'll pass to your verifier
### Processor::Output
This type represent the public outputs your program will pass to the verifier
### get_guest_inputs
This function is an helper to pass your inputs to the zkvm, you should not have to modify this function (or at least not often)
### get_host_inputs
This function passes the public inputs to the prover, you could for example take these inputs from your user directyl
### prove
This is where you'll write the code you want to prove, this code will be the one passed to the prover
### process_outputs
This function is the callback you'll get at the end of the program (after verification), you can then uses the output values to do any verification you need!

## TODO
- Add more zkVMs
- Add Valida with their custom ISA
- Add benchmarks