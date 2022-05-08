### p2p_file_transfer


### To run the system you'll have to launch a number of peer process independently (preferably one process per terminal window)
### ech time you creeat a new peer process you'll have to provide a list of arguments such as IP, PORT ... and the list of initialy know peers

### here is a scenario that you can try 
### first we'll create 5 peers p0, p2, p3, p4, p5
### note that we are reading the input for know peer from a text file (optional) which you can edit and add 'done' at the end 
```console
foo@bar:~$ java Server s 127.0.0.99 9999 peer0 < n0
foo
```
