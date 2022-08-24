+++
title = "About"
path = "about"
template = "about.html"
+++

# About
## What is Twizzler?
Twizzler is a new operating system. It was designed by the Center for Research in Storage Systems,
primarily by Daniel Bittman, Peter Alvaro, and Ethan L. Miller. Its design is centered around a
"data-centric model", that is to say, a model in which the persistent data that applications access
is the "primary citizen" instead of a process, as is common in other operating systems. Concretely,
this translates to programs operating on persistent and shared data with memory semantics without the added
complexity of serialization or the added latency of explicit load and unload system calls.

Twizzler is motivated by a convergence of persistence, low-latency memory, and distributed memory
and compute, realized through the introduction of byte-addressable NVM technologies, faster
persistent storage,
and network technologies like RDMA.
Our design enables both effective direct access to data and effective sharing of persistent objects
both between different applications (through interoperability of invariant pointers) and across
address spaces and machines (by providing a global address space). The latter means that Twizzler
provides an effective solution to low-coordination sharing and concurrent access to persistent
data in a global space of data objects, a vital feature with the increasing disaggregation and sizes
of memories.

For more information, see our <a href="/pubs">publications</a>.

## How does it work?
Twizzler's kernel is very small. Its goal is to support a userspace environment that handles the
majority of the day-to-day OS operations. The kernel provides a simple set of primitives for thread
management and synchronization, data object management, and talking to devices. It acts as the
trusted computing base which is primarily responsible for multiplexing and virtualizing hardware,
and mapping data objects into address spaces for userspace programs. A userland program uses the
Twizzler APIs to operate on persistent or shared data.

For more information, see our <a href="/docs">documentation</a>.

## How can I try it out?
Twizzler is available for downloading in the Downloads page, currently in source code form. 
The source code provides a method for building the code into a usable image. NOTE: this is a research OS! It is unstable and should be used with care in production environments. We assume you know what you are doing when you try to use it :)

## How can I write code for it?
See `doc/src/develop.md` for details in the source repo.