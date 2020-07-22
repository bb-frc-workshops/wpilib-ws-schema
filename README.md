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

Messages are exchanged via JSON objects following the structure:

```
{
    "type": <string>,
    "device": <string>,
    "data": <object>
}
```

The `type` string will be the type of device (e.g. DIO, AnalogIn, PWM, etc) and `device` represents a device identifier (usually the channel number).

## Generating Documentation
To generate the documentation, run the following from the `schema` directory:

- HTML: `ag ./wpilib-ws.yaml @asyncapi/html-template -o ../html`
- Markdown: `ag ./wpilib-ws.yaml @asyncapi/markdown-template -o ../md`

## TODO
- System messages? e.g. enable/disable, heartbeat, reset
