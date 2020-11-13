# Managed File Transfer - Config SAPI

The system API is used for configuring entries leveraged by MFT Agents to process files.

Currently, only an SFTP agent has been configured: https://github.com/mikeacjones/mft-sftp-agent

This System API should be setup first as agents are dependent.

# Setup
1. Spin up a MongoDB in SE Platform
2. Pick an encryption key
3. Using the Blowfish algroithm and all other defaults, encrypt the username/password/database name. I suggest using this UI to handle your encryption: https://secure-properties-api.us-e1.cloudhub.io/
4. Update `Secure_Properties_Config` in `global.xml` with your encryption key.
5. Update `src/main/resources/mongodb.secure.yaml` with your encrypted information. The pattern should follow `![ENCRYPTED_STRING]`
6. The collections will be automatically created in the database when you first make a `POST`.
