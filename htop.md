*htop* 
---
Here are the different values that the s, stat and state output specifiers (header "STAT" or "S") will display to
describe the state of a process:

+ D Uninterruptible sleep (usually IO)
+ R Running or runnable (on run queue)
+ S Interruptible sleep (waiting for an event to complete)
+ T Stopped, either by a job control signal or because it is being traced. (原因ctrl +z,代表程序被挂住了)
+ W Paging (not valid since the 2.6.xx kernel)
+ X Dead (should never be seen)
+ Z Defunct ("zombie") process, terminated but not reaped by its parent.

详细的请见
[htop explained](https://peteris.rocks/blog/htop/#t-stopped-by-job-control-signal)
