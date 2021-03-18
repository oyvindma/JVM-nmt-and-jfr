# JVM-nmt-and-jfr
Useful resources for understanding native memory tracking and Java Flight Recorder

## Links
https://www.baeldung.com/native-memory-tracking-in-jvm
http://openjdk.java.net/groups/hotspot/docs/RuntimeOverview.html#VM%20Fatal%20Error%20Handling|outline
https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/memleaks001.html
https://www.baeldung.com/java-heap-dump-capture
https://www.baeldung.com/jvm-parameters
http://www.mastertheboss.com/other/java-stuff/solving-java-lang-outofmemoryerror-metaspace-error
https://medium.com/@chrishantha/using-java-flight-recorder-2367c01deacf
https://docs.oracle.com/javase/8/docs/technotes/guides/vm/nmt-8.html
https://docs.oracle.com/javase/8/docs/technotes/guides/vm/gctuning/considerations.html
https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/tooldescr007.html
https://blog.sokolenko.me/2014/11/javavm-options-production.html
https://www.ivankrizsan.se/2019/11/21/visualvm-and-jdk-mission-control-on-mac-os/
https://www.youtube.com/watch?v=9u6btGIw7AA
https://docs.oracle.com/javacomponents/jmc-5-5/jfr-command-reference/JFRCR.pdf
http://www.mastertheboss.com/other/java-stuff/solving-java-lang-outofmemoryerror-metaspace-error
https://wiki.openjdk.java.net/display/HotSpot/Metaspace
https://www.programmersought.com/article/1563524182/
https://developers.redhat.com/blog/2020/08/25/get-started-with-jdk-flight-recorder-in-openjdk-8u/
https://www.vogella.com/tutorials/JavaPerformance/article.html
https://neo4j.com/developer/kb/understanding-memory-consumption/
https://technology.blog.gov.uk/2015/12/11/using-jemalloc-to-get-to-the-bottom-of-a-memory-leak/
https://stackoverflow.com/questions/39684464/java-process-memory-usage-jcmd-vs-pmap
https://stackoverflow.com/questions/31173374/why-does-a-jvm-report-more-committed-memory-than-the-linux-process-resident-set


Direct memory:
https://stackoverflow.com/questions/20058489/is-there-a-way-to-measure-direct-memory-usage-in-java
https://dzone.com/articles/analyzing-tcp-socket-with-java-flight-recorder
https://web.archive.org/web/20160527214434/https://blogs.oracle.com/alanb/entry/monitoring_direct_buffers
https://stackoverflow.com/questions/15657837/what-is-mapped-buffer-pool-direct-buffer-pool-and-how-to-increase-their-size/15755696
https://gist.github.com/t3rmin4t0r/1a753ccdcfa8d111f07c


Questions to elaborate no:
Different types of off-heap memory (Metaspace, direct memory buffers++. How do they work and how to monitor?

## JFR
Where JFR should store data captured during profiling. The files stored can be concatenated by using "JFR.dump" while the process is running. If your process dies, they can be concatenated afterwards.
jcmd <<PID>> JFR.configure repositorypath=./jfr-recordings

Start JFR:
jcmd <<PID>> JFR.start settings=profile disk=true filename=<<where you want result when doing jcmd JFR.dump>>.jfr maxsize=500M dumponexit=true name=partProfilering
  
Assemble the files in the repository folder with jfr assemble <repository> <file>
<file> is the new file you want the result written to.

On Mac: Try the Azul zulu-mission-control if you have trouble installing/running Mission Control bundled with AdoptOpenJDK or OpenJDK https://www.azul.com/products/zulu-mission-control/
