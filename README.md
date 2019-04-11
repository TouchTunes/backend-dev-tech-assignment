# Backend Developer tech assignment

## Problem description

Imagine you are building a web application to remote control Jukebox settings. Depending on components (hardware modules) a jukebox has, it may or may not support a setting (a key-value pair). For example a jukebox with "LED panel" component supports `animation_type` setting or a jukebox which does not have a "money_receiver" component does not support `currency` setting. 

## The assignment

You need to create a REST API with a single GET endpoint which returns a paginated list of jukeboxes for a given setting id. It should support following parameters:
 - `settingId` - setting id (required)
 - `model` - filter by model name (optional)
 - `offset` - specifies at what index start the page (optional)
 - `limit` - specifies the page size (optional)

Create a production-ready implementation, as you see it.  
_Hint_: docs / error codes / tests / API docs

## Prerequisites

In order to do that you need to use following mocked APIs:

### Jukes API

Lists jukes with information about them:

**GET** `http://my-json-server.typicode.com/touchtunes/tech-assignment/jukes`:

```json
[{
  "id": "5ca94a8ac470d3e47cd4713c",
  "model": "fusion",
  "components": [{
    "name": "led_panel"
  }, {
    "name": "amplifier"
  }, {
    "name": "led_panel"
  }]
},
...
]
```
 
### Settings API

Lists all available settings a jukebox may have and required components jukebox should have in order to support this setting:

**GET** `http://my-json-server.typicode.com/touchtunes/tech-assignment/juke_settings`:

```json
{
  "juke_settings": [{
    "id": "e9869bbe-887f-4d0a-bb9d-b81eb55fbf0a",
    "requires": ["camera", "speaker", "pcb"]
  }, {
    "id": "db886f37-16e3-4a55-80e4-cfffc9e4e464",
    "requires": ["touchscreen", "money_pcb", "led_panel", "money_receiver"]
  },
  ...
  ]
}
```

**Note** that setting is considered to be supported if jukebox has _all_ required components.

## Submission

Submit your assignment using a public github / gitlab / bitbucket repository (please don't use "touchtunes" in repo name or description) or a zip archive.
