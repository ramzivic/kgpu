# Updates #
**The k32 branch on github now works with kernel 3.2.x. Hope that makes people a little bit happier. I also encourage people take a look at [Snap](https://github.com/wbsun/snap), which is another system-level GPU computing study. It helps build parallel packet processing boxes with GPUs.**

# Where is the source code? #
Github: https://github.com/wbsun/kgpu
We use the Google code as a place to publish updates.

# What is It? #

KGPU (or GPUstore, for storage) is a GPU computing framework for the Linux kernel. It allows Linux kernel to call CUDA programs running on GPUs directly. The motivation is to augment operating systems with GPUs so that not only userspace applications but also the operating system itself can benefit from GPU acceleration. It can also free the CPU from some computation intensive work by enabling the GPU as an extra computing device.

Modern GPUs can be used for more than just graphics processing;
they can run general-purpose programs as well. While not well-suited to all types of programs, they excel on code that can make use of their high degree of parallelism. Most uses of so-called ``General Purpose GPU'' (GPGPU) computation have been outside the realm of systems software. However, recent work on [software routers](http://shader.kaist.edu/packetshader) and  [encrypted network connections](http://shader.kaist.edu/sslshader/) has given examples of how GPGPUs can be applied to tasks more traditionally within the realm of operating systems. These uses are only scratching the surface. Other examples
of system-level tasks that can take advantage of GPUs include general cryptography, pattern matching, program analysis, and acceleration of basic commonly-used algorithms;
we give more details in [our whitepaper](http://www.cs.utah.edu/~wbsun/kgpu.pdf). These  tasks have applications on the desktop, on the server, and in the datacenter.

KGPU is a project of the [Flux Research Group](http://www.flux.utah.edu/) at the [University of Utah](http://www.cs.utah.edu). It is supported by NVIDIA through a
[graduate fellowship](http://research.nvidia.com/content/nvidia-graduate-fellowship-results-2011) awarded to Weibin Sun.

# More #

The idea behind KGPU is to treat the GPU as a computing co-processor for the operating system, enabling data-parallel computation inside the Linux kernel. This allows us to use SIMD (or SIMT in CUDA) style code to accelerate Linux kernel functionality, and to bring new functionality formerly considered too compute intensive into the kernel. Simply put, KGPU enables vector computing for the kernel.

It makes the Linux kernel really parallelized: it is not only processing multiple requests concurrently, but can also partition a single large requested computation into tiles and spread them across the large number of cores on a GPU.

KGPU is not an OS running on GPU; this is practically impossible because of the limited functionality of current GPUs.

# Performance #
See our paper about storage applications: **GPUstore: Harnessing GPU Computing for Storage Systems in the OS Kernel** by: _Weibin Sun (University of Utah) Robert Ricci (University of Utah) Matthew L. Curry (Sandia National Laboratories)_ (SYSTOR 2012) [PDF](http://www.cs.utah.edu/~wbsun/gpustore.pdf).

# News #
A flowchart to describe the GPU request processing is uploaded. Find it at the **Downloads** page.