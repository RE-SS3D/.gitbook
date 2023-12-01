# ObserversRPC

## Code that is called from the server to be run on the client, with the information from the server

Usually here is where things get messy for some people, but for starters, the attribute is **\[ObserversRpc]**, RPC stands for **remote-procedure-call**, this one is called by the server, which means the server decides when to run it, and makes the client run it, with the information it wants.&#x20;

That information is only valid for params, as the logic inside the code is run by the client, everything there only exists for the client, excepts for the method parameters sent by the server.
