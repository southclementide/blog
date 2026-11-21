---
title: "Lab Nexus"
weight: 1
params:
  bookFlatSection: true
# bookToc: true
# bookBreadcrumbs: false
# bookPageLinks: false
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
# bookHref: ''
# bookIcon: ''
---

# Lab Nexus

## Setup

```yml {filename=compose.yml}
services:
  nexus:
    image: sonatype/nexus3:latest
    container_name: nexus
    restart: unless-stopped
    ports:
      - "8081:8081"
    environment:
      # Nexus Java heap tuning (2GB min, 2GB max; adjust as needed)
      - INSTALL4J_ADD_VM_PARAMS=-Xms2048m -Xmx2048m -XX:MaxDirectMemorySize=2048m
    volumes:
      - nexus_data:/nexus-data

volumes:
  nexus_data:
```

Retrieve the initial admin passwd:

```bash
docker exec nexus cat /nexus-data/admin.password
```
