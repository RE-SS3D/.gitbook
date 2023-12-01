# Applying attributes on all network related methods.

Whenever someone add a script implementing NetworkBehaviour, they have access to the following attributes, indicating if a given method should be server only, client only, or both :

* \[Server] for server only code.
* \[Client] for client only code.
* \[ServerOrClient] for both.

Make sure no methods goes without an attribute in a script inheriting NetworkBehaviour. The goal is to increase readability and to generate warnings or exceptions when clients or server are attempting to call something they should not.

Methods with \[ServerOrClient] attributes should stay uncommon, they make debugging harder. If possible, try to refactor the code to avoid them.
