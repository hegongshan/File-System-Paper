# File System

* [1.Local File System](#local-file-system)
  
  * [1.1 Kernel File System](#kernel-file-system)
  
    * [1.1.1 Multicore/Manycore Scalability](#multicoremanycore-scalability)
  
  * [1.2 User-Space File System](#user-space-file-system)


* [2.Distributed File System](#distributed-file-system)
  
  * [2.1 General Purpose File System](#general-purpose-file-system)
  
  * [2.2 Big Data](#big-data)
  
  * [2.3 High Performance Computing](#high-performance-computing-hpc)

    * [2.3.1 Burst Buffer File System](#burst-buffer-file-system)

* [3.Metadata Management Optimization](#metadata-management-optimization)

* [4.Surveys](#surveys)

## Local File System

### Kernel File System

[Linux File System](https://www.kernel.org/doc/html/latest/filesystems)

[1991 SOSP] **The Design and Implementation of a Log-Structured File System**. [[PDF](https://people.eecs.berkeley.edu/~brewer/cs262/LFS.pdf)]

[1995] **Design and Implementation of the Second Extended Filesystem**. [[PDF](http://e2fsprogs.sourceforge.net/ext2intro.html)]

[1998] ext3: **Journaling the Linux ext2fs Filesystem**. [[PDF](https://pdos.csail.mit.edu/6.828/2020/readings/journal-design.pdf)]

#### Multicore/Manycore Scalability

[2016 ATC] **Understanding Manycore Scalability of File Systems**. [[PDF](https://www.usenix.org/system/files/conference/atc16/atc16_paper-min.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc16_slides_min.pdf)]

[2017 SOSP] ScaleFS: **Scaling a File System to Many Cores Using an Operation Log**. [[PDF](https://pdos.csail.mit.edu/papers/scalefs.pdf)]

[2022 FAST] **ScaleXFS: Getting scalability of XFS back on the ring**. [[PDF](https://www.usenix.org/system/files/fast22-kim.pdf)]

### User-Space File System

> FUSE: **F**ilesystem in **USE**rspace, https://github.com/libfuse/libfuse

[2004 ATC] **Wayback: A User-level Versioning File System for Linux**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/usenix04/tech/freenix/cornell/cornell.pdf)]

[2015 HotStorage] **Terra Incognita: On the Practicality of User-Space File Systems**. [[PDF](https://www.usenix.org/system/files/conference/hotstorage15/hotstorage15-tarasov.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/hotstorage15_slides_tarasov.pdf)]

[2017 FAST] **To FUSE or Not to FUSE: Performance of User-Space File Systems**. [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-vangoor.pdf)]

## Distributed File System

### General Purpose File System

[1985] **Design and Implementation of the Sun Network Filesystem**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=06C4017AA8BFD7230B528C0F94A21B1D?doi=10.1.1.14.473&rep=rep1&type=pdf)]

[1987 SOSP & 1988 TOCS] AFS: **Scale and performance in a distributed file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/35037.35059)]

[2011 ATC] **TidyFS: A Simple and Small Distributed File System**. [[PDF](https://www.usenix.org/legacy/events/atc11/tech/final_files/Fetterly.pdf)] [[Slides](https://www.usenix.org/legacy/events/atc11/tech/slides/fetterly.pdf)]

* Ceph

[2004 SC] **Dynamic Metadata Management for Petabyte-scale File Systems**. [[PDF](https://ceph.com/assets/pdfs/weil-mds-sc04.pdf)]

[2006 SC] **CRUSH: Controlled, Scalable, Decentralized Placement of Replicated Data**. [[PDF](https://ceph.com/assets/pdfs/weil-crush-sc06.pdf)]

[2006 OSDI] **Ceph: A Scalable, High-Performance Distributed File System**. [[PDF](https://www.usenix.org/legacy/events/osdi06/tech/full_papers/weil/weil.pdf)]

[2007 SC] **RADOS: A Scalable, Reliable Storage Service for Petabyte-scale Storage Clusters**. [[PDF](https://ceph.com/assets/pdfs/weil-rados-pdsw07.pdf)]

[2007 Ph.D. thesis@UCSC] **Ceph: Reliable, Scalable, and High-Performance Distributed Storage**. [[PDF](https://ceph.com/assets/pdfs/weil-thesis.pdf)]

[2019 SOSP] **File systems unfit as distributed storage backends: lessons from 10 years of Ceph evolution**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3341301.3359656)]

### Big Data

[2003 SOSP] GFS: **The Google file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/945445.945450)]

[2010 MSST] **The Hadoop Distributed File System**. [[PDF](https://www.storageconference.us/2010/Papers/MSST/Shvachko.pdf)]

[2010 OSDI] **Finding a needle in Haystack: Facebook’s photo storage**. [[PDF](https://www.usenix.org/legacy/events/osdi10/tech/full_papers/Beaver.pdf)]

[2021 FAST] **Facebook’s Tectonic Filesystem: Efficiency from Exascale**. [[PDF](https://www.usenix.org/system/files/fast21-pan.pdf)]

### High Performance Computing (HPC)

[2000] **PVFS: A Parallel File System for Linux Clusters**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/als00/2000papers/papers/full_papers/carns/carns.pdf)]

[2002 FAST] **GPFS: A Shared-Disk File System for Large Computing Clusters**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/fast02/full_papers/schmuck/schmuck.pdf)]

[2003] **Lustre: Building a File System for 1,000-node Clusters**. [[PDF](https://www.kernel.org/doc/ols/2003/ols2003-pages-380-386.pdf)]

[2008 FAST] **Scalable Performance of the Panasas Parallel File System**. [[PDF](https://www.usenix.org/legacy/events/fast08/tech/full_papers/welch/welch.pdf)]

#### Burst Buffer File System

[2016 SC] BurstFS: **An Ephemeral Burst-Buffer File System for Scientific Applications**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7877147)]

[2018 CLUSTER & 2020 JCST] **GekkoFS – A temporary distributed file system for HPC applications**. [[CLUSTER PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8514892)] [[JCST PDF](https://link.springer.com/content/pdf/10.1007/s11390-020-9797-6.pdf)] [[Codes](https://storage.bsc.es/gitlab/hpc/gekkofs)]

### Metadata Management Optimization

> Key-Value Store Based

[2013 ATC] **TABLEFS: Enhancing Metadata Efficiency in the Local File System**. [[PDF](https://www.usenix.org/system/files/conference/atc13/atc13-ren.pdf)]

[2014 SC] **IndexFS: Scaling File System Metadata Performance with Stateless Caching and Bulk Insertion**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/FS/IndexFS-SC14.pdf)] [[Slides](http://www.cs.cmu.edu/afs/cs/Web/People/kair/papers/index_fs_sc_2014.pdf)]

[2015 SoCC] **ShardFS vs. IndexFS: Replication vs. Caching Strategies for Distributed Metadata Management in Cloud Storage Systems**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/CloudComputing/p236-xiao-SoCC15.pdf)]

[2015 PDSW] **DeltaFS: Exascale File Systems Scale Better Without Dedicated Servers**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/CloudComputing/p1-zheng-PDSW15.pdf)]

[2017 SC] **LocoFS: A Loosely-Coupled Metadata Service for Distributed File Systems**. [[PDF](http://storage.cs.tsinghua.edu.cn/papers/sc17-locofs.pdf/)]

### Surveys

[1989] **A Survey of Distributed File Systems**. [[PDF](https://www.cs.cmu.edu/~satya/docdir/satya89survey.pdf)]

[1990] **Distributed File Systems: Concepts and Examples**. [[PDF](https://www.isical.ac.in/~ansuman/dist_sys/DFSPaper.pdf)]

[2008 NCM] **A Taxonomy and Survey on Distributed File Systems**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=4623994)]

[2015] **Analysis of Six Distributed File Systems**. [[PDF](https://hal.inria.fr/hal-00789086/file/a_survey_of_dfs.pdf)]

[2016 ICCCA] **Evolution and Analysis of Distributed File Systems in Cloud Storage: Analytical Survey**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7813828)]
