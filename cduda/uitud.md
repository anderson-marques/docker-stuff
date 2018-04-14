# 2. Unit/Integration Testing Using Docker

## 2.1. Continuous Delivery Workflow

1. **Test** - We are here
2. Build
3. Release
4. Deploy

## 2.2. Test Workflow Using Docker

1. Create Test Environment
    - Base Image
    - Development Image
    - Docker Compose
2. Run Unit Tests
    - Single Container
3. Run Integration Tests
    - Single/Multi Container Complex Workflow

## 2.3. Docker Image Hierarchy 

1. Create a _**Base Image**_ for each application (Ops Team)
    - Establish the minimum Runtime Environment
    - Application Dependencies
    - System Configuration
    - Default Settings

2. Create a _**Development Image**_ child of the _**Base Image**_ (DevOps Team)
    - Install Dev Dependencies
    - Install Test/Build Tools

3. Create a _**Release Image**_ child of the _**Base Image**_ (Dev Team)
    - Install Application
    - Application Configuration
    - Application Entrypoint

### Good Practices
1. Create the _**Base Image**_ using a **_Official Image_** from Docker Official Repositories
2. Create the **_Organizational Parent Images_** children of one **_Official Images_**

### Example:

```Docker
FROM ubuntu:trusty
MAINTAINER Anderson Marques <anderson.mo.carvalho@gmail.com>

# Prevent dpkg errors
ENV TERM=xterm-256color

# Set mirrors to the country nearest to me
RUN set -i "s/http:\/\/archive./http:\/\/br.archive./g" /etc/apt/sources.list

# Install Python runtime
RUN apt-get update && \
    apt-get install -y \
    -o APT::Install-Recommend=false \
    -o APT::Install-Suggests=false \
    python python-virtualenv

# Add entrypoint script
ADD scripts/entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
```

#
## [Goback..](./index.md)