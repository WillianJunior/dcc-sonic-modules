# Why?
Simple way to configure environments for a distributed system. Maintains versioning. Easy to deploy as everything is just files.

# How to use?
This repo can be cloned in a NFS export. Client nodes can NFS mount the two main dirs in the propper places. These are:
 - modules: maintain the binary installation files. Should be mounted at /opt/modules in each client node. Actual modules are ignored on git, only the install scripts are here (ansible or just a single install?).
 - modulefiles: maintain the modulefiles... Should be mounted at /opt/modulefiles in each client node.

# Configurations
 - Mount should be read-only, over NFS with root-squashing, with fs-cache (fsc)
 - All nodes are the same (thus all binaries should be compatible)
