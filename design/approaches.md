### Different approaches

## A Service Based Approach                                                                                                                                                                                
Maybe there's not even reason to funk around with the scheduler. It is probably possible to just
save process state in user-space rather than kernel-space and have the process state visible across
nodes in the convergence. Or at least communicated, rather than visible.

Frankly I think this is the easier approach of the two.

This approach asks that I try to figure out what information from process state is necessary to share
across machines. I think it's like... all of the state?

Does a scheduler-based approach *not* need that requirement?

## A Scheduler-based Approach

I'll need to investigate a bit more about how the linux scheduler works.

Perhaps there would be some kind of way to have a service running on the machine that,
when a process is started through that service, it would tag it and force the scheduler
to run it in a sequential machine alongside the other nodes in the convergence.

This way processes would be executed something like:  
 'converge /.process'.  
The "converge" command would talk to a systemd service that would tag the "./process" command
with something that the scheduler would pick up on. 

I think with this approach, I'd clearly need some kind of service running in the background anyways
to make sure that not ALL processes were run in the convergence. Because that would break everything.

## Comparisons

