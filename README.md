### p2p_file_transfer


#### To run the system you'll have to launch a number of peer process independently (preferably one process per terminal window)
### ech time you creeat a new peer process you'll have to provide a list of arguments such as IP, PORT ... and the list of initialy know peers

#### here is a scenario that you can try 
#### first we'll create 5 peers p0, p2, p3, p4, p5
#### note that we are reading the input for know peer from a text file (optional) which you can edit and add 'done' at the end 
#### the argument after port number (peer0 for ex) represents the directory in which the peer stores its local files

#### first compile all java files 
```console
window-1
foo@bar:~$ javac *.java
```

open 5 different terminal windows to run the scenario described above
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
foo@bar:~$ java Server P5 127.0.0.99 9999 peer5 < n5
```

 then on a separate new window run **SyntaxAnalyser** to interact with the system 
 first connect to the public peer with the **connect_with** command then you can start using other like **ask_name**, **download**, ...
