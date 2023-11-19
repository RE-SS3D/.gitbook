# Network Message

## Network Messages

Network messages are a way to transmit data without having to worry about object relationships, they are basically global events, which anyone can subscribe and listen to. And we can create structures to send whatever we want via the network.&#x20;

The downside of that is that it doesn’t support late joins, the client has to be connected in order to receive that, otherwise it would miss the message. We should only use them when we want to ask something for the server to do, without worrying about object relations.
