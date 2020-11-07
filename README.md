# Convergent


Convergent is a practice project idea.

I want to build a little platform for distributed sequential computing. 

What's the use case? I have no clue.

Premise
=======

The idea is to connect machines together as 'nodes' so they can compute a task together. 

Each 'node' will have a running service that reveals it to the local network as an available node.
When it detects the presence of convergent nodes, it will request to attach itself to the group.

If no convergent nodes are detected on the network, it will start its own 'convergence'.

Then, the idea is to be able to do some computation on the convergence. This will 100% just be a predetermined task first
and not a generalized application, because unless I see an easy way to do that while I'm writing this, I'm not that good
at writing code yet.

Implementation
==============

This will be on linux.

I'll probably use systemd services for node discovery and whatnot. 

I'm going to write it in C first, but might port it to either python, go, or rust as a way to learn or practice those languages.

Caveats
=======

I am well aware there are other projects that do this kind of thing, and do it way, way better. This is strictly a learning exercise.
