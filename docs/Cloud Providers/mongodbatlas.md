---
slug: /cloud-providers/mongodb-atlas
title: MongoDB Atlas
sidebar_label: MongoDB Atlas
---

# MongoDB Atlas

## Supported resources

- Clusters


## Local Komiser CLI (Single account)

Komiser now supports multiple cloud accounts by default. Account configuration is done through the `config.toml` file, just pass in your account `API Token`.

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

To enable Komiser collecting your MongoDB Atlas Clusters, you need to add following configuration to the `config.toml`:

```toml
[[mongodbatlas]]
  name="MyMongoDBAtlasAccount"
  organizationId="organizationId"
  publicApiKey="publicApiKey"
  privateApiKey="privateApiKey"


[sqlite]
  file="komiser.db
```

The `name` can be anything you want. You can use different names in the case you want to connect more than one MongoDB Atlas account. 

Find your `organizationId` by pressing on the gear icon next to your Organization name.

![](/img/mongodbatlas-orgid-1.png)

To generate `publicApiKey` and `privateApiKey` you have to be an **Organization Owner**. On the **Settings** page where you've copied the `organizationId`, select **Access Manager** from the sidebar navigation. Create the public/private key pair and paste it in the the respective fields from the above configuration. 

### Run it!
* That should be it. Try out the following from your command prompt to start the server:

```
komiser start 
```

* Point your browser to `http://localhost:3000`

## Local Komiser CLI (Multiple accounts)
Simply add more authentication blocks to the configuration file

```
[[mongodbatlas]]
  name="FirstAccount"
  organizationId="organizationId"
  publicApiKey="publicApiKey"
  privateApiKey="privateApiKey"

[[mongodbatlas]]
  name="SecondAccount"
  organizationId="organizationId"
  publicApiKey="publicApiKey"
  privateApiKey="privateApiKey"


[sqlite]
file="komiser.db
```
