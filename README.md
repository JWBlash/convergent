# Convergent


Convergent is a practice project idea.

I want to build a little platform for distributed sequential computing. 

What's the use case? I have no clue.

Premise
=======

The idea is to connect machines together as 'nodes' so they can compute a task together. 

Each 'node' will have a kernel module that reveals it to the local network as an available node.
When it detects the presence of convergent nodes, it will request to attach itself to the group.

If no convergent nodes are detected on the network, it will start its own 'convergence'.

Then, the idea is to be able to do some computation on the convergence or cluster 

Implementation
==============

This will be on linux.

I'll probably use systemd services for node discovery and whatnot. 

Caveats
=======

I am well aware there are other projects that do this kind of thing, and that will do it better. This is strictly a learning exercise.
