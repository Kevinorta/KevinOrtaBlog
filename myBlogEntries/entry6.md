# mancala blog #6
### server modifications

---------------------------------------

## ports and disconnections:
I took other peoples examples and tried to impliment them into my own application.
Who thought it would be so hard to try to understand someone elses code. Even with 
a tutorial it was hard. I believe c9 is making this whole process more complicated
then it has to be. When starting up an app it connects to the port 8080. Since I am
trying to get the client and server to connect again I thought the server should run on
port 8080. Boy was I wrong. Now everything was running on port 8080 which I thought 
it should, but this was overwhelming the port and caused it to disconnect and sometimes
refuse connection if I had the server running. 

## another port:
The solution to this is to have a port that the server runs on but then the client
connect to this port. Even though it seems logical to have them all on the same port
so they can talk to eachother, they need their own port to be able to communicate.

## takeaways:
* Things are sometimes more complicated than they have to be
    *and you have to deal with it. Think through things in different ways even if 
they aren't the way you think it should work. The server running on a different doesn't 
seem like it should work like it does but thats the way it was made so I had to follow 
that.

#### sources:
http://blog.honeybadger.io/building-a-simple-websockets-server-from-scratch-in-ruby/
