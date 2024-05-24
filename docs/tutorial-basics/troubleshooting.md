---
sidebar_position: 3
---

# Troubleshooting

## CHATWITHTECH VSCode Extension Troubleshooting Guide

### Introduction

This guide is designed to help you resolve common issues that may arise during the installation and use of the CHATWITHTECH extension. Before you begin, ensure that you meet all the necessary requirements and configurations outlined below.

### Requirements

To run the CHATWITHTECH extension, your setup must meet the following requirements:

- VSCode Version: Your VSCode must be version 1.82.0 or higher.
- Node.js Version: Your Node.js must be version 18.0.0 or higher.

### Common Issues and Solutions

- Issue:
The CHATWITHTECH extension requires the use of port 54112 for localhost. If this port is not available, the extension will fail to run.

- Solution:
Ensure that port 54112 is free and not being used by any other application. You can check and free up this port by using the following commands:

For Windows:

```
netstat -aon | findstr :54112
taskkill /F /PID <PID>
```

For macOS and Linux:

```
lsof -i :54112
kill -9 <PID>
```
Replace `<PID>` with the actual Process ID using the port.


### 2. Using devcontainer

- Issue:
When using a devcontainer, port 54112 must be opened in the docker-compose configuration.

- Solution:
Ensure that your docker-compose.yml includes the following configuration to open port 54112:

```
services:
  your-service-name:
    ports:
      - "54112:54112"
```

### 3. VSCode Tunnel Incompatibility

- Issue:
The CHATWITHTECH extension is not compatible with VSCode Tunnel as it cannot run localhost under this setup.

- Solution:
Unfortunately, there is no workaround for using the CHATWITHTECH extension with VSCode Tunnel at this time. Ensure you are running VSCode in a local environment where localhost can be utilized.
