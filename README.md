# File System

* [1.Local File System](#local-file-system)
  
    * [1.1 Kernel File System](#kernel-file-system)
    
    * [1.2 User-Space File System](#user-space-file-system)
    
    * [1.3 Crash Consistency](#crash-consistency)
      
        * [1.3.1 File System Checker](#file-system-checker)
        
        * [1.3.2 Others](#others)
    
    * [1.4 Fragmentation](#fragmentation)
    
    * [1.5 Multicore/Manycore Scalability](#multicoremanycore-scalability)

* [2.Distributed File System](#distributed-file-system)

    * [2.1 General Purpose File System](#general-purpose-file-system)

    * [2.2 Big Data](#big-data)
    
    * [2.3 High Performance Computing](#high-performance-computing-hpc)
    
        * [2.3.2 Parallel File System](#parallel-file-system)
        
        * [2.3.1 Burst Buffer File System](#burst-buffer-file-system)
    
    * [2.4 Cloud Computing](#cloud-computing)
    
    * [2.5 Artificial Intelligence](#artificial-intelligence)
    
        * [2.5.1 AI for Storage](#ai-for-storage)

    * [2.6 Data Distribution](#data-distribution)
    
    * [2.7 Metadata Management](#metadata-management)
    
    * [2.8 Fault Tolerance](#fault-tolerance)
      
        * [2.8.1 Replication](#replication)
          
        * [2.8.2 Erasure Coding](#erasure-coding)

    * [2.9 Hardware Optimization](#hardware-optimization)

* [3.Other Topics](#other-topics)
    
    * [3.1 Data Reduction](#data-reduction)
        
        * [3.1.1 Data Deduplication](#data-deduplication)
        
    * [3.2 Security](#security)
    
* [4.Surveys](#surveys)

* [5.Analysis](#analysis)

* [6.Object Storage](#object-storage)

* [7.New Hardware](#new-hardware)

## Local File System

### Kernel File System

> Linux File System, https://www.kernel.org/doc/html/latest/filesystems

[1974 CACM] Old UNIX File System: **The UNIX Time-Sharing System**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/361011.361061)]

[1984 TOCS] FFS: **A Fast File System for UNIX**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/989.990)]

[1986 USENIX Summer] **Vnodes: An Architecture for Multiple File System Types in Sun UNIX**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=02078963FA44C8EBC96821CDF6B7E03D?doi=10.1.1.113.4370&rep=rep1&type=pdf)]

[1991 USENIX Winter] **Extent−like Performance from a UNIX File System**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=039E84DD92E84589651112B56EC7D240?doi=10.1.1.26.2218&rep=rep1&type=pdf)]

[1991 SOSP] LFS: **The Design and Implementation of a Log-Structured File System**. [[PDF](https://people.eecs.berkeley.edu/~brewer/cs262/LFS.pdf)]

[1993 USENIX Winter] **An Implementation of a Log-Structured File System for UNIX**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/sd93/seltzer.pdf)]

[1995] **Design and Implementation of the Second Extended Filesystem**. [[PDF](http://e2fsprogs.sourceforge.net/ext2intro.html)]

[1996 ATC] **Scalability in the XFS File System**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/sd96/full_papers/sweeney.ps)]

[1998 LinuxExpo] ext3: **Journaling the Linux ext2fs Filesystem**. [[PDF](https://pdos.csail.mit.edu/6.828/2020/readings/journal-design.pdf)]

[2001 Ottawa linux symposium] **JFFS: The Journalling Flash File System**. [[PDF](https://www.kernel.org/doc/mirror/ols2001/jffs2.pdf)]

[2003 FAST] ZFS: **The Zettabyte File System**. [[PDF](https://courses.cs.washington.edu/courses/cse451/22sp/lectures/zfs_overview.pdf)]

[2006 SIGOPS Operating Systems Review] NILFS: **The Linux implementation of a log-structured file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1151374.1151375)]

[2007] **The new ext4 filesystem: Current status and future plans**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.111.798&rep=rep1&type=pdf#page=21)]

[2013 TOS] **BTRFS: The Linux B-Tree Filesystem**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/2501620.2501623)]

[2015 FAST] **F2FS: A New File System for Flash Storage**. [[PDF](https://www.usenix.org/system/files/conference/fast15/fast15-paper-lee.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast15_slides_lee.pdf)]

[2019 ATC] **EROFS: A Compression-friendly Readonly File System for Resource-scarce Devices**. [[PDF](https://www.usenix.org/system/files/atc19-gao.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc19_slides_gao.pdf)]

[2020 VAULT] **zonefs: Mapping POSIX File System Interface to Raw Zoned Block Device Accesses**. [[Slides](https://www.usenix.org/system/files/vault20_slides_moal.pdf)]

### User-Space File System

> FUSE: **F**ilesystem in **USE**rspace, https://github.com/libfuse/libfuse

[2004 ATC] **Wayback: A User-level Versioning File System for Linux**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/usenix04/tech/freenix/cornell/cornell.pdf)]

[2010 SAC] **Performance and Extension of User Space File Systems**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1774088.1774130)]

[2010 MSST] LTFS: **The Linear Tape File System**. [[PDF](https://msstconference.org/MSST-history/2010/Papers/MSST/Pease.pdf)] [[Codes](https://github.com/LinearTapeFileSystem/ltfs)]

[2011 EuroSys] **Refuse to crash with Re-FUSE**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1966445.1966453)]

[2013 ATC] **TABLEFS: Enhancing Metadata Efficiency in the Local File System**. [[PDF](https://www.usenix.org/system/files/conference/atc13/atc13-ren.pdf)]

[2015 HotStorage] **Terra Incognita: On the Practicality of User-Space File Systems**. [[PDF](https://www.usenix.org/system/files/conference/hotstorage15/hotstorage15-tarasov.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/hotstorage15_slides_tarasov.pdf)]

[2016 FAST] **The Composite-file File System: Decoupling the One-to-one Mapping of Files and Metadata for Better Performance**. [[PDF](https://www.usenix.org/system/files/conference/fast16/fast16-papers-zhang-shuanglong.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast16_slides_zhang61.pdf)]

[2017 FAST] **To FUSE or Not to FUSE: Performance of User-Space File Systems**. [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-vangoor.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast17_slides_vangoor.pdf)]

[2018 ROSS] **Direct-FUSE: Removing the Middleman for High-Performance FUSE File System Support**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3217189.3217195)] [[Codes](https://github.com/LLNL/direct-fuse)]

[2019 TOS] **Performance and Resource Utilization of FUSE User-Space File Systems**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3310148)]

[2019 ATC] ExtFUSE: **Extension Framework for File Systems in User space**. [[PDF](https://www.usenix.org/system/files/atc19-bijlani.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc19_slides_bijlani.pdf)]

[2021 ATC] **XFUSE: An Infrastructure for Running Filesystem Services in User Space**. [[PDF](https://www.usenix.org/system/files/atc21-huai.pdf)] [[Slides](https://www.usenix.org/system/files/atc21_slides_huai.pdf)]

[2022 TOS] **DEFUSE: An Interface for Fast and Correct User Space File System Access**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3494556)]

[2024 FAST] **RFUSE: Modernizing Userspace Filesystem Framework through Scalable Kernel-Userspace Communication**. [[PDF](https://www.usenix.org/system/files/fast24-cho.pdf)] [[Slides](https://www.usenix.org/system/files/fast24_slides-cho.pdf)]

### Crash Consistency

#### File System Checker

[1983] **Fsck − The UNIX File System Check Program**. [[PDF](https://docs.freebsd.org/44doc/smm/03.fsck/paper.pdf)]

[2008 OSDI] **SQCK: A Declarative File System Checker**. [[PDF](https://www.usenix.org/legacy/events/osdi08/tech/full_papers/gunawi/gunawi.pdf)]

[2013 FAST] **ffsck: The Fast File System Checker**. [[PDF](https://research.cs.wisc.edu/wind/Publications/ffsck-fast13.pdf)]

[2018 TOS] **Towards Robust File System Checkers**. [[PDF](https://www.researchgate.net/profile/Vyacheslav-Dubeyko/publication/329404304_Towards_Robust_File_System_Checkers/links/5ef11e2d92851ce9e7fcb189/Towards-Robust-File-System-Checkers.pdf)]

[2021 FAST] **pFSCK: Accelerating File System Checking and Repair for Modern Storage**. [[PDF](https://www.usenix.org/system/files/fast21-domingo.pdf)]

#### Others

[2012 FAST] **Consistency Without Ordering**. [[PDF](https://www.usenix.org/legacy/event/fast/tech/full_papers/Chidambaram.pdf)] [[Slides](https://research.cs.wisc.edu/adsl/Publications/nofs-fast12-slides.pdf)] [[Codes](https://github.com/utsaslab/nofs)]

[2013 SOSP] **Optimistic Crash Consistency**. [[PDF](https://research.cs.wisc.edu/adsl/Publications/optfs-sosp13.pdf)] [[Slides](https://research.cs.wisc.edu/adsl/Publications/optfs-sosp13-slides.pdf)] [[Codes](https://github.com/utsaslab/optfs)]

[2017 TOS] **Application Crash Consistency and Performance with CCFS**. [[PDF](https://research.cs.wisc.edu/adsl/Publications/ccfs-tos17.pdf)]

### Fragmentation

[2016 HotStorage] **An Empirical Study of File-System Fragmentation in Mobile Storage Systems**. [[PDF](https://www.usenix.org/system/files/conference/hotstorage16/hotstorage16_ji.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc16_slides_ji.pdf)]

[2017 FAST] **File Systems Fated for Senescence? Nonsense, Says Science!** [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-conway.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast17_slides_conway.pdf)]

[2017 ATC] **Improving File System Performance of Mobile Storage Systems Using a Decoupled Defragmenter**. [[PDF](https://www.usenix.org/system/files/conference/atc17/atc17-hahn.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc17_slides_hahn.pdf)]

[2024 FAST] **We Ain't Afraid of No File Fragmentation: Causes and Prevention of Its Performance Impact on Modern Flash SSDs**. [[PDF](https://www.usenix.org/system/files/fast24-jun.pdf)] [[Slides](https://www.usenix.org/system/files/fast24_slides-jun.pdf)]

### Multicore/Manycore Scalability

[2016 ATC] **Understanding Manycore Scalability of File Systems**. [[PDF](https://www.usenix.org/system/files/conference/atc16/atc16_paper-min.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc16_slides_min.pdf)]

[2017 SOSP] ScaleFS: **Scaling a File System to Many Cores Using an Operation Log**. [[PDF](https://pdos.csail.mit.edu/papers/scalefs.pdf)]

[2022 FAST] **ScaleXFS: Getting scalability of XFS back on the ring**. [[PDF](https://www.usenix.org/system/files/fast22-kim.pdf)]

## Distributed File System

### General Purpose File System

[1985] **Design and Implementation of the Sun Network Filesystem**. [[PDF](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=06C4017AA8BFD7230B528C0F94A21B1D?doi=10.1.1.14.473&rep=rep1&type=pdf)]

[1987 SOSP & 1988 TOCS] AFS: **Scale and performance in a distributed file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/35037.35059)]

[1993 SOSP & 1995 TOCS] **The Zebra Striped Network File System**. [[PDF](http://people.eecs.berkeley.edu/~prabal/resources/osprelim/HO93.pdf)] [[Ph.D. Thesis](https://www.researchgate.net/profile/John-Ousterhout/publication/220439180_The_Zebra_Striped_Network/links/53e296890cf275a5fdda2eca/The-Zebra-Striped-Network.pdf)]

[2003 MSST] **zFS - A Scalable Distributed File System Using Object Disks**. [[PDF](https://msstconference.org/MSST-history/2003/papers/29-Rodeh-zFS.pdf)] [[Slides](https://msstconference.org/MSST-history/2003/presentations/D02-Teperman.pdf)]

[2006 OSDI] **Ceph: A Scalable, High-Performance Distributed File System**. [[PDF](https://www.usenix.org/legacy/events/osdi06/tech/full_papers/weil/weil.pdf)]

[2007 SC] **RADOS: A Scalable, Reliable Storage Service for Petabyte-scale Storage Clusters**. [[PDF](https://ceph.com/assets/pdfs/weil-rados-pdsw07.pdf)]

[2007 Ph.D. Thesis@UCSC] **Ceph: Reliable, Scalable, and High-Performance Distributed Storage**. [[PDF](https://ceph.com/assets/pdfs/weil-thesis.pdf)]

[2011 ATC] **TidyFS: A Simple and Small Distributed File System**. [[PDF](https://www.usenix.org/legacy/events/atc11/tech/final_files/Fetterly.pdf)] [[Slides](https://www.usenix.org/legacy/events/atc11/tech/slides/fetterly.pdf)]

[2019 SOSP] **File systems unfit as distributed storage backends: lessons from 10 years of Ceph evolution**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3341301.3359656)] [[Slides](https://sosp19.rcs.uwaterloo.ca/slides/aghayev.odp)]

### Big Data

[2003 SOSP] GFS: **The Google File System**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/945445.945450)]

[2010 MSST] HDFS: **The Hadoop Distributed File System**. [[PDF](https://msstconference.org/MSST-history/2010/Papers/MSST/Shvachko.pdf)] [[Slides](https://msstconference.org/MSST-history/2010/Presentations/Research/9.Shvachko.pdf)]

[2013 VLDB] QFS: **The Quantcast File System**. [[PDF](https://vldb.org/pvldb/vol6/p1092-ovsiannikov.pdf)] [[Codes](https://github.com/quantcast/qfs)]

[2021 FAST] **Facebook’s Tectonic Filesystem: Efficiency from Exascale**. [[PDF](https://www.usenix.org/system/files/fast21-pan.pdf)]

[2023 FAST] **More Than Capacity: Performance-Oriented Evolution of Pangu in Alibaba**. [[PDF](https://www.usenix.org/system/files/fast23-li-qiang_more.pdf)] [[Video](https://www.youtube.com/watch?v=Twss7x3Ib2Q)]

### High Performance Computing (HPC)

#### Parallel File System

[2000] **PVFS: A Parallel File System for Linux Clusters**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/als00/2000papers/papers/full_papers/carns/carns.pdf)]

[2002 FAST] **GPFS: A Shared-Disk File System for Large Computing Clusters**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/fast02/full_papers/schmuck/schmuck.pdf)]

[2003] **Lustre: Building a File System for 1,000-node Clusters**. [[PDF](https://www.kernel.org/doc/ols/2003/ols2003-pages-380-386.pdf)]

[2008 FAST] **Scalable Performance of the Panasas Parallel File System**. [[PDF](https://www.usenix.org/legacy/events/fast08/tech/full_papers/welch/welch.pdf)]

#### Burst Buffer File System

[2009 SC] **PLFS: A Checkpoint Filesystem for Parallel Applications**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/PDSI/plfs.pdf)] [[Codes](https://github.com/plfs/plfs-core)]

[2016 SC] BurstFS: **An Ephemeral Burst-Buffer File System for Scientific Applications**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7877147)]

[2018 CLUSTER & 2020 JCST] **GekkoFS – A temporary distributed file system for HPC applications**. [[CLUSTER PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8514892)] [[JCST PDF](https://link.springer.com/content/pdf/10.1007/s11390-020-9797-6.pdf)] [[Codes](https://storage.bsc.es/gitlab/hpc/gekkofs)]

[2020 JCST] **Gfarm/BB — Gfarm File System for Node-Local Burst Buffer**. [[PDF](https://link.springer.com/content/pdf/10.1007/s11390-020-9803-z.pdf)] [[Codes](https://github.com/oss-tsukuba/gfarm)]

[2022 HPCAsia] **CHFS: Parallel Consistent Hashing File System for Node-local Persistent Memory**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3492805.3492807)] [[Codes](https://github.com/otatebe/chfs)]

[2023 FAST] **HadaFS: A File System Bridging the Local and Shared Burst Buffer for Exascale Supercomputers**. [[PDF](https://www.usenix.org/system/files/fast23-he.pdf)] [[Video](https://www.youtube.com/watch?v=l-pwBIewqno)]

[2023 IPDPS] **UnifyFS: A User-level Shared File System for Unified Access to Distributed Local Storage**. [[PDF](https://www.osti.gov/servlets/purl/1995690)] [[Codes](https://github.com/LLNL/UnifyFS)] [[Relevant Slides](https://hpckp.org/wp-content/uploads/2022/10/09-UnifyFS-HPCKP20.pdf)]

### Cloud Computing

[2018 VLDB] **PolarFS: An Ultra-low Latency and Failure Resilient Distributed File System for Shared Storage Cloud Database**. [[PDF](http://www.vldb.org/pvldb/vol11/p1849-cao.pdf)]

[2019 SIGMOD] **CFS: A Distributed File System for Large Scale Container Platforms**. [[PDF](https://arxiv.org/pdf/1911.03001.pdf)]

### Artificial Intelligence

#### AI for Storage

[2021 FAST] **Learning Cache Replacement with CACHEUS**. [[PDF](https://www.usenix.org/system/files/fast21-rodriguez.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast21_slides_yusuf.pdf)]

[2023 FAST] **GL-Cache: Group-level learning for efficient and high-performance caching**. [[PDF](https://www.usenix.org/system/files/fast23-yang.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast23_slides_yang-juncheng.pdf)] [[Codes](https://github.com/Thesys-lab/fast23-glcache)]

[2024 FAST] **Baleen: ML Admission & Prefetching for Flash Caches**. [[PDF](https://www.usenix.org/system/files/fast24-wong.pdf)] [[Slides](https://www.usenix.org/system/files/fast24_slides-wong.pdf)] [[Codes](https://github.com/wonglkd/Baleen-FAST24)] [[Dataset](https://ftp.pdl.cmu.edu/pub/datasets/Baleen24/)]

### Data Distribution

[1997 STOC] **Consistent Hashing and Random Trees: Distributed Caching Protocols for Relieving Hot Spots on the World Wide Web**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/258533.258660)]

[2006 SC] **CRUSH: Controlled, Scalable, Decentralized Placement of Replicated Data**. [[PDF](https://ceph.com/assets/pdfs/weil-crush-sc06.pdf)]

[2020 FAST] **MAPX: Controlled Data Migration in the Expansion of Decentralized Object-Based Storage Systems**. [[PDF](https://www.usenix.org/system/files/fast20-wang_li.pdf)]

### Metadata Management

[2003 MSST] **Efficient Metadata Management in Large Distributed Storage Systems**. [[PDF](https://msstconference.org/MSST-history/2003/papers/36-Brandt-Efficient.pdf)] [[Slides](https://msstconference.org/MSST-history/2003/presentations/D09-Brandt.pdf)]

[2004 SC] **Dynamic Metadata Management for Petabyte-scale File Systems**. [[PDF](https://ceph.com/assets/pdfs/weil-mds-sc04.pdf)]

[2011 FAST] **Scale and Concurrency of GIGA+: File System Directories with Millions of Files**. [[PDF](https://www.usenix.org/legacy/event/fast11/tech/full_papers/PatilNew.pdf)]

[2014 SC] **IndexFS: Scaling File System Metadata Performance with Stateless Caching and Bulk Insertion**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/FS/IndexFS-SC14.pdf)] [[Slides](http://www.cs.cmu.edu/afs/cs/Web/People/kair/papers/index_fs_sc_2014.pdf)]

[2015 FAST] **CalvinFS: Consistent WAN Replication and Scalable Metadata Management for Distributed File Systems**. [[PDF](https://www.usenix.org/system/files/conference/fast15/fast15-paper-thomson.pdf)]

[2015 SoCC] **ShardFS vs. IndexFS: Replication vs. Caching Strategies for Distributed Metadata Management in Cloud Storage Systems**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/CloudComputing/p236-xiao-SoCC15.pdf)]

[2015 PDSW] **DeltaFS: Exascale File Systems Scale Better Without Dedicated Servers**. [[PDF](https://www.pdl.cmu.edu/PDL-FTP/CloudComputing/p1-zheng-PDSW15.pdf)]

[2017 FAST] **HopsFS: Scaling Hierarchical File System Metadata Using NewSQL Databases**. [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-niazi.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast17_slides_niazi.pdf)]

[2017 SC] **LocoFS: A Loosely-Coupled Metadata Service for Distributed File Systems**. [[PDF](http://storage.cs.tsinghua.edu.cn/papers/sc17-locofs.pdf/)]

[2018 TPDS] **A Flattened Metadata Service for Distributed File Systems**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8370078)]

[2022 FAST] **InfiniFS: An Efficient Metadata Service for Large-Scale Distributed Filesystems**. [[PDF](https://www.usenix.org/system/files/fast22-lv.pdf)] [[Slides](https://www.usenix.org/system/files/fast22_slides_lv.pdf)]

[2023 ATC] **SingularFS: A Billion-Scale Distributed File System Using a Single Metadata Server**. [[PDF](https://www.usenix.org/system/files/atc23-guo.pdf)] [[Slides](https://www.usenix.org/system/files/atc23_slides_guo.pdf)]

* Load Balance

[2015 SC] **Mantle: a programmable metadata load balancer for the ceph file system**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/2807591.2807607)]

[2021 SC] **Lunule: An Agile and Judicious Metadata Load Balancer for CephFS**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3458817.3476196)]

### Fault Tolerance

#### Replication

* Primary-backup Replication

[1976 ICSE] **A principle for resilient sharing of distributed resources**. [[PDF](https://dl.acm.org/doi/pdf/10.5555/800253.807732)]

* Chain Replication

[2004 OSDI] **Chain Replication for Supporting High Throughput and Availability**. [[PDF](https://www.usenix.org/legacy/events/osdi04/tech/full_papers/renesse/renesse.pdf)]

* Consensus-based Replication

[1998 TOCS] Paxos: **The Part-Time Parliament**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/279227.279229)]

[2001 ACM SIGACT News] **Paxos Made Simple**. [[PDF](https://lamport.azurewebsites.net/pubs/paxos-simple.pdf)]

[2014 ATC] Raft: **In Search of an Understandable Consensus Algorithm**. [[PDF](https://www.usenix.org/system/files/conference/atc14/atc14-paper-ongaro.pdf)]

#### Erasure Coding

[2012 ATC] **Erasure Coding in Windows Azure Storage**. [[PDF](https://www.usenix.org/system/files/conference/atc12/atc12-final181_0.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/huang_atc12_slides_0.pdf)]

[2015 FAST] **A Tale of Two Erasure Codes in HDFS**. [[PDF](https://www.usenix.org/system/files/conference/fast15/fast15-paper-xia.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast15_xia_slides.pdf)]

[2018 FAST] **Clay Codes: Moulding MDS Codes to Yield an MSR Code**. [[PDF](https://www.usenix.org/system/files/conference/fast18/fast18-vajha.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast18_slides_vajha.pdf)]

### Hardware Optimization

[2017 ATC] **Octopus: an RDMA-enabled Distributed Persistent Memory File System**. [[PDF](https://www.usenix.org/system/files/conference/atc17/atc17-lu.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/atc17_slides_chen_0.pdf)]

[2020 OSDI] **Assise: Performance and Availability via Client-local NVM in a Distributed File System**. [[PDF](https://www.usenix.org/system/files/osdi20-anderson.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/osdi20_slides_anderson.pdf)]

[2021 SOSP] **LineFS: Efficient SmartNIC Offload of a Distributed File System with Pipeline Parallelism**. [[PDF](https://mcanini.github.io/papers/linefs.sosp21.pdf)]

## Other Topics

### Data Reduction

#### Data Deduplication

[2001 SOSP] LBFS: **A Low-bandwidth Network File System**. [[PDF](https://www.sosp.org/2001/papers/mazieres.pdf)]

[2008 FAST] **Avoiding the Disk Bottleneck in the Data Domain Deduplication File System**. [[PDF](https://www.usenix.org/legacy/event/fast08/tech/full_papers/zhu/zhu.pdf)]

[2009 FAST] **Sparse Indexing: Large Scale, Inline Deduplication Using Sampling and Locality**. [[PDF](https://www.usenix.org/legacy/event/fast09/tech/full_papers/lillibridge/lillibridge.pdf)] [[Slides](https://www.usenix.org/legacy/event/fast09/tech/slides/lillibridge.pdf)]

[2009 ATC] **Decentralized Deduplication in SAN Cluster File Systems**. [[PDF](https://www.usenix.org/legacy/events/usenix09/tech/full_papers/clements/clements.pdf)] [[Slides](https://www.usenix.org/legacy/events/usenix09/tech/slides/clements.pdf)]

[2010 FAST] **I/O Deduplication: Utilizing Content Similarity to Improve I/O Performance**. [[PDF](https://www.usenix.org/legacy/events/fast10/tech/full_papers/koller.pdf)] [[Slides](https://www.usenix.org/legacy/events/fast10/tech/slides/koller.pdf)]

[2011 ATC] **Building a High-performance Deduplication System**. [[PDF](https://www.usenix.org/events/atc11/tech/final_files/GuoEfstathopoulos.pdf)]

### Security

[1993 CCS] CFS: **A Cryptographic File System for Unix**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/168588.168590)]

[1999 SOSP] SFS: **Separating key management from file system security**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/319151.319160)]

[2000 OSDI] **Fast and secure distributed read-only file system**. [[PDF](https://www.usenix.org/legacy/events/osdi2000/full_papers/fu/fu.pdf)]

[2008 StorageSS] **Tahoe – The Least-Authority Filesystem**. [[PDF](https://tahoe-lafs.org/~trac/lafs.pdf)] [[Codes](https://github.com/tahoe-lafs/tahoe-lafs)]

## Surveys

[1989] **A Survey of Distributed File Systems**. [[PDF](https://www.cs.cmu.edu/~satya/docdir/satya89survey.pdf)]

[1990] **Distributed File Systems: Concepts and Examples**. [[PDF](https://www.isical.ac.in/~ansuman/dist_sys/DFSPaper.pdf)]

[2005 ATC] **Analysis and Evolution of Journaling File Systems**. [[PDF](https://www.usenix.org/legacy/events/usenix05/tech/general/full_papers/prabhakaran/prabhakaran.pdf)]

[2008 NCM] **A Taxonomy and Survey on Distributed File Systems**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=4623994)]

[2015] **Analysis of Six Distributed File Systems**. [[PDF](https://hal.inria.fr/hal-00789086/file/a_survey_of_dfs.pdf)]

[2016 ICCCA] **Evolution and Analysis of Distributed File Systems in Cloud Storage: Analytical Survey**. [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7813828)]

[2016 PIEEE] **A Comprehensive Study of the Past, Present, and Future of Data Deduplication**. [[PDF](https://csyhua.github.io/csyhua/hua-PIEEE.pdf)]

[2018 CSUR] **Scalable Metadata Management Techniques for Ultra-Large Distributed Storage Systems – A Systematic Review**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3212686)]

[2020 JCST] **Ad Hoc File Systems for High-Performance Computing**. [[PDF](https://link.springer.com/content/pdf/10.1007/s11390-020-9801-1.pdf)]

[2022 TOS] **Survey of Distributed File System Design Choices**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/3465405)]

[2022 CCF-THPC] **A survey on AI for storage**. [[PDF](https://link.springer.com/content/pdf/10.1007/s42514-022-00101-3.pdf)]

[2022 TPDS] **The State of the Art of Metadata Managements in Large-Scale Distributed File Systems — Scalability, Performance and Availability**. [[PDF](https://daihao42.github.io/assets/pdf/tpds.pdf)]

[2022 TPDS] **A Survey of Storage Systems in the RDMA Era**. [[PDF](http://madsys.cs.tsinghua.edu.cn/publications/TPDS2022-ma.pdf)]

[2024 JCRD] **From BERT to ChatGPT: Challenges and Technical Development of Storage Systems for Large Model Training**. [[PDF](http://dx.doi.org/10.7544/issn1000-1239.202330554)]

## Analysis

[2000 ATC] **A Comparison of File System Workloads**. [[PDF](https://www.usenix.org/legacy/publications/library/proceedings/usenix2000/general/full_papers/roselli/roselli.pdf)]

[2007 FAST] **A Five-Year Study of File-System Metadata**. [[PDF](https://www.usenix.org/legacy/events/fast07/tech/full_papers/agrawal/agrawal.pdf)]

[2008 TOS] **A Nine Year Study of File System and Storage Benchmarking**. [[PDF](https://dl.acm.org/doi/pdf/10.1145/1367829.1367831)]

[2011 HotOS] **Benchmarking File System Benchmarking: It *IS* Rocket Science**. [[PDF](https://www.usenix.org/legacy/events/hotos11/tech/final_files/Tarasov.pdf)]

[2011 FAST] **A Study of Practical Deduplication**. [[PDF](https://www.usenix.org/legacy/events/fast11/tech/full_papers/Meyer.pdf)] [[Slides](https://www.usenix.org/legacy/events/fast11/tech/slides/meyer.pdf)]

[2012 SC] **A Study on Data Deduplication in HPC Storage Systems**. [[PDF](https://ieeexplore.ieee.org/abstract/document/6468447)]

[2013 FAST] **A Study of Linux File System Evolution**. [[PDF](https://www.usenix.org/system/files/conference/fast13/fast13-final75_0.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/lu_fast13_slides.pdf)]

## Object Storage

[2003 MSST] **Towards an Object Store**. [[PDF](https://msstconference.org/MSST-history/2003/papers/24-Azagury-Towards.pdf)] [[Slides](https://msstconference.org/MSST-history/2003/presentations/C07-Azagury.pdf)]

[2004 MSST] **OBFS: A File System for Object-based Storage Devices**. [[PDF](https://msstconference.org/MSST-history/2004/Papers/33-Wang-a.pdf)] [[Slides](https://msstconference.org/MSST-history/2004/Presentations/33r1.pdf)]

[2010 OSDI] **Finding a needle in Haystack: Facebook’s photo storage**. [[PDF](https://www.usenix.org/legacy/event/osdi10/tech/full_papers/Beaver.pdf)] [[Slides](https://www.usenix.org/legacy/events/osdi10/tech/slides/beaver.pdf)]

[2020 SCFA] **DAOS: A Scale-Out High Performance Storage Stack for Storage Class Memory**. [[PDF](https://www.researchgate.net/publication/341844608_DAOS_A_Scale-Out_High_Performance_Storage_Stack_for_Storage_Class_Memory)]

## New Hardware

[2017 FAST] **LightNVM: The Linux Open-Channel SSD Subsystem**. [[PDF](https://www.usenix.org/system/files/conference/fast17/fast17-bjorling.pdf)] [[Slides](https://www.usenix.org/sites/default/files/conference/protected-files/fast17_slides_bjorling.pdf)]

[2021 ATC] **ZNS: Avoiding the Block Interface Tax for Flash-based SSDs**. [[PDF](https://www.usenix.org/system/files/atc21-bjorling.pdf)] [[Slides](https://www.usenix.org/system/files/atc21_slides_bjorling.pdf)]

[2021 OSDI] **ZNS+: Advanced Zoned Namespace Interface for Supporting In-Storage Zone Compaction**. [[PDF](https://www.usenix.org/system/files/osdi21-han.pdf)] [[Slides](https://www.usenix.org/system/files/osdi21_slides_shin.pdf)]
