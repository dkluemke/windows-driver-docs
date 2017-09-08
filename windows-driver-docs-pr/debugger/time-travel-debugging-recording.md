---
title: Time Travel Debugging - Recording 
description: This section describes how to record time travel traces.
ms.author: windowsdriverdev
ms.date: 09/06/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

> [!NOTE]
> The information in this topic is preliminary. Updated information will be provided in a later release of the documentation. 
>

# ![Small logo on windbg preview](images/windbgx-preview-logo.png) Time Travel Debugging - Recording 

TBD TBD TBD 

This section describes how to record time travel traces.

To record a TTD trace, follow these steps.

1. In WinDbg Preview, select **File** > **Launch executable (advanced)** .

2. Fill in the path to the user mode executable that you wish to trace.

![Screen shot of WinDbg Preview showing start recording checkbox](images/ttd-start-recording.png)

> [!NOTE]
> The UI shown here is preliminary and will likley change. Updated information will be provided in a later release of the documentation. 
>

3. Click **OK** to launch the executable and start tracing. 

4. The recording dialog appears indicatting the trace is being recorded.

![TTD recording popup showing stop and debug as well as cancel options](images/ttd-recording-pop-up.png)

When the recording dialog box is being displayed you can:

- Stop tracing and debug your program. 
- Cancel the tracing. This option does 

As you can see the trace is loaded automatically. And this is the case if your program crashes as well.

When the application terminates the trace file will be closed and written out to disk.

Here is where you work to cause the activty that you wish to analyze to occur. You may open a problematic file or click on a specific button in the app to cause the event of interest to occur. 

Using breakpoints is a common apprroach to pause code execution at the event of interest.

Once complete, close your app or hit “Stop and debug” – This will kill your process.

5. When the trace file is closed, indexing will happen automatically as shown in the output below.

```
Time Travel Position: 6D1:0
ntdll!ZwTerminateProcess+0x12:
00007ffc`61f75922 0f05            syscall
||0:0:000> !index
Successfully created the index in 0ms.
```

Right after the trace is loaded, the indexing process begins. Indexing allows for complete and faster memory value look ups. This indexing process will take longer for larger trace files.

```
Time Travel Position: 10:0
ntdll!ZwTestAlert+0x14:
00007ffc`61f789d4 c3              ret
0:000> !index
Indexed 1/1 keyframes
Successfully created the index in 96ms.
```


# Notes - TBD

Command line version: 

1. Get process id of program that is running using tlist or taskmgr
Example command to get id of explorer: "tlist | findstr explorer"

2. Run ttt:
c:\Debuggers\ttt\TTTracer.exe -attach <pid>

3. Dialog window should appear. When you are done taking a trace, press "Exit app"

4. Share the content of the folder

FAQ
- Need to attach idna trace at launch?

Try:
c:\Debuggers\ttt\TTTracer.exe -onlaunch <process name> -out c:\data\test\bin\openwithtrace.run
 
When you are done, you can stop further tracing by running 
c:\Debuggers\ttt\TTTracer.exe –delete “all”



Help for Time Travel Debugging Extensions
  activitytree [all|<guid>] - Display the E2E activity tree.
  cmp <p1> <p2>     - Show the execution order relationship between two
                      positions.  The relationship is ?? if it cannot
                      determine the runtime ordering.
  events            - Bring up the .cmdtree window (currently unavailable in clients other than WinDBG).
  help              - Shows this help.
  index [-q]        - Commits a memory index to the trace file to extend
                      the range of addresses the debugger can resolve.
  position [-c|-s|  - Display current position info.  Use -c to specify
            -a]       only the current thread.  Use -s to specify the
                      trace start position.  Use -a to specify displaying
                      only active threads.
  pa <addr> [size]  - Get the value(s) in <addr>.  This may return multiple
                      values if the last reference to the <addr> occurred
                      in overlapping sequences in different threads.
  pr <addr> [size]  - Search for the previous read(s) in <addr>.
  pw <addr> [size]  - Search for the previous write(s) in <addr>.
  search <direction> <expr> - Search either backwards or forwards in the
                      trace until the expression evaluates to true.  See the
                      section on searching the trace file using the debugger
                      by going to http://idna and following the link to the
                      Search page in the Wiki pages.
  sn [count] <expr> - Short cut for !search +j <expr> with optional
                      iteration count.  Count can be a number in hex or
                      decimal format, or it can be the symbol '*' to
                      indicate that it should iterate to the end of the
                      trace.
  sp [count] <expr> - Short cut for !search -j <expr> with optional
                      iteration count.
  tt <position>     - Time Travel to a position in the trace or if the
                      position x is 0 to 100 it travels to approximately
                      x% of the way through the trace.
  ttpw              - Search previous write instruction in <addr>, and
                      perform a time travel to write position.
  replayexceptions [on|off]       - Control how exceptions are replayed:
                                      on = all software exceptions replay as recorded (slower)
                                     off = most software exceptions are replayed as C++ exceptions (default, fast)
                                    Note that all exceptions remain visible in the '!events' command,
                                    regardless of this setting
  replaydebugoutput [on|off]      - Control how debug output is replayed:
                                      on = all debug output will be shown as recorded (slower)
                                     off = no debug output will be shown (default, fast)
                                    Note that all debug output events remain visible in the '!events' command,
                                    regardless of this setting

Note: Input all address and position values in HEX format.  Size must be a
      a decimal value between 1 and 8.






> Additional Content Pending

---

## See Also

[Time Travel Debugging - Overview](time-travel-debugging-overview.md)

---


[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[debugger\debugger]:%20Debugging%20Using%20WinDbg%20%20RELEASE:%20%285/15/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



