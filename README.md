# TaxiCluster-Go

TaxiClustering program written in go using concurrent DB-San algorithm.

Majority of code in map.go was provided by the University of Ottawa.
prodcons.go was entirely provided by university.

Lines 83 - 96 were written by Easton Smith, Student#: 300189637 (me)
So were the produce and consume functions, which are run concurrently as goroutines. 

The produce function loops through the points and stores them a channel as well as the i,j values from a loop in a different channel.
when the loop is finished send 'true' to the 'done' channel, which will then allow the code to progress past line 96.

The consume function pulls the values from the channels as they are added and runs them through the DB-scan algorithm provided. 
The values are also pulled from the ij channel in order to properly label each partition using the ij values to offset.