---
slug: /cloud-providers/oci
title: Oracle Cloud Infrastructure (OCI)
sidebar_label: Oracle Cloud Infrastructure (OCI)
---

# Oracle Cloud Infrastructure (OCI)

## Supported resources
- Compute instances
- Identity policies
- Autonomous databases
- Functions
- Object storage
- Storage block volumes

## Local Komiser CLI (Single Account)

Komiser now supports multiple cloud accounts by default. Account configuration is done through the config.toml file, using the `CREDENTIALS_FILE` method.
We've also added 2 methods of persisting your account data.

### Data persistence
Choose between these two methods of persisting your OCI account data.
#### Postgres
**Add to config.toml file**
```
[postgres]
uri="postgres://postgres:komiser@localhost:5432/komiser?sslmode=disable"
```
#### SQLite

```
[sqlite]
  file = "komiser.db"
```

### Configuration file
In the configuration file you add the OCI account name, authentication method (CREDENTIALS_FILE) and a data persistence.

```
[[oci]]
name="sandbox-account"
source="CREDENTIALS_FILE"
path="Users/name/.oci/credentials"
profile="default"

[sqlite]
file="komiser.db
```

### Credentials file
Use an OCI user and an API key for authentication. In this case, you’ll need to put your tenancy OCID, user OCID, region name, the path to an API key, and the fingerprint of the API key.

> Download OCI CLI, find instructions [here](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/cliinstall.htm)

The easiest way is to let OCI walk you through the setup process by executing the following command:
```
$ oci setup config
 
Enter a location for your config [/home/opc/.oci/config]:
Enter a user OCID: ocid1.user.oc1..
Enter a tenancy OCID: ocid1.tenancy.oc1..
Enter a region by index or name(e.g. 1: ap-chiyoda-1, 2: ap-chuncheon-1, ...: eu-frankfurt-1
Do you want to generate a new API Signing RSA key pair? [Y/n]: Y
Enter a directory for your keys to be created [/home/opc/.oci]:
Enter a name for your key [oci_api_key]:
Enter a passphrase for your private key (empty for no passphrase):

```
Now, a config file and key pair have been created in your local `.oci` folder:

```
$ ls -la /home/opc/.oci/
-rw-------. 1 opc opc  302 Oct  1 11:13 config
-rw-------. 1 opc opc 1675 Oct  1 11:13 oci_api_key.pem
-rw-------. 1 opc opc  451 Oct  1 11:13 oci_api_key_public.pem


$ cat /home/opc/.oci/config
[DEFAULT]
user=ocid1.user.oc1..
fingerprint=e1:c8:bb:6a:71:c4:d6:28:90:7a:e3:23:0a:ed:d5:8d
key_file=/home/opc/.oci/oci_api_key.pem
tenancy=ocid1.tenancy.oc1..
region=eu-eu-paris-1
key_password=PASSWORD
```
Since Komiser looks for credentials in a file called `credentials`. Create a `credentials` file in the `.oci` folder and copy the contents of the `config` file to it.


### Contents of credentials file
```
[DEFAULT]
user=ocid1.user.oc1....
fingerprint=e8:99:10:45:54:c4:3d:c6:61:9e:42:e0:51:c0:76:cc
key_path="/Users/jakepage/.oci/oci_api_key.pem"
tenancy=ocid1.tenancy.oc1...
region=eu-paris-1
key_password=PASSWORD
```

> Make sure that the path added in the `config.toml` is correct to ensure that Komiser has access to the credentials file.  


### Run it!
That should be it. Try out the following command from your command prompt to start the server:

```
komiser start
```

If you point your browser to `http://localhost:3000`, you should be able to see your OCI resources.

## Local Komiser CLI (Multiple accounts)
Simply add more authentication blocks to the configuration file

```
[[oci]]
name="sandbox-account"
source="CREDENTIALS_FILE"
path="Users/name/.oci/credentials"
profile="DEFAULT"

[[oci]]
name="admin-account"
source="CREDENTIALS_FILE"
path="Users/name/.oci/credentials"
profile="ADMIN"

[[oci]]
name="production-account"
source="CREDENTIALS_FILE"
path="Users/name/.oci/credentials"
profile="PRODUCTION"

[sqlite]
file="komiser.db
```

### Contents of credentials file
```
[DEFAULT]
user=ocid1.user.oc1....
fingerprint=e8:99:10:45:54:c4:3d:c6:61:9e:42:e0:51:c0:76:cc
key_path="/Users/jakepage/.oci/oci_api_key.pem"
tenancy=ocid1.tenancy.oc1...
region=eu-paris-1
key_password=PASSWORD

[ADMIN]
user=ocid1.user.oc1....
fingerprint=e8:99:10:45:54:c4:3d:c6:61:9e:42:e0:51:c0:76:cc
key_path="/Users/jakepage/.oci/oci_api_key.pem"
tenancy=ocid1.tenancy.oc1...
region=eu-paris-1
key_password=PASSWORD

[PRODUCTION]
user=ocid1.user.oc1....
fingerprint=e8:99:10:45:54:c4:3d:c6:61:9e:42:e0:51:c0:76:cc
key_path="/Users/jakepage/.oci/oci_api_key.pem"
tenancy=ocid1.tenancy.oc1...
region=eu-paris-1
key_password=PASSWORD
```

### Run it!
That should be it. Try out the following command from your command prompt to start the server:

```
komiser start
```

If you point your browser to `http://localhost:3000`, you should be able to see your OCI resources.
