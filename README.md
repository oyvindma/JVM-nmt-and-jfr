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

## JFR
Where JFR should store data captured during profiling. The files stored can be concatenated by using "JFR.dump" while the process is running. If your process dies, they can be concatenated afterwards.
jcmd <<PID>> JFR.configure repositorypath=./jfr-recordings

Start JFR:
jcmd <<PID>> JFR.start settings=profile disk=true filename=<<where you want result when doing jcmd JFR.dump>>.jfr maxsize=500M dumponexit=true name=partProfilering

On Mac: Try the Azul zulu-mission-control if you have trouble installing/running Mission Control bundled with AdoptOpenJDK or OpenJDK https://www.azul.com/products/zulu-mission-control/
