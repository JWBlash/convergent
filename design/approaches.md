## Goals

Convergence is just for learning. There are a lot of frameworks that do distributed computing
in beautiful ways, and this isn't meant to be one of them. 

I think it will be important to draw from scheduler designs. What I have in mind for this
kind of seems to be something like a macro-scheduler across a distributed network of machines.

### Design Principles

#### All nodes are equal

This means that any node should be able to initiate processes, and any other available nodes
should pick up that slack.

I think the best way to achieve this kind of thing is to use queues to manage process states.
Due to the sequential nature of this program.

#### Support N nodes

Who cares how many nodes are in a convergence? I don't.

#### Grow the convergence dynamically

We want new nodes that join to be able to jump right into the fun. It would be gross to
shut down a convergence and restart it every time a node wants to hop in.


## Different approaches

### A Service Based Approach                                                                                                                                                                                
Maybe there's not even reason to funk around with the scheduler. It is probably possible to just
save process state in user-space rather than kernel-space and have the process state visible across
nodes in the convergence. Or at least communicated, rather than visible.

Frankly I think this is the easier approach of the two.

This approach asks that I try to figure out what information from process state is necessary to share
across machines. I think it's like... all of the state?

Does a scheduler-based approach *not* need that requirement?

### A Scheduler-based Approach

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

### Comparisons


