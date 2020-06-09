NNgen
========================================

A Fully-Customizable Hardware Synthesis Compiler for Deep Neural Network

Copyright 2017, Shinya Takamaeda-Yamazaki and Contributors


License
==============================

Apache License 2.0 (http://www.apache.org/licenses/LICENSE-2.0)


GitHub Repository
========================================

https://github.com/NNgen/nngen


What's NNgen?
==============================

NNgen is an open-sourced compiler to synthesize a model-specific hardware accelerator for deep neural networks. NNgen generates a Verilog HDL source code and an IP-core package (IP-XACT) of a DNN accelerator from an input model definition.

Generated hardware is all-inclusive, which includes processing engine, on-chip memory, on-chip network, DMA controller, and control circuits. So the generated hardware does not require any additional controls from an external circuit or the CPU after the processing is started.

The backend of NNgen employes Veriloggen, an open-sourced mixed-paradigm high-level synthesis compiler in Python. So you can customize NNgen for new DNN algorithms and applications.


Tutorial
========================================

- [NNgen tutorial on Ultra96 v2 and PYNQ](./tutorial-ultra96v2-pynq)
