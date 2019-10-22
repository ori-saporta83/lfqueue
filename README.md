# A Scalable, Portable, and Memory-Efficient Lock-Free FIFO Queue

* Publications

	A Scalable, Portable, and Memory-Efficient Lock-Free FIFO Queue.
	In Proceedings of the 33rd International Symposium on DIStributed
	Computing (DISC'19). Budapest, Hungary.

	[Paper](http://drops.dagstuhl.de/opus/volltexte/2019/11335/pdf/LIPIcs-DISC-2019-28.pdf)

* Source code license

	Copyright (c) 2019 Ruslan Nikolaev. All Rights Reserved.

	The SCQ/SCQD/SCQ2/NCQ code is distributed under the 2-Clause BSD license.

* Description

	The benchmark code is in the "benchmark" directory,
	which is forked from the original WFQUEUE's benchmark
	available [here](https://github.com/chaoran/fast-wait-free-queue).
	For usage, see its original README file in "benchmark".

	Additional queues were implemented. See the description below for
	details.

	Both GCC and LLVM should be supported. Older versions may lack
	support for lfring\_cas2.h and/or have suboptimal performance.
	We have tested the code with GCC 8.3.0 and LLVM 7.0.1.

* CAS

	An implementation of the FAA test using CAS emulation (based on
	the original FAA test).

* NCQ

	A naive implementation of the ring buffer. The implementation is in
	lfring\_naive.h.

* SCQ

	This is a "bare-bones" SCQ which simply implements *enqueue* and *dequeue*
	(all platforms). The implementation is in lfring\_cas1.h.

* SCQD

	This is a version which stores pointers as data entries through indirection
	(all platforms). The implementation is in lfring\_cas1.h.

* SCQ2

	This is a version which stores pointers through double-width CAS
	(certain platforms such as x86-64). The implementation is in lfring\_cas2.h.
