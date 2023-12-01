# Server RPC

## Code that is called from the client to be run in the server, with the client information

Continuing the disgrace, there’s code that the client decides when to run and the server actually executes it, with the information the client gave it.

This is probably one of the most critical parts when we think about security, we sometimes we have to trust the client with what they are sending the server, so extra validation can be welcoming.

Anyways the attribute is **\[ServerRpc]** this one has another trick at its sleeve, we have to own the object that we are trying to call the method, this can however be completed ignored by using **\[ServerRpc(ignoreAuthority = true)]**.

To guarantee you got it right, the params of the call will use data from the client, and the logic will be executed with the server’s data.
