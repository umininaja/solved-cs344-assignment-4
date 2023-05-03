Download Link: https://assignmentchef.com/product/solved-cs344-assignment-4
<br>
The goal of this lab is to understand some of the new and interesting features of modern file systems, and to evaluate their benefits quantitatively.

<h1>Quantitative comparison of filesystems</h1>

Several modern filesystems are being built and used today, e.g., ZFS, btrfs, ext4 etc. These modern filesystems offer several new features like data deduplication, compression, check summing, copyon write, optimized block allocations, and so on. Each of these features results in several benefits, in terms of lower disk usage, better reliability, better performance, and so on. In this lab, we will take two filesystems that differ in a feature, and understand the pros and cons of having that feature. Proceed to solve the lab as described below, and document your observations in your report.

<ol>

 <li>Pick two filesystems and a feature that they differ in. For example, ZFS has the feature of datadeduplication, while ext4 does not. Similarly, ext4 optimizes large file creation as compared to older Linux filesystems. You must pick two such filesystems for comparison. You can use two separate instances of the same filesystem also, with different configurations, for your comparison. Read about the filesystems to gain a good idea of how the feature is implemented. Describe the feature of interest in your report, and the two filesystems you have chosen for your evaluation. Briefly describe how the feature has been implemented (from reading the filesystem code or documentation). Before you proceed further, have installations of these filesystems on one or more machines, in order to run experiments on them. (Google to know about installing file systems)</li>

 <li>Now, quantify the benefit(s) of this new feature. To do this, you must setup a workload (use thetool mentioned at end of the assignment) that will help showcase this new feature, run experiments using the same workload on both the filesystems, pick some metrics to measure in both sets of experiments, and compare the values of the metrics. Your report must describe all of the above aspects in detail. A few sample ideas on how to quantify performance benefits are given below; you can pick one of them, or come up with something that’s not on this list as well:</li>

</ol>

<ul>

 <li>If you want to quantify the benefits of the data deduplication feature of ZFS, pick a workload that consists of writing similar files to disk. Measure the disk space occupied with ZFS and an older filesystem like ext3 (or with ZFS itself, but with data deduplication turned off). You should be able to see the lower consumption of disk space when deduplication is used.</li>

 <li>Some modern filesystems are optimized to easily create and manage large files. You should be able to observe better throughput for such operations.</li>

 <li>For filesystems that provide the compression feature, you should be able to observe lower disk space usage.</li>

 <li>For filesystems that provide copy-on-write features, you should be able to observe that copying files or making snapshots/backups will take significantly shorter time.</li>

 <li>Some filesystems that use improved data structures to store metadata should result in faster disk reads or writes, depending on what they are optimized for.</li>

</ul>

<ol start="3">

 <li>Finally, state and quantify any disadvantages of your feature of interest that you may have observed in your report. For example, while the deduplication feature leads to lower disk usage, it may result in significantly higher CPU consumption.</li>

</ol>

<h1>Submission and Grading</h1>

You must submit a zipped file; whose filename is the group number of your group. For example, G[1-41].zip. The file should contain the following:

<ul>

 <li>pdf should describe your comparison of file systems, as described above.</li>

 <li>Any scripts and code you have written to solve this lab, along with a readme file describing how torun your code.</li>

</ul>

Evaluation of this lab will be as follows.

<ul>

 <li>We will read through your report and evaluate your understanding of file systems.</li>

 <li>We will run your code and try to reproduce your results.</li>

</ul>

<h1>Workload Creation Tool</h1>

A tool named ‘vdbench’ is packed in the assignment zip file, which you have to use to create workloads for testing the file systems. This tool provides functionality for raw I/O testing as well as file-system testing, make sure to use the file-system testing. A manual is included with in the ‘vdbench’ directory, from where you can get to know about the tool. You are free to create your own workloads in the way you like it, but you should be able to explain the behaviour of different file systems through the output.

<strong>*</strong> You need to install jre in your systems to be able to use this tool.