# How to analyse a .phd heap dump from an IBM JVM

If you have been handed a `.phd` file which is a dump of the heap of an `IBM Java virtual machine`, 
you can analyse it using the `Eclipse Memory Analyzer Tool (MAT)`, 
but you must install the `IBM Monitoring and Diagnostic Tools` first.

Download MAT from: https://www.eclipse.org/mat/downloads.php

I suggest the Standalone version.

Unzip it and run the `MemoryAnalyzer` executable inside the zip. Add an argument to control how much memory it gets e.g. to give it 4GB:

```bash
./MemoryAnalyzer -vmargs -Xmx4g
```

Once it’s started, go to Help -> Install new software.

Next to "Work with" paste in the URL for the `IBM Developer Toolkit` update site: 
http://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/runtimes/tools/dtfj/

Click Add...

Type in a name like `IBM Monitoring and Diagnostic Tools` and click OK.

In the list below, an item should appear called `IBM Monitoring and Diagnostic Tools`. 
Tick the box next to it, click Next, and follow the wizard to accept the license agreements and install the toolkit.

Restart `Eclipse` when prompted.

Choose File -> Open Heap Dump and choose your `.phd` file.
It should open in MAT and allow you to figure out who is using all that memory.