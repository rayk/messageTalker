# Message Talker

This package is resposible forming and sending messages to one or more services.

Messsages are required as services run in their own isolate having their own heap
and execution loop. The message talker component is resposible for getting a message
to the service.

There is not dependence on reply streams etc, it is assume that if you sending a
message via the talk you will already have a connection established to service.

The only dependence the Message Talker has is will the serviceRegistry which it
used to lookup ports for services.

The Talker itself does not execute on it own thread, it has been design to be
available for all modules.

The act of creating a new message causes it to be sent to it's destination.
