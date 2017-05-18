# mancala blog #3
### let the learning begin

---------------------------------------

## more descisions:
I quickly learned that there are a lot of different ways to use websockets. This
ranges from the easy to use but functionally weaker JavaScript to Ruby with 
some more functionality to Node.JS with robust websockets and a lot more support.
I looked through each and decided to use Ruby to create websockets even though
not many people use it or provide examples of ruby websockets in use. I didn't go
with the more robust Node.JS because I looked over a few examples and realized it
would be too difficult to wrap my head around a new concept like websockets and 
a practically new language like Node.JS.

## websocket background:
Websockets is the answer to concerns about latency in client server connections.
Older techniques of having a client and server talk to each other such as long
polling and flash are not capable of long term connections with low latency. Thats
where websockets come in. They can be connected long term and are extremly low latency
especially with some other add ons(I will most likely not get into this). 

## server talk:
websockets requires a server connection. That means I will need to create a server
in the future. Before getting into the more complex side of websockets, I will 
just use echo servers. Echo servers are servers set up to test websocket connections
and functionality. They simply send back to the client what ever the client sent 
to it. Connecting to a websocket server is easy using Faye WebSocket for Ruby. 
```ruby
ws = Faye::WebSocket::Client.new('ws://ServerLink)
```
I ran into an issue that set me back using this though. I initially connected to
an echo server. When testing it out, the client kept refusing to connect. I had no
idea why that was the case. It worked when I tried it out at home but in school it
never did. One day it just clicked that I am using the non-secure websocket connection.
It was a quick fix. Instead of using ws:// for websockets I used wss:// which is
simply the secure connection of websockets similar to https://

## takeaways:
* pay close attention to everything
    * The smallest things can set you back a long time. Make sure you read everything
    closely just so you don't miss anything. This is what happened to me. I skimmed
over the part of the tutorial that taught me about the wss:// secure connection 
so I didn't get why my client refused to connect to the echo server. 