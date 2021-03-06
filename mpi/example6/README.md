Example 6: Collective Communication
===================================

This directory contains programs which use collective communication functions.

broadcast
---------

In this scenario, we would like to send some information from the
master process to all the other processes in the communicator.
This situation could arise if the master process had read some
parameter settings from file, or it had received some information
from one or more other processes and needs to coordinate the rest.

This program contrasts the time taken to achieve this using a
series of point-to-point communications against that used by one
collective _broadcast_ operation.

### Exercise

Run the program several times using different numbers of processors
and plot how the communication times scale over an increasing number
of processors in the communicator.


reduce_trapezoid
----------------

Another common scenario is one in which each process has computed a
value which we would like to combine in some way: add, multiply,
divide etc.

In this program we revisit the trapezoidal approach to numerical
integration.
Instead of sending the subtotals back to the master
processes as a sequence of point-to-point communications, we can
call a collective _reduce_ operation to achieve the same result,
but more efficiently.


scatter_gather
--------------

This last program demonstrates two more collective operations: _scatter_ and _gather_.

The call to scatter chunks up a send buffer on one of the
processes (called the _root_) and distributes those chunks to
all the other processes.

The call to gather takes chunks from all the other processes
and collates them into a single buffer on the root process,
i.e. it performs a mirror image of the scatter operation.

### Exercise

Our master send buffer contains a line from Macbeth, which
is 66 characters long.
Pay close attention to the contents of
the reconstituted buffer as you vary processor count.
