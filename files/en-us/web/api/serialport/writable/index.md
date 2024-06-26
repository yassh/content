---
title: "SerialPort: writable property"
short-title: writable
slug: Web/API/SerialPort/writable
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.SerialPort.writable
---

{{SecureContext_Header}}{{APIRef("Web Serial API")}}{{SeeCompatTable}}{{AvailableInWorkers("window_and_dedicated")}}

The **`writable`** read-only property of the {{domxref("SerialPort")}} interface returns a {{domxref("WritableStream")}} for sending data to the device connected to the port. Chunks written to this stream must be instances of {{jsxref("ArrayBuffer")}}, {{jsxref("TypedArray")}}, or {{jsxref("DataView")}}. This property is non-null as long as the port is open and has not encountered a fatal error.

## Value

A {{domxref("WritableStream")}}

## Examples

The following example shows how to write a string to a port. A {{domxref("TextEncoder")}} converts the string to a `Uint8Array` before transmission.

```js
const encoder = new TextEncoder();
const writer = port.writable.getWriter();
await writer.write(encoder.encode("PING"));
writer.releaseLock();
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
