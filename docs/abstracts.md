# Abstracts

## Wodan talk

MirageOS is a library operating system that constructs unikernels for secure,
high-performance network applications. Until now, MirageOS lacked a reliable,
usable filesystem, which limited its applicability by introducing a dependency
on an external storage service. For example, the CueKeeper web application is
Mirage-based and dependent on client-side storage.

We introduce Wodan, a filesystem library designed for MirageOS. It is designed
with flash in mind: SSDs, NVM, hybrid devices. It provides a low-level
key-value layer that Irmin (a distributed database inspired by Git) can use to
store data. It is designed to be reliable and prevent bit rot. It puts control
over layout details and performance tradeoffs in the library user’s hands.

The flash focus of the design makes for some novel design choices. To prevent
wearing out the flash, the newest filesystem root can be written anywhere (in
sequential order), and opening the filesystem involves bisecting for the root.

This talk will delve into the design of Wodan.


