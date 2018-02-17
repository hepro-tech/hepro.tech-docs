# Events

When an interaction with the device occurs it should send one of the following events to the the events endpoint. Events follow this structure:

|Event Object|||
|---|---|---|
|Field|Type|Description|
|type|`string`|the type of the event|
|payload|`any`|the event payload|

## System Events

### Proximity Event

This event represents when an individual approaches the device. The payload will include the distance the individual is from the device in meters.

```json
{
    "type" : "PROMXIMITY",
    "payload" : {
        "distance" : 7
    }
}
```

### Tampering Event

This event represents when an individual actually moves the device.

```json
{
    "type" : "TAMPERING",
    "payload" : { }
}
```

# Endpoints

## Arming System

```
POST /arm/
```

## Disarming System

```
POST /disarm/
```

## Getting the status of the system

```
GET /status/
```

```json
{
    "name" : "cookie-jar",
    "armed" : true,
}
```

## Broadcasting an event

```
POST /events/
```

This endpoint accepts an