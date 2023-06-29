# open.CONNECT Instance

## Configuration
There are several configuration options to make successful API calls or plc connections. 
1. Start by creating an `.env`-file. Refer to `.env-example` for the properties.
2. Create a config in configs-folder and specify the name of the file in `.env`.
3. If you are using the API create a `config.json` in sync-folder.

## Config file
The config file should look something like this.

```
{
    "devices": [
    {
        "connectionString": "xxx://xxx:xxx",
        "interval": 5000,
        "options": {
            //Your individual options
        },
        "enabled": true,
        "objectId": "1",
        "name": "",
        "extraOptions": {
            "host": "",
            "username": "",
            "password": "",
            "clientId": ""
        }
    }],
    "items": [
    {
        "objectId": "1",
        "DeviceID": { "objectId": "1" },
        "extraOptions": {
            "note": "",
            "persist": true,
            "charset": "UTF-8"
        },
        "source": { "tag": "" },
        "enabled": true,
        "unit": "",
        "address": "",
        "label": "",
        "onChange": false
    },
    ]
}
```

## Sync file
In order to map values and fields from one API to another you should specify a sync file. 

The mapper uses Apache velocity to get and replace template fields.

The sync file should look something like this.

```
{
    "from": {
        "to": {
            "type": {},
            "type": {},
            "type": {
                "xxx": { "value": "$source.id", "type": "string" }
            }
        }
    }
}
```
