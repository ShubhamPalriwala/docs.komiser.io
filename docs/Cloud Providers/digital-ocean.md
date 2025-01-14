---
slug: /cloud-providers/digital-ocean
title: Digital Ocean
sidebar_label: Digital Ocean
---

# Digital Ocean

## Supported resources
- Droplets 
- Firewalls
- LoadBalancers
- VPCs

## Local Komiser CLI (Single account)

Komiser now supports multiple cloud accounts by default. Account configuration is done through the `config.toml` file, just pass in your account `Personal access Token`.

We've also added 2 methods of persisting your account data.
### Postgres
#### Add to config.toml file
```
[postgres]
uri="postgres://postgres:komiser@localhost:5432/komiser?sslmode=disable"
```
### SQLite

```
[sqlite]
  file = "komiser.db"
```

### Configuring Credentials

Firstly create your DigitalOcean `personal access token` from the DigitalOcean console.

Click the `API` link in the main navigation, which takes you to the `Applications & API` page on the `Tokens/Keys` tab. In the Personal access tokens section, click the `Generate New Token` button.

Need help finding it? Head on over to the official DigitalOcean [documentation](https://docs.digitalocean.com/reference/api/create-personal-access-token/).

### Add your DigitalOcean personal access token to your configuration file

```
[[digitalocean]]
name="demo-account"
token="yourApiTokenHere"

[sqlite]
file="komiser.db
```
                                        

### Run it!
* That should be it. Try out the following from your command prompt to start the server:

```
komiser start 
```

* Point your browser to `http://localhost:3000`

## Local Komiser CLI (Multiple accounts)
Simply add more authentication blocks to the configuration file

```
[[digitalocean]]
name="demo-account"
token="yourApiTokenHere"

[[digitalocean]]
name="sandbox"
token="yourSandboxApiTokenHere"

[[digitalocean]]
name="production"
token="yourProductionApiTokenHere"

[sqlite]
file="komiser.db
```