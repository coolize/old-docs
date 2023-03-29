---
id: managecloudcred
title: Managing Cloud Credentials
sidebar_label: Managing Cloud Credentials
---
## Connecting Public Cloud Credential to Lyrid Platform
Before you can use Public Cloud in Lyrid Platform , you also need to link the Cloud credential (AWS or GCP) into the account.

### Adding AWS credential
To add AWS Secret Key and Access Key, run the following command:
```bash
lc cloud add --framework "AWS" --key "<AWSKey>" --secret "<AWSSecret>"
```

### Adding GCP credential
To add the GCP JSON file, run the following command
```bash
lc cloud add --framework "GCP" --json <json-file-location>
```

:::note
Currently only one cloud credential per cloud framework per account is possible, adding another cloud account
credential of the same framework will override the credential that is saved in the system.
:::

### Listing all credentials
To list credential that is in the system:
```bash
lc cloud list
```

### Removing a credential
To remove credential that is in the system:
```bash
lc cloud delete –id <credential-id>
```

:::note
Use [Cloud Credential List](managecloudcred#listing-all-credentials) to get the ID of the credential to be deleted.
:::
