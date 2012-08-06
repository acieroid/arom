arom
====

# Introduction

AROM is a distributed parallel processing framework based on the DFG model for the execution and the definition of the jobs. 

# Architecture

There are 2 principal runtimes in AROM:

- The master node, which schedules and orchestrates the operators to be executed in parallel on the cluster
- The slave nodes which run the operator code.

It is built around the actor model and uses AKKA 1.0 as the basis of its stack. AROM is implemented in Scala.

# Compilation Instructions
The current code on the repository is fully fonctional and comprises the master and the slave runtimes. Once 
repository is cloned all is needed to run AROM is a Java virtual machine.

To compile on UNIX systems, simply run

$ ./sbt update
$ ./sbt compile

# Configuration

There are two configuration files that must be adjusted:
 * aromslave/src/main/resources/akka.conf 
   (contains all AROM settings along those for the Akka library)

# Starting the runtime

The slave runtime can be launched with the command:

$ ./sbt 'project naiadslave' run

At the moment, the slave runtime needs to be manually launched on each of the slave nodes in the cluster.

The master runtime is automatically launched once a job is defined and started (more job examples to come)