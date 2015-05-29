
Project NewCastle
=================
<br />


<br />


???

Visit [http://project-ncl.github.io/presentations/demo-v0.4/] (http://project-ncl.github.io/presentations/demo-v0.4/) to see slides in presentation mode. 

---

Agenda
======

### - Overview and motivation

### - Main components

### - Demo

### - Modularity and Extendibility

### - Project structure

### - Project structure - maven modules

### - How to build pnc and try it out

### - Open decissions

---

Overview and motivation
=======================
- Open source on github
    - [https://github.com/project-ncl/pnc](https://github.com/project-ncl/pnc)
- Analyze community projects
    - Track all maven dependencies
    - Compare which artifacts are already in the system
    - Track also non mvn requests
- Re-use artifacts from other project
- Do one build only

---

Main components
===============
![main components](./images/pnc-main-components.png)

- REST & WebSockets
- OAuth (KeyCloak server)

---

Demo
====
- How to configure a build
- Trigger the build
- View collected results

---

Modularity and Extendibility
============================
- External
    - REST
    - Swagger (pnc-web/apidocs/)
    - BPM
- Internal
    - Build environment SPI
    - Repository manager SPI
    - Build driver SPI

---

Project structure - components
==============================
- PNC orchestrator (ear deployment)
- Aprox - maven repository manager
- Docker host / OpenShift - environment
    - Builder images with installed build agent and other tools like mvn, git
- JBPM server - build is a task in the process
- KeyCloak server 

[PNC structure diagram](./images/pnc-detailed-diagram.png)

---

Project structure - maven modules
=================================
- UI (AngularJS)
- REST / Swagger api doc
- Datastore
- Build-coordinator
- repository manager driver SPI
    - *Aprox repository driver*, Nodejs registry, Docker registry
- Environment driver SPI
    - *Docer host / swarm env driver*, OpenShift, local
- Build driver SPI
    - *Jenkins build driver*, pnc build agent driver, local?
- Auth
- Integration tests

---

How to build pnc and try it out
===============================
- Clone github repo http://github.com/project-ncl/pnc/
- mvn clean install
    - produces an ear package to deploy to EAP
- Set-up remote services
    - Docker host with required images
    - Aprox repository manager
- Configure settings
    - or use env variables to "fill" the default file
- Remote tests disabled by default - see README
    - Currently you need all remote components up and running
    - Settings vs. env variables
- Authentication is disabled by default
    - requires KeyCloak server

---

Open discussions
================
- pom-manipulation and versioning
- OpenShift deployment
- Persistent coordinator state
- JBPM and OAuth
- JBPM and UI integration
- New light-weight Build Agent replacing Jenkins
- Brew connection and reliable storage


---

Thanks
======

### PNC
- [https://github.com/project-ncl/pnc](https://github.com/project-ncl/pnc)

### AProx
- [https://github.com/Commonjava/aprox](https://github.com/Commonjava/aprox)

### Presentation tool used
- https://github.com/gnab/remark/

<br />
*Matej Lazar (mlazar@redhat.com)*
