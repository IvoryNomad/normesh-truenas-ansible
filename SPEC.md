# Normesh TrueNAS collection - requirements

## Core Operations

- Internal operations
  - connect to API
  - authenticate to API
- Dataset Management
  - Key operations:
    - Create/delete/clone/snapshot datasets
    - Set properties
    - Set quotas
    - Query status
  - Implementation: WebSocket API calls from control node
- Share Management
  - Required API endpoints: sharing/*
  - Key operations:
    - Configure SMB shares
    - Configure NFS exports
  - Implementation: WebSocket API calls from control node
- Device Operations
  - Certificates
  - Cloud backup
  - Configuration
  - Core (future)
  - Cronjob
  - Filesystem
    - ACLs
    - can perform chown/chgrp here!

## Supporting Operations

- File Management
  - Required capabilities:
    - Deploy configuration files
    - Manage permissions
  - Implementation: Existing ansible.builtin modules
    - ansible.builtin.copy
    - ansible.builtin.file [^1]
    - ansible.builtin.template

[^1]: Functionality appears to be present using Filesystem methods of WebSocket API. Will prefer API methods.
