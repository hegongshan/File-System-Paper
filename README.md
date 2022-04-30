# File System

* [1.Local File System](#local-file-system)

    * [1.1 Kernel File System](#kernel-file-system)
    
    * [1.2 User-Space File System](#user-space-file-system)
    
    * [1.3 Crash Consistency](#crash-consistency)
    
        * [1.3.1 File System Check](#file-system-check)
    
    * [1.4 Fragmentation](#fragmentation)
    
    * [1.5 Multicore/Manycore Scalability](#multicoremanycore-scalability)
    
* [2.Distributed File System](#distributed-file-system)

    * [2.1 General Purpose File System](#general-purpose-file-system)
    
    * [2.2 Big Data](#big-data)
    
    * [2.3 High Performance Computing](#high-performance-computing-hpc)
    
        * [2.3.1 Burst Buffer File System](#burst-buffer-file-system)
    
    * [2.4 Data Distribution](#data-distribution)
    
    * [2.5 Metadata Management](#metadata-management)
  
* [3.Surveys](#surveys)

* [4.Analysis](#analysis)

* [5.Object Storage](#object-storage)

## Local File System

### Kernel File System

[Linux File System](https://www.kernel.org/doc/html/latest/filesystems)

[1984 TOCS] FFS: **A Fast File System for UNIX**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/989.990)]

[1986 USENIX Summer] **Vnodes: An Architecture for Multiple File System Types in Sun UNIX**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=02078963FA44C8EBC96821CDF6B7E03D?doi=10.1.1.113.4370&rep=rep1&type=pdf)]

[1991 USENIX Winter] **Extent−like Performance from a UNIX File System**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=039E84DD92E84589651112B56EC7D240?doi=10.1.1.26.2218&rep=rep1&type=pdf)]

[1991 SOSP] LFS: **The Design and Implementation of a Log-Structured File System**. [[PDF](https://people.eecs.berkeley.edu/~brewer/cs262/LFS.pdf)]

[1995] **Design and Implementation of the Second Extended Filesystem**. [[PDF](http://e2fsprogs.sourceforge.net/ext2intro.html)]

[1996 ATC] **Scalability in the XFS File System**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/sd96/full_papers/sweeney.ps)]

[1998 LinuxExpo] ext3: **Journaling the Linux ext2fs Filesystem**. [[PDF](https://pdos.csail.mit.edu/6.828/2020/readings/journal-design.pdf)]

[2005 ATC] **Analysis and Evolution of Journaling File Systems**. [[PDF](https://www.usenix.org/legacy/events/usenix05/tech/general/full_papers/prabhakaran/prabhakaran.pdf)]

[2006 SIGOPS Operating Systems Review] NILFS: **The Linux implementation of a log-structured file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1151374.1151375)]

[2007] **The new ext4 filesystem: Current status and future plans**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.111.798&rep=rep1&type=pdf#page=21)]

[2013 FAST] **A Study of Linux File System Evolution**. [[PDF](https://www.usenix.org/system/files/conference/fast13/fast13-final75_0.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/lu_fast13_slides.pdf)]

[2013 TOS] **BTRFS: The Linux B-Tree Filesystem**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/2501620.2501623)]

[2015 FAST] **F2FS: A New File System for Flash Storage**. [[PDF](https://www.usenix.org/system/files/conference/fast15/fast15-paper-lee.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast15_slides_lee.pdf)]


### User-Space File System

> FUSE: **F**ilesystem in **USE**rspace, https://github.com/libfuse/libfuse

[2004 ATC] **Wayback: A User-level Versioning File System for Linux**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/usenix04/tech/freenix/cornell/cornell.pdf)]

[2010 SAC] **Performance and Extension of User Space File Systems**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1774088.1774130)]

[2011 EuroSys] **Refuse to crash with Re-FUSE**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1966445.1966453)]

[2015 HotStorage] **Terra Incognita: On the Practicality of User-Space File Systems**. [[PDF](https://www.usenix.org/system/files/conference/hotstorage15/hotstorage15-tarasov.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/hotstorage15_slides_tarasov.pdf)]

[2017 FAST] **To FUSE or Not to FUSE: Performance of User-Space File Systems**. [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-vangoor.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast17_slides_vangoor.pdf)]

[2019 TOS] **Performance and Resource Utilization of FUSE User-Space File Systems**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3310148)]

[2019 ATC] ExtFUSE: **Extension Framework for File Systems in User space**. [[PDF](https://www.usenix.org/system/files/atc19-bijlani.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc19_slides_bijlani.pdf)]

[2021 ATC] **XFUSE: An Infrastructure for Running Filesystem Services in User Space**. [[PDF](https://www.usenix.org/system/files/atc21-huai.pdf)] [[Slides](https://www.usenix.org/system/files/atc21_slides_huai.pdf)]

### Crash Consistency

[2012 FAST] **Consistency Without Ordering**. [[PDF](https://www.usenix.org/legacy/event/fast/tech/full_papers/Chidambaram.pdf)] [[Slides](https://research.cs.wisc.edu/adsl/Publications/nofs-fast12-slides.pdf)] [[Codes](https://github.com/utsaslab/nofs)]

[2013 SOSP] **Optimistic Crash Consistency**. [[PDF](https://research.cs.wisc.edu/adsl/Publications/optfs-sosp13.pdf)] [[Slides](https://research.cs.wisc.edu/adsl/Publications/optfs-sosp13-slides.pdf)] [[Codes](https://github.com/utsaslab/optfs)]

[2017 TOS] **Application Crash Consistency and Performance with CCFS**. [[PDF](https://research.cs.wisc.edu/adsl/Publications/ccfs-tos17.pdf)]

#### File System Check

[1983] **Fsck − The UNIX File System Check Program**. [[PDF](https://docs.freebsd.org/44doc/smm/03.fsck/paper.pdf)]

[2008 OSDI] **SQCK: A Declarative File System Checker**. [[PDF](https://www.usenix.org/legacy/events/osdi08/tech/full_papers/gunawi/gunawi.pdf)]

[2013 FAST] **ffsck: The Fast File System Checker**. [[PDF](https://research.cs.wisc.edu/wind/Publications/ffsck-fast13.pdf)]

[2018 TOS] **Towards Robust File System Checkers**. [[PDF](https://www.researchgate.net/profile/Vyacheslav-Dubeyko/publication/329404304_Towards_Robust_File_System_Checkers/links/5ef11e2d92851ce9e7fcb189/Towards-Robust-File-System-Checkers.pdf)]

[2021 FAST] **pFSCK: Accelerating File System Checking and Repair for Modern Storage**. [[PDF](https://www.usenix.org/system/files/fast21-domingo.pdf)]

### Fragmentation

[2016 HotStorage] **An Empirical Study of File-System Fragmentation in Mobile Storage Systems**. [[PDF](https://www.usenix.org/system/files/conference/hotstorage16/hotstorage16_ji.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc16_slides_ji.pdf)]

[2017 FAST] **File Systems Fated for Senescence? Nonsense, Says Science!** [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-conway.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast17_slides_conway.pdf)]

[2017 ATC] **Improving File System Performance of Mobile Storage Systems Using a Decoupled Defragmenter**. [[PDF](https://www.usenix.org/system/files/conference/atc17/atc17-hahn.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc17_slides_hahn.pdf)]


### Multicore/Manycore Scalability

[2016 ATC] **Understanding Manycore Scalability of File Systems**. [[PDF](https://www.usenix.org/system/files/conference/atc16/atc16_paper-min.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc16_slides_min.pdf)]

[2017 SOSP] ScaleFS: **Scaling a File System to Many Cores Using an Operation Log**. [[PDF](https://pdos.csail.mit.edu/papers/scalefs.pdf)]

[2022 FAST] **ScaleXFS: Getting scalability of XFS back on the ring**. [[PDF](https://www.usenix.org/system/files/fast22-kim.pdf)]

## Distributed File System

### General Purpose File System

[1985] **Design and Implementation of the Sun Network Filesystem**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=06C4017AA8BFD7230B528C0F94A21B1D?doi=10.1.1.14.473&rep=rep1&type=pdf)]

[1987 SOSP & 1988 TOCS] AFS: **Scale and performance in a distributed file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/35037.35059)]

[1993 SOSP & 1995 TOCS] **The Zebra Striped Network File System**. [[PDF](http://people.eecs.berkeley.edu/~prabal/resources/osprelim/HO93.pdf)] [[Ph.D. Thesis](https://www.researchgate.net/profile/John-Ousterhout/publication/220439180_The_Zebra_Striped_Network/links/53e296890cf275a5fdda2eca/The-Zebra-Striped-Network.pdf)]

[2003 MSST] **zFS - A Scalable Distributed File System Using Object Disks**. [[PDF](https://www.storageconference.us/2003/papers/29-Rodeh-zFS.pdf)] [[Slides](https://storageconference.us/2003/presentations/D02-Teperman.pdf)]

[2006 OSDI] **Ceph: A Scalable, High-Performance Distributed File System**. [[PDF](https://www.usenix.org/legacy/events/osdi06/tech/full_papers/weil/weil.pdf)]

[2007 SC] **RADOS: A Scalable, Reliable Storage Service for Petabyte-scale Storage Clusters**. [[PDF](https://ceph.com/assets/pdfs/weil-rados-pdsw07.pdf)]

[2007 Ph.D. Thesis@UCSC] **Ceph: Reliable, Scalable, and High-Performance Distributed Storage**. [[PDF](https://ceph.com/assets/pdfs/weil-thesis.pdf)]

[2011 ATC] **TidyFS: A Simple and Small Distributed File System**. [[PDF](https://www.usenix.org/legacy/events/atc11/tech/final_files/Fetterly.pdf)] [[Slides](https://www.usenix.org/legacy/events/atc11/tech/slides/fetterly.pdf)]

[2019 SOSP] **File systems unfit as distributed storage backends: lessons from 10 years of Ceph evolution**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3341301.3359656)] [[Slides](https://sosp19.rcs.uwaterloo.ca/slides/aghayev.odp)]

### Big Data

[2003 SOSP] GFS: **The Google file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/945445.945450)]

[2010 MSST] **The Hadoop Distributed File System**. [[PDF](https://www.storageconference.us/2010/Papers/MSST/Shvachko.pdf)]

[2021 FAST] **Facebook’s Tectonic Filesystem: Efficiency from Exascale**. [[PDF](https://www.usenix.org/system/files/fast21-pan.pdf)]

### High Performance Computing (HPC)

[2000] **PVFS: A Parallel File System for Linux Clusters**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/als00/2000papers/papers/full_papers/carns/carns.pdf)]

[2002 FAST] **GPFS: A Shared-Disk File System for Large Computing Clusters**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/fast02/full_papers/schmuck/schmuck.pdf)]

[2003] **Lustre: Building a File System for 1,000-node Clusters**. [[PDF](https://www.kernel.org/doc/ols/2003/ols2003-pages-380-386.pdf)]

[2008 FAST] **Scalable Performance of the Panasas Parallel File System**. [[PDF](https://www.usenix.org/legacy/events/fast08/tech/full_papers/welch/welch.pdf)]

#### Burst Buffer File System

[2016 SC] BurstFS: **An Ephemeral Burst-Buffer File System for Scientific Applications**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7877147)]

[2018 CLUSTER & 2020 JCST] **GekkoFS – A temporary distributed file system for HPC applications**. [[CLUSTER PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8514892)] [[JCST PDF](https://link.springer.com/content/pdf/10.1007/s11390-020-9797-6.pdf)] [[Codes](https://storage.bsc.es/gitlab/hpc/gekkofs)]

### Data Distribution

[2006 SC] **CRUSH: Controlled, Scalable, Decentralized Placement of Replicated Data**. [[PDF](https://ceph.com/assets/pdfs/weil-crush-sc06.pdf)]

[2020 FAST] **MAPX: Controlled Data Migration in the Expansion of Decentralized Object-Based Storage Systems**. [[PDF](https://www.usenix.org/system/files/fast20-wang_li.pdf)]

### Metadata Management

[2003 MSST] **Efficient Metadata Management in Large Distributed Storage Systems**. [[PDF](https://www.storageconference.us/2003/papers/36-Brandt-Efficient.pdf)] [[Slides](https://www.storageconference.us/2003/presentations/D09-Brandt.pdf)]

[2004 SC] **Dynamic Metadata Management for Petabyte-scale File Systems**. [[PDF](https://ceph.com/assets/pdfs/weil-mds-sc04.pdf)]

* Key-Value Store based

[2013 ATC] **TABLEFS: Enhancing Metadata Efficiency in the Local File System**. [[PDF](https://www.usenix.org/system/files/conference/atc13/atc13-ren.pdf)]

[2014 SC] **IndexFS: Scaling File System Metadata Performance with Stateless Caching and Bulk Insertion**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/FS/IndexFS-SC14.pdf)] [[Slides](http://www.cs.cmu.edu/afs/cs/Web/People/kair/papers/index_fs_sc_2014.pdf)]

[2015 SoCC] **ShardFS vs. IndexFS: Replication vs. Caching Strategies for Distributed Metadata Management in Cloud Storage Systems**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/CloudComputing/p236-xiao-SoCC15.pdf)]

[2015 PDSW] **DeltaFS: Exascale File Systems Scale Better Without Dedicated Servers**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/CloudComputing/p1-zheng-PDSW15.pdf)]

[2017 SC] **LocoFS: A Loosely-Coupled Metadata Service for Distributed File Systems**. [[PDF](http://storage.cs.tsinghua.edu.cn/papers/sc17-locofs.pdf/)]

[2018 TPDS] **A Flattened Metadata Service for Distributed File Systems**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8370078)]

[2022 FAST] **InfiniFS: An Efficient Metadata Service for Large-Scale Distributed Filesystems**. [[PDF](https://www.usenix.org/system/files/fast22-lv.pdf)] [[Slides](https://www.usenix.org/system/files/fast22_slides_lv.pdf)]

* Load Balance

[2015 SC] **Mantle: a programmable metadata load balancer for the ceph file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/2807591.2807607)]

[2021 SC] **Lunule: An Agile and Judicious Metadata Load Balancer for CephFS**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3458817.3476196)]

### Surveys

[1989] **A Survey of Distributed File Systems**. [[PDF](https://www.cs.cmu.edu/~satya/docdir/satya89survey.pdf)]

[1990] **Distributed File Systems: Concepts and Examples**. [[PDF](https://www.isical.ac.in/~ansuman/dist_sys/DFSPaper.pdf)]

[2008 NCM] **A Taxonomy and Survey on Distributed File Systems**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=4623994)]

[2015] **Analysis of Six Distributed File Systems**. [[PDF](https://hal.inria.fr/hal-00789086/file/a_survey_of_dfs.pdf)]

[2016 ICCCA] **Evolution and Analysis of Distributed File Systems in Cloud Storage: Analytical Survey**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7813828)]

[2018 CSUR] **Scalable Metadata Management Techniques for Ultra-Large Distributed Storage Systems – A Systematic Review**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3212686)]

### Analysis

[2000 ATC] **A Comparison of File System Workloads**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/usenix2000/general/full_papers/roselli/roselli.pdf)]

## Object Storage

[2003 MSST] **Towards an Object Store**. [[PDF](https://www.storageconference.us/2003/papers/24-Azagury-Towards.pdf)] [[Slides](https://www.storageconference.us/2003/presentations/C07-Azagury.pdf)]

[2004 MSST] **OBFS: A File System for Object-based Storage Devices**. [[PDF](https://www.storageconference.us/2004/Papers/33-Wang-a.pdf)] [[Slides](https://www.storageconference.us/2004/Presentations/33r1.pdf)]

[2010 OSDI] **Finding a needle in Haystack: Facebook’s photo storage**. [[PDF](https://www.usenix.org/legacy/event/osdi10/tech/full_papers/Beaver.pdf)] [[Slides](https://www.usenix.org/legacy/events/osdi10/tech/slides/beaver.pdf)]

[2020 SCFA] **DAOS: A Scale-Out High Performance Storage Stack for Storage Class Memory**. [[PDF](https://www.researchgate.net/publication/341844608_DAOS_A_Scale-Out_High_Performance_Storage_Stack_for_Storage_Class_Memory)]

