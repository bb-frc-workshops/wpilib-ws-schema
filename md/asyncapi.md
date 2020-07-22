# WPILib WebSocket Remote Endpoint API 1.0.0 documentation

API to route WPILib HAL calls over WebSockets.

## Table of Contents

* [Channels](#channels)




## Channels



<a name="channel-wpilibws"></a>

General channel for WPILib WebSocket messages

#### Channel Parameters




###  `publish` wpilibws



#### Message


Message envelope. Note that the &quot;data&quot; field contains a diff of the current state of a particular device. E.g. If only the &quot;value&quot; changes for a DIO device, then only the &quot;&lt;&gt;value&quot; field will be sent.



##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>type </td>
  <td>string</td>
  <td><p>Device Type (e.g. DIO/AO/AI/PWM/Encoder etc)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>device </td>
  <td>string</td>
  <td><p>Device Identifier (usually channel)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data </td>
  <td>oneOf</td>
  <td><p>Payload for the message. Note that not all fields for a particular message will get sent. Only the diff of the current state of the particular device will be sent.</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt; </td>
  <td>object</td>
  <td><p>DIO Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this DIO channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;&gt;value </td>
  <td>boolean</td>
  <td><p>Current value of this DIO channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;pulse_length </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;input </td>
  <td>boolean</td>
  <td><p>Whether or not this DIO channel has been initialized as an input</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt; </td>
  <td>object</td>
  <td><p>Analog In Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this Analog In channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&lt;avg_bits </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&lt;oversample_bits </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&gt;voltage </td>
  <td>number</td>
  <td><p>The current input voltage of this Analog In channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum </td>
  <td>object</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not the accumulator for this Analog In channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&gt;value </td>
  <td>number</td>
  <td><p>Current accumulator value</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&gt;count </td>
  <td>number</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&lt;center </td>
  <td>number</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&lt;deadband </td>
  <td>number</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;3&gt; </td>
  <td>object</td>
  <td><p>Analog Out Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;3&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this Analog Out channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;3&gt;.&lt;voltage </td>
  <td>number</td>
  <td><p>Current output voltage of this Analog Out channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt; </td>
  <td>object</td>
  <td><p>DriverStation Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;enabled </td>
  <td>boolean</td>
  <td><p>Whether or not the driver station is enabled</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;autonomous </td>
  <td>boolean</td>
  <td><p>Whether or not to go into autonomous mode (when enabled)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;test </td>
  <td>boolean</td>
  <td><p>Whether or not to go into test mode (when enabled)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;estop </td>
  <td>boolean</td>
  <td><p>Whether or not the robot has been emergency stopped</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;fms </td>
  <td>boolean</td>
  <td><p>Whether or not the driver station is connected to FMS</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;ds </td>
  <td>boolean</td>
  <td><p>Whether or not the Driver Station is connected to the robot</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&lt;match_time </td>
  <td>number</td>
  <td><p>Current elapsed match time</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;station </td>
  <td>string</td>
  <td><p>Driver Station Position identifier</p>
</td>
  <td><code>red1</code>, <code>red2</code>, <code>red3</code>, <code>blue1</code>, <code>blue2</code>, <code>blue3</code></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks </td>
  <td>array(object)</td>
  <td><p>Information about all joysticks connected to the DS</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks.&gt;buttons </td>
  <td>array(boolean)</td>
  <td><p>State of all buttons on this joystick</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks.&gt;povs </td>
  <td>array(number)</td>
  <td><p>State of all POV switches on this joystick</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks.&gt;axes </td>
  <td>array(number)</td>
  <td><p>State of all axes on this joystick</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt; </td>
  <td>object</td>
  <td><p>Encoder Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this encoder channel is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&gt;count </td>
  <td>integer</td>
  <td><p>Current count of the encoder</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&gt;period </td>
  <td>number</td>
  <td><p>Current period of the encoder</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;reset </td>
  <td>boolean</td>
  <td><p>Whether or not this encoder should be reset</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;reverse_direction </td>
  <td>boolean</td>
  <td><p>Whether or not this encoder should reverse its counting direction</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;samples_to_avg </td>
  <td>integer</td>
  <td><p>Number of samples to average over</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt; </td>
  <td>object</td>
  <td><p>PWM Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this PWM channel is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;speed </td>
  <td>number</td>
  <td><p>Speed value of this PWM channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;position </td>
  <td>number</td>
  <td><p>Position value of this PWM channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;raw </td>
  <td>integer</td>
  <td><p>Raw value of this PWM channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;period_scale </td>
  <td>number</td>
  <td><p>Period scale factor</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;zero_latch </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt; </td>
  <td>object</td>
  <td><p>Relay data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;init_fwd </td>
  <td>boolean</td>
  <td><p>Whether or not the forward direction of this relay is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;init_rev </td>
  <td>boolean</td>
  <td><p>Whether or not the reverse direction of this relay is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;fwd </td>
  <td>boolean</td>
  <td><p>Whether or not the forward direction of this relay is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;rev </td>
  <td>boolean</td>
  <td><p>Whether or not the reverse direction of this relay is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt; </td>
  <td>object</td>
  <td><p>RoboRIO Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;fpga_button </td>
  <td>boolean</td>
  <td><p>Whether or not the FPGA button on the RoboRIO is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;vin_voltage </td>
  <td>number</td>
  <td><p>Input voltage</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;vin_current </td>
  <td>number</td>
  <td><p>Input Current</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_voltage </td>
  <td>number</td>
  <td><p>Voltage on the 6V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_current </td>
  <td>number</td>
  <td><p>Current on the 6V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_active </td>
  <td>boolean</td>
  <td><p>Whether or not the 6V rail is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_faults </td>
  <td>number</td>
  <td><p>Bitmask of faults on the 6V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_voltage </td>
  <td>number</td>
  <td><p>Voltage on the 5V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_current </td>
  <td>number</td>
  <td><p>Current on the 5V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_active </td>
  <td>boolean</td>
  <td><p>Whether or not the 5V rail is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_faults </td>
  <td>number</td>
  <td><p>Bitmask of faults on the 5V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_voltage </td>
  <td>number</td>
  <td><p>Voltage on the 3.3V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_current </td>
  <td>number</td>
  <td><p>Current on the 3.3V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_active </td>
  <td>boolean</td>
  <td><p>Whether or not the 3.3V rail is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_faults </td>
  <td>number</td>
  <td><p>Bitmask of faults on the 3.3V rail</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>



###### Examples of payload


```json
{
  "type": "PWM",
  "device": "1",
  "data": {
    "&lt;speed": 0.5
  }
}
```

```json
{
  "type": "DIO",
  "device": "3",
  "data": {
    "&lt;init": true
  }
}
```




###  `subscribe` wpilibws



#### Message


Message envelope. Note that the &quot;data&quot; field contains a diff of the current state of a particular device. E.g. If only the &quot;value&quot; changes for a DIO device, then only the &quot;&lt;&gt;value&quot; field will be sent.



##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>type </td>
  <td>string</td>
  <td><p>Device Type (e.g. DIO/AO/AI/PWM/Encoder etc)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>device </td>
  <td>string</td>
  <td><p>Device Identifier (usually channel)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data </td>
  <td>oneOf</td>
  <td><p>Payload for the message. Note that not all fields for a particular message will get sent. Only the diff of the current state of the particular device will be sent.</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt; </td>
  <td>object</td>
  <td><p>DIO Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this DIO channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;&gt;value </td>
  <td>boolean</td>
  <td><p>Current value of this DIO channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;pulse_length </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;1&gt;.&lt;input </td>
  <td>boolean</td>
  <td><p>Whether or not this DIO channel has been initialized as an input</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt; </td>
  <td>object</td>
  <td><p>Analog In Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this Analog In channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&lt;avg_bits </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&lt;oversample_bits </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.&gt;voltage </td>
  <td>number</td>
  <td><p>The current input voltage of this Analog In channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum </td>
  <td>object</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not the accumulator for this Analog In channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&gt;value </td>
  <td>number</td>
  <td><p>Current accumulator value</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&gt;count </td>
  <td>number</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&lt;center </td>
  <td>number</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;2&gt;.accum.&lt;deadband </td>
  <td>number</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;3&gt; </td>
  <td>object</td>
  <td><p>Analog Out Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;3&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this Analog Out channel has been initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;3&gt;.&lt;voltage </td>
  <td>number</td>
  <td><p>Current output voltage of this Analog Out channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt; </td>
  <td>object</td>
  <td><p>DriverStation Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;enabled </td>
  <td>boolean</td>
  <td><p>Whether or not the driver station is enabled</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;autonomous </td>
  <td>boolean</td>
  <td><p>Whether or not to go into autonomous mode (when enabled)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;test </td>
  <td>boolean</td>
  <td><p>Whether or not to go into test mode (when enabled)</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;estop </td>
  <td>boolean</td>
  <td><p>Whether or not the robot has been emergency stopped</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;fms </td>
  <td>boolean</td>
  <td><p>Whether or not the driver station is connected to FMS</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;ds </td>
  <td>boolean</td>
  <td><p>Whether or not the Driver Station is connected to the robot</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&lt;match_time </td>
  <td>number</td>
  <td><p>Current elapsed match time</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.&gt;station </td>
  <td>string</td>
  <td><p>Driver Station Position identifier</p>
</td>
  <td><code>red1</code>, <code>red2</code>, <code>red3</code>, <code>blue1</code>, <code>blue2</code>, <code>blue3</code></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks </td>
  <td>array(object)</td>
  <td><p>Information about all joysticks connected to the DS</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks.&gt;buttons </td>
  <td>array(boolean)</td>
  <td><p>State of all buttons on this joystick</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks.&gt;povs </td>
  <td>array(number)</td>
  <td><p>State of all POV switches on this joystick</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;4&gt;.joysticks.&gt;axes </td>
  <td>array(number)</td>
  <td><p>State of all axes on this joystick</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt; </td>
  <td>object</td>
  <td><p>Encoder Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this encoder channel is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&gt;count </td>
  <td>integer</td>
  <td><p>Current count of the encoder</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&gt;period </td>
  <td>number</td>
  <td><p>Current period of the encoder</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;reset </td>
  <td>boolean</td>
  <td><p>Whether or not this encoder should be reset</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;reverse_direction </td>
  <td>boolean</td>
  <td><p>Whether or not this encoder should reverse its counting direction</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;5&gt;.&lt;samples_to_avg </td>
  <td>integer</td>
  <td><p>Number of samples to average over</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt; </td>
  <td>object</td>
  <td><p>PWM Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;init </td>
  <td>boolean</td>
  <td><p>Whether or not this PWM channel is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;speed </td>
  <td>number</td>
  <td><p>Speed value of this PWM channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;position </td>
  <td>number</td>
  <td><p>Position value of this PWM channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;raw </td>
  <td>integer</td>
  <td><p>Raw value of this PWM channel</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;period_scale </td>
  <td>number</td>
  <td><p>Period scale factor</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;6&gt;.&lt;zero_latch </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt; </td>
  <td>object</td>
  <td><p>Relay data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;init_fwd </td>
  <td>boolean</td>
  <td><p>Whether or not the forward direction of this relay is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;init_rev </td>
  <td>boolean</td>
  <td><p>Whether or not the reverse direction of this relay is initialized</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;fwd </td>
  <td>boolean</td>
  <td><p>Whether or not the forward direction of this relay is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;7&gt;.&lt;rev </td>
  <td>boolean</td>
  <td><p>Whether or not the reverse direction of this relay is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt; </td>
  <td>object</td>
  <td><p>RoboRIO Data</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;fpga_button </td>
  <td>boolean</td>
  <td><p>Whether or not the FPGA button on the RoboRIO is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;vin_voltage </td>
  <td>number</td>
  <td><p>Input voltage</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;vin_current </td>
  <td>number</td>
  <td><p>Input Current</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_voltage </td>
  <td>number</td>
  <td><p>Voltage on the 6V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_current </td>
  <td>number</td>
  <td><p>Current on the 6V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_active </td>
  <td>boolean</td>
  <td><p>Whether or not the 6V rail is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;6v_faults </td>
  <td>number</td>
  <td><p>Bitmask of faults on the 6V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_voltage </td>
  <td>number</td>
  <td><p>Voltage on the 5V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_current </td>
  <td>number</td>
  <td><p>Current on the 5V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_active </td>
  <td>boolean</td>
  <td><p>Whether or not the 5V rail is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;5v_faults </td>
  <td>number</td>
  <td><p>Bitmask of faults on the 5V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_voltage </td>
  <td>number</td>
  <td><p>Voltage on the 3.3V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_current </td>
  <td>number</td>
  <td><p>Current on the 3.3V rail</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_active </td>
  <td>boolean</td>
  <td><p>Whether or not the 3.3V rail is active</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>data.&lt;8&gt;.&gt;3v3_faults </td>
  <td>number</td>
  <td><p>Bitmask of faults on the 3.3V rail</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>



###### Examples of payload


```json
{
  "type": "PWM",
  "device": "1",
  "data": {
    "&lt;speed": 0.5
  }
}
```

```json
{
  "type": "DIO",
  "device": "3",
  "data": {
    "&lt;init": true
  }
}
```





