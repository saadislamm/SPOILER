SPOILER: Speculative Load Hazards Boost Rowhammer and Cache Attacks
CVE-2019-0162
INTEL-SA-00238

Authors: 
Saad Islam and Ahmad Moghimi, Worcester Polytechnic Institute; Ida Bruhns and Moritz Krebbel, University of Luebeck; Berk Gulmezoglu, Worcester Polytechnic Institute; Thomas Eisenbarth, Worcester Polytechnic Institute and University of Luebeck; Berk Sunar, Worcester Polytechnic Institute

Abstract: 
Modern microarchitectures incorporate optimization techniques such as speculative loads and store forwarding to improve the memory bottleneck. The processor executes the load speculatively before the stores, and forwards the data of a preceding store to the load if there is a potential dependency. This enhances performance since the load does not have to wait for preceding stores to complete. However, the dependency prediction relies on partial address information, which may lead to false dependencies and stall hazards.

In this work, we are the first to show that the dependency resolution logic that serves the speculative load can be exploited to gain information about the physical page mappings. Microarchitectural side-channel attacks such as Rowhammer and cache attacks like Prime+Probe rely on the reverse engineering of the virtual-to-physical address mapping. We propose the SPOILER attack which exploits this leakage to speed up this reverse engineering by a factor of 256. Then, we show how this can improve the Prime+Probe attack by a 4096 factor speed up of the eviction set search, even from sandboxed environments like JavaScript. Finally, we improve the Rowhammer attack by showing how SPOILER helps to conduct DRAM row conflicts deterministically with up to 100% chance, and by demonstrating a double-sided Rowhammer attack with normal user’s privilege. The later is due to the possibility of detecting contiguous memory pages using the SPOILER leakage.




Steps to run in LINUX:

$ make

$ ./spoiler

// Install gnuplot if alrady not installed or plot t2.txt in any other software
// plot_t2.m MATLAB script provided
$ gnuplot

gnuplot> plot 't2.txt' with lines

// If you see the peaks similar to peaks_linux.png,
// your CPU is vulnerable to SPOILER



Steps to run in WINDOWS:

Execute "spoiler.exe" with double click or command prompt

Plot "t2.txt" using any software or with plot_t2.m MATLAB script



BibTeX

@inproceedings {236252,
author = {Saad Islam and Ahmad Moghimi and Ida Bruhns and Moritz Krebbel and Berk Gulmezoglu and Thomas Eisenbarth and Berk Sunar},
title = {{SPOILER}: Speculative Load Hazards Boost Rowhammer and Cache Attacks},
booktitle = {28th {USENIX} Security Symposium ({USENIX} Security 19)},
year = {2019},
isbn = {978-1-939133-06-9},
address = {Santa Clara, CA},
pages = {621--637},
url = {https://www.usenix.org/conference/usenixsecurity19/presentation/islam},
publisher = {{USENIX} Association},
month = aug,
}

Link to the paper:
https://www.usenix.org/system/files/sec19-islam.pdf

Link to the poster:
https://www.researchgate.net/publication/339484716_SPOILER_Speculative_Load_Hazards_Boost_Rowhammer_and_Cache_Attacks
