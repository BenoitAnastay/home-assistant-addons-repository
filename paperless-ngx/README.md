# Paperless-ngx Home Assistant Addon
Paperless is an application that manages your personal documents. With the help of a document scanner, paperless transforms your wieldy physical document binders into a searchable archive and provides many utilities for finding and managing your documents.
### Paperless Version 2.1.3

## About

_Paperless is an application that manages your personal documents. With the help of a document scanner (see [Scanner recommendations](https://paperless-ngx.readthedocs.io/en/latest/scanners.html)), paperless transforms your wieldy physical document binders into a searchable archive and provides many utilities for finding and managing your documents._

![Dashboard screenshot](https://github.com/paperless-ngx/paperless-ngx/blob/b961df90a72f506f4a58c236fd3712cebb1523ff/docs/assets/screenshots/dashboard.png)

Read more in the project's [Readme](https://github.com/paperless-ngx/paperless-ngx)

## Installation

The installation of this add-on is pretty straightforward and not different in
comparison to installing any other Home Assistant add-on.

1. Click the Home Assistant My button below to open the add-on on your Home
   Assistant instance.

   [![Open this add-on in your Home Assistant instance.][addon-badge]][addon]

1. Click the "Install" button to install the add-on.
1. Start the "Paperless-ngx" add-on.
1. Check the logs of the "Paperless-ngx" add-on to see it in action.

## Documentation

The documentation for this addon can be found [here](DOCS.md)

## Integrate into Home Assistant

In Home Assistant Information from paperless can be accessed trought a REST-Sensor:

```
- platform: rest
  unique_id: 5dade7bc-ddb7-442e-bb17-0d379dbf01fb
  resource: paperless.server:port/api/documents/
  headers:
    Authorization: !secret paperless_auth_header
  params:
    query: "tag:inbox"
  value_template: "{{ value_json.count | int }}"
  name: "Paperless Inbox"
  icon: mdi:inbox
```

In your secrets file you'll have to specify:

```
paperless_auth_header: Token <django-token>
```

You can generate a token by clicking on `Settings -> Django Adminpanel -> Token` in your paperless instance.

[project-stage-shield]: https://img.shields.io/badge/project%20stage-production%20ready-brightgreen.svg
[release-shield]: https://img.shields.io/badge/version-v0.1.5-blue.svg
[release]: https://github.com/BenoitAnastay/paperless-home-assistant-addon/tree/v0.1.5