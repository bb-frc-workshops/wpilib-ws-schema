# wpilib-ws-schema
Schema for the WPILib WebSocket extension

## General Structure
The WPILib HALSim Extension acts as a WebSocket client and communicates with an endpoint that runs a WebSocket server.

Messages are exchanged via JSON objects following the structure below:

```json
{
    type: <string>
    payload: <object>
}
```

## Digital Messages
This section covers messages that deal with digital input and output

### Digital Configuration
This message configures the direction of a specified digital channel

#### Direction
Robot Code --> Endpoint

#### Message Structure
```json
{
    type: "digital-configure",
    payload: {
        channel: <number>,
        isInput: <boolean>
    }
}
```

### Digital Output
This message sets the output value of a specified digital output channel.

#### Direction
Robot Code --> Endpoint

#### Message Structure
```json
{
    type: "digital-out",
    payload: {
        channel: <number>,
        value: <boolean>
    }
}
```

### Digital Input
This message advertises a digital input channel value.

#### Direction
Endpoint --> Robot Code

#### Message Structure
```json
{
    type: "digital-in",
    payload: {
        channel: <number>,
        value: <boolean>
    }
}
```

## Analog Messages
This section covers messages that deal with analog input and output

### Analog Output
This message sets the output value of an analog output channel

#### Direction
Robot Code --> Endpoint

#### Message Structure
```json
{
    type: "analog-out",
    payload: {
        channel: <number>,
        voltage: <number>
    }
}
```

### Analog Input
This message advertises an analog input channel value

#### Direction
Endpoint --> Robot Code

#### Message Structure
```json
{
    type: "analog-in",
    payload: {
        channel: <number>,
        voltage: <number>
    }
}
```

## PWM Messages
This section covers messages that deal with PWM output

### Set PWM Value
This message sets the PWM output value. The value is within the range [-1.0, 1.0]. Note that WPILib supports setting `speed` and `position` (which lies in the range [-1.0, 1.0]), and a `raw` value (which lies in the range [0, 255]). Each of these calls will get converted into the range [-1.0, 1.0].

#### Direction
Robot Code --> Endpoint

#### Message Structure
```json
{
    type: "pwm",
    payload: {
        channel: <number>,
        value: <number>
    }
}
```

## Encoder Messages
This section covers messages that deal with encoders.

TODO: We need some way to identify the encoders
Seems like we can just assign an index from 0 to numEncoders

