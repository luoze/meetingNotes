UCSD Wisconsin Meeting 01-July-2014
* Performance is again highly variable  Prism -> CHTC
* What is the performance to an intermediate point
   * bwctl -T iperf -t 20 -i 1 -fm -c ps.tacc.utexas.edu   (from ps-10g-prism.calit2.optiputer.net)
   [ 14]  0.0-20.0 sec  1585 MBytes   664 Mbits/sec  <-- This is not good. I2 WAN performance is still quite bad
   
   
Pat/Tom Todo:  Find intermediate test points to between San Diego and Wisconsin to figure out where 
performance fall off is located. 

Pat to chat with Eli Dart at ESNet for 

Phil was able to also run the job script that Alan put together for a simple data placement job
* Uses the parallel universe to create a server on node 0, client on node 1
* nc (netcat) listens on the server
* condor_chirp is used to put  the host and port into a Job Ad and then the client connects to that server:port to send /etc/hosts
* Small bug in the script kept two different users from running the same job.

Next for Nate/Alan.
* Regularly run a data placement job between Komatsu(Wisc)/Flashio(UCSD) every hour or two
* report the results in a comma (or tab) delimited file
* If possible, simplify the Condor config file to remove duplicates (e.g. multiple defines of the same variable)


No Meeting 7/8 (Phil on Travel)
Next meeting 7/15 at regular time.






