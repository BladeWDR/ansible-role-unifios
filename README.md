# Unifi OS install Ansible role.

## Overview

Installs the new Unifi OS appliance on Debian or Ubuntu.

By default it will always install the latest release and force an upgrade.

I recommend setting the `unifi_os_version` variable to avoid unintentional upgrades.

## LetsEncrypt Certificates

Supports installing LetsEncrypt TLS certificates via Certbot and Cloudflare with a DNS-01 challenge.

You'll need to set the following variables:

- `unifi_os_domain` - the domain name where your Unifi OS server is reachable. This will be used on the common name of the certificate. The TLS part of the playbook will simply not run if this is not set.
- `certbot_cloudflare_api_key` - the API key from your Cloudflare account with permissions to edit Zone DNS. I _highly_ recommend keeping this in a secrets manager or Ansible Vault.
- `certbot_email` - used in the certbot command to create your ACME account.
