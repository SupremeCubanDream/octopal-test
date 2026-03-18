Minimal JSON Schema

{  
  "$schema": "http://json-schema.org/draft-07/schema\#",  
  "title": "OctoPal State Schema",  
  "type": "object",  
  "required": \["version", "lastUpdated", "mode"\],  
  "properties": {  
    "version": {  
      "type": "string",  
      "pattern": "^0\\\\.\[0-9\]+$"  
    },  
    "lastUpdated": {  
      "type": "string",  
      "format": "date-time"  
    },  
    "mode": {  
      "enum": \["normal", "degraded", "doctor"\]  
    },  
    "lastTickType": {  
      "type": "string",  
      "enum": \["STARTUP", "FOREGROUND\_USER", "BACKGROUND\_MONITOR", "TRANSACTION", "RECOVERY"\]  
    },  
    "preemptionFlags": {  
      "type": "object",  
      "properties": {  
        "doctorModeActive": { "type": "boolean" },  
        "transactionInFlight": { "type": "boolean" },  
        "degradedModeActive": { "type": "boolean" }  
      }  
    }  
  },  
  "additionalProperties": true  
}  
