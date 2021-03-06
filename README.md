### p2p_file_transfer


 To run the system you'll have to launch a number of peer processes independently (preferably one process per terminal window)
     ech time you creeat a new peer process you'll have to provide a list of arguments such as IP, PORT ... and the list of initialy know pee
     here is a scenario that you can try 
     first we'll create 5 peers p0, p2, p3, p4, p5
     note that we are reading the input for know peer from a text file (optional) which you can edit and add 'done' at the end 
     the argument after port number (peer0 for ex) represents the directory in which the peer stores its local files
    
#### first compile all java files.
```console
window-1
foo@bar:~$ javac *.java
```
Open 5 different terminal windows to run the scenario described above.

```console
window-1
foo@bar:~$ java Server P0 127.0.0.99 9999 peer0 < n0
```

```console
window-2
foo@bar:~$ java Server P2 127.0.0.2 2222 peer2 < n2
```
```console
window-3
foo@bar:~$ java Server P3 127.0.0.3 3333 peer3 < n3
```
```console
window-4
foo@bar:~$ java Server P4 127.0.0.4 4444 peer4 < n4
```
```console
window-5
foo@bar:~$ java Server P5 127.0.0.5 5555 peer5 < n5
```
The class server is just a class to initialize peer to listen to incoming requests and doesn't mean that the system is centralized through a server.


 Then on a separate new window run **SyntaxAnalyser** to interact with the system.
 First connect to the public peer with the **connect_with** command then you can start using other commands like **ask_name**, **download**, ...
 
 If everything goes well you should see this interface : 

```console
abdel@msi:~/projet_java$ java SyntaxAnalyser 

  ==> public peer to join the network : IP:127.0.0.99 PORT:9999  
  ==> type 'connect_with' <IP> <PORT>  
  ==> type 'help' to view all commands 

>>connect_with 127.0.0.99 9999
P1[127.0.0.1] connected to 127.0.0.99

>>download file-p0-00
Voila!! here is file-p0-00
receiving file ... 
	===== START OF FILE ======
JRZqTxjrvqSOOCiU9Km965gIpEyxV/tRfH9
	===== END OF FILE  =======

>>download file-p5-03

looking for file-p5-03 in 127.0.0.2
P1[127.0.0.1] connected to 127.0.0.2
looking for file-p5-03 in 127.0.0.3
P1[127.0.0.1] connected to 127.0.0.3
looking for file-p5-03 in 127.0.0.5
P1[127.0.0.1] connected to 127.0.0.5

Voila!! here is file-p5-03
receiving file ... 
	===== START OF FILE ======
r6W4QLOB1jxq3/EkNg41C2VrKjkp
	===== END OF FILE  =======

>>

```


To generate random directories with random files for additional peers (in case you want create another scenario) run **rand.sh** where arg1 arg2 are the number of dirs and the number of files per dir respectively.

```console
foo@bar:~$ bash rand.sh <arg1> <arg2>
```
