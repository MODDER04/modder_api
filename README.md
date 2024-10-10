# API Documentation

## Base URL
The url will be sent when you buy a key from @modder04
---

### 1. Create Call

Initiates a new call

- **Endpoint**: `/create_call`
- **Method**: `POST`
- **Description**: Creates a new call to the specified destination.
- **Note**: Don't add `+` before the number and the spoof
#### Request:
```json
{
"number": "string",
"spoof": "string",
"callback_url": "string",
"api_key":"string",
}
```
#### Response:
```json
{
    "call_uuid": "26444296-489f-42e0-8b47-d3fa172dd946",
    "message": "Call created successfully"
}
```
### 2. Play Audio
Plays an text during a call.
- **Endpoint**: `/play_audio`
- **Method**: `POST`
- **Description**: Plays the provided text in an active call session.
- **Voices**: [Voice list](https://docs.aws.amazon.com/polly/latest/dg/neural-voices.html)
#### Request:
```json
{
"uuid": "string",
"text": "string",
"voice" : "string",
}
```
### 3. Gather DTMF Input

Gathers DTMF (Dual-tone multi-frequency) input during a call.

- **Endpoint**: `/gather_dtmf`
- **Method**: `POST`
- **Description**: Collects DTMF input from the user during an active call.
- **Voices**: [Voice list](https://docs.aws.amazon.com/polly/latest/dg/neural-voices.html)

#### Request:
```json
{
"digits" : int,
"uuid": "string",
"text": "string",
"voice" : "string",
}
```
### 4. End Call

Ends an ongoing call.

- **Endpoint**: `/end_call`
- **Method**: `POST`
- **Description**: Terminates an active call session.

#### Request:
```json
{
  "uuid": "string"
}
```
