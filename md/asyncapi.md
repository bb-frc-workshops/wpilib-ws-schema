# WPILib WebSocket API 0.0.1 documentation

API for a WPILib based robot program to communciate with a remote endpoint over WebSockets

## Table of Contents

* [Channels](#channels)




## Channels



<a name="channel-digital/config"></a>

Configure a digital port

#### Channel Parameters




###  `publish` digital/config



#### Message




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
  <td>channel </td>
  <td>integer</td>
  <td><p>Channel number</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>isInput </td>
  <td>boolean</td>
  <td><p>Whether or not this port is an input</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "channel": 0,
  "isInput": true
}
```





<a name="channel-digital/out"></a>

Write to a digital port

#### Channel Parameters




###  `publish` digital/out



#### Message




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
  <td>channel </td>
  <td>integer</td>
  <td><p>Channel number</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>value </td>
  <td>boolean</td>
  <td><p>Value of the digital port</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "channel": 0,
  "value": true
}
```





<a name="channel-digital/in"></a>

Reading from a digital port

#### Channel Parameters




###  `subscribe` digital/in



#### Message




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
  <td>channel </td>
  <td>integer</td>
  <td><p>Channel number</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>value </td>
  <td>boolean</td>
  <td><p>Value of the digital port</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "channel": 0,
  "value": true
}
```





<a name="channel-analog/out"></a>

Write to an analog port

#### Channel Parameters




###  `publish` analog/out



#### Message




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
  <td>channel </td>
  <td>integer</td>
  <td><p>Channel number</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>voltage </td>
  <td>number</td>
  <td><p>Voltage of the analog port</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "channel": 0,
  "voltage": 0
}
```





<a name="channel-analog/in"></a>

Reading from an analog port

#### Channel Parameters




###  `subscribe` analog/in



#### Message




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
  <td>channel </td>
  <td>integer</td>
  <td><p>Channel number</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>voltage </td>
  <td>number</td>
  <td><p>Voltage of the analog port</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "channel": 0,
  "voltage": 0
}
```





<a name="channel-pwm/out"></a>

Write to a PWM port

#### Channel Parameters




###  `publish` pwm/out



#### Message




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
  <td>channel </td>
  <td>integer</td>
  <td><p>Channel number</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>value </td>
  <td>number</td>
  <td><p>Value of the PWM port [-1.0, 1.0]</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "channel": 0,
  "value": -1
}
```





