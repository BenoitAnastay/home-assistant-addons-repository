# Authelia

**Authelia** is an open-source authentication and authorization server providing two-factor authentication and single
sign-on (SSO) for your applications via a web portal.

## Installation

The installation of this add-on is pretty straightforward and not different in
comparison to installing any other Home Assistant add-on.

1. Click the Home Assistant My button below to open the add-on on your Home
   Assistant instance.

   [![Open this add-on in your Home Assistant instance.][addon-badge]][addon]

1. Click the "Install" button to install the add-on.
1. Start the "Authelia" add-on.
1. Check the logs of the "Authelia" add-on to see it in action.

## Configuration

**Note**: _Remember to restart the add-on when the configuration is changed._

```yaml
url: http://example.com
filename: "{created_year}/{correspondent}/{title}"
language: eng
language_packages: eng deu fra ita spa
default_superuser:
  username: admin
  email: admin@example.com
  password: changeme
timezone: Europe/Paris
polling_interval: 0
barcodes_enabled: false
barcodes_asn: false
consumer_recursive: false
consumer_subdirs_as_tags: false
ssl: false
certfile: fullchain.pem
keyfile: privkey.pem
```

### Option: `domain`

The FQDN of authelia

### Option: `smtp_*`

SMTP configuration for emails

### Configuration

Affter installation you'll be able to edit the configuration in `/addon_config/ca5234a0_authelia/`

[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=ca5234a0_authelia&repository_url=https%3A%2F%2Fgithub.com%2FBenoitAnastay%2Fhome-assistant-addons-repository
