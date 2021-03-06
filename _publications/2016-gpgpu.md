---
title: "GPUpIO: The Case for I/O-Driven Preemption on GPUs"
collection: publications
permalink: /publication/2016-gpgpu-gpupio
excerpt: ''
date: 2016-03-12
venue: "GPGPU '16, The 9th Annual Workshop on General Purpose Processing Using Graphics Processing Unit"
paperurl: 'https://liorze.github.io/files/gpupio-gpgpu16.pdf'
authors: Lior Zeno, Avi Mendelson, Mark Silberstein
---
As GPUs become general purpose, they are outgrowing the coprocessor model and require convenient I/O abstractions such as
files and network sockets. Recent studies have shown the benefits
of native GPU I/O layers, in terms of both programmability and
performance. However, due to lack of hardware support, the GPU
threads performing I/O calls are forced to busy-wait for the completion of I/O operations, resulting in underutilized hardware, higher
power consumption, and reduced system throughput.

We argue that I/O-driven preemption improves the performance
of existing solutions, despite many challenging system characteristics such as a large kernel state. We analyze the benefits of adding
preemption support using a simple system performance model, and,
encouraged by the results, explore the design of a software-based
preemption mechanism for GPUs. In our prototype, GPUpIO, we
implement a source-to-source compiler for state checkpoint and
restoration, and a runtime library for scheduling preempted threadblocks, which together enable I/O-driven preemption for GPUs.

We evaluate our prototype across a variety of system parameters
and workloads to determine when preemption is worthwhile. We
show that in some workloads the I/O-driven preemption approach
may indeed double the effective system throughput by completely
hiding the I/O latency behind computations. However, we also observe that the software-only solution is currently limited, not only
due to its overheads, but also because it does not have sufficient
control of the hardware scheduler queue and therefore may lead to
starvation of I/O kernels. We then discuss a new hardware feature
that, if added, may render a general I/O-driven preemption mechanism on GPUs practical.
