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



Followup: on 7/6/2014, Incoming from texas is OK (Trying to rule out problems with UCSD endpoint)
[root@ps-10g-prism ~]# bwctl -T iperf  -t 20 -i 1 -fm -s ps.tacc.utexas.edu
bwctl: Using tool: iperf
bwctl: 27 seconds until test results available

RECEIVER START
------------------------------------------------------------
Server listening on TCP port 5035
Binding to local address 67.58.50.75
TCP window size: 0.06 MByte (default)
------------------------------------------------------------
[ 15] local 67.58.50.75 port 5035 connected with 129.114.0.189 port 5035
[ ID] Interval       Transfer     Bandwidth
[ 15]  0.0- 1.0 sec   183 MBytes  1537 Mbits/sec
[ 15]  1.0- 2.0 sec   723 MBytes  6063 Mbits/sec
[ 15]  2.0- 3.0 sec   687 MBytes  5765 Mbits/sec
[ 15]  3.0- 4.0 sec   691 MBytes  5795 Mbits/sec
[ 15]  4.0- 5.0 sec   759 MBytes  6369 Mbits/sec
[ 15]  5.0- 6.0 sec   803 MBytes  6738 Mbits/sec
[ 15]  6.0- 7.0 sec   847 MBytes  7107 Mbits/sec
[ 15]  7.0- 8.0 sec   892 MBytes  7481 Mbits/sec
[ 15]  8.0- 9.0 sec   652 MBytes  5470 Mbits/sec
[ 15]  9.0-10.0 sec   555 MBytes  4657 Mbits/sec
[ 15] 10.0-11.0 sec   555 MBytes  4659 Mbits/sec
[ 15] 11.0-12.0 sec   600 MBytes  5030 Mbits/sec
[ 15] 12.0-13.0 sec   564 MBytes  4731 Mbits/sec
[ 15] 13.0-14.0 sec   340 MBytes  2855 Mbits/sec
[ 15] 14.0-15.0 sec   349 MBytes  2924 Mbits/sec
[ 15] 15.0-16.0 sec   371 MBytes  3108 Mbits/sec
[ 15] 16.0-17.0 sec   416 MBytes  3494 Mbits/sec
[ 15] 17.0-18.0 sec   475 MBytes  3982 Mbits/sec
[ 15] 18.0-19.0 sec   564 MBytes  4730 Mbits/sec
[ 15] 19.0-20.0 sec   667 MBytes  5592 Mbits/sec
[ 15]  0.0-20.1 sec  11736 MBytes  4907 Mbits/sec
[ 15] MSS size 8948 bytes (MTU 8988 bytes, unknown interface)

RECEIVER END
[root@ps-10g-prism ~]# ping ps.tacc.utexas.edu
PING ps.tacc.utexas.edu (129.114.0.189) 56(84) bytes of data.
64 bytes from ps.tacc.utexas.edu (129.114.0.189): icmp_seq=1 ttl=51 time=40.2 ms
64 bytes from ps.tacc.utexas.edu (129.114.0.189): icmp_seq=2 ttl=51 time=40.3 ms
64 bytes from ps.tacc.utexas.edu (129.114.0.189): icmp_seq=3 ttl=51 time=40.1 ms
^C




