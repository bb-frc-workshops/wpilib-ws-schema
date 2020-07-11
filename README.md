# wpilib-ws-schema
Schema for the WPILib WebSocket extension

## Schema
The schema is defined using the AsyncAPI style and is located in the `schema` folder.

### Markdown Output
The Markdown Output of what is on master can be found [here](https://github.com/bb-frc-workshops/wpilib-ws-schema/blob/master/md/asyncapi.md)

### HTML Output
The HTML Output of what is on master can be found [here](https://htmlpreview.github.io/?https://github.com/bb-frc-workshops/wpilib-ws-schema/blob/master/html/index.html)

## General Structure
The WPILib HALSim Extension acts as a WebSocket client and communicates with an endpoint that runs a WebSocket server.

Messages are exchanged via JSON objects following the structure below:

```
{
    "topic": <string>,
    "payload": <object>
}
```

The `topic` string will be the name of the channel (as defined in the AsyncAPI schema), and the payload is the object that is defined in the applicable message for that channel.

## TODO
- Need to handle encoders
- System messages? e.g. enable/disable, heartbeat, reset