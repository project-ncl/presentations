Productize Your Project Using PNC
=================================
<br />


<br />


???

Visit [http://project-ncl.github.io/presentations/productize-your-project-using-pnc/] (http://project-ncl.github.io/presentations/productize-your-project-using-pnc/) to see slides in presentation mode.

---

Agenda
======

### - Productization requirements

### - Why PNC

### - Analyzing your project

### - Coordinating local builds with PNC

### - Build using on-line version

### - Versioning

### - Use artifacts from other build systems (Brew)

### - Implementation Status

---

Productization requirements
===========================
- Off-line (internal) reproducibility
    - SCM clone / sync
    - Capture all dependencies
        - Maven
        - Other http
- Ability to produce patches
- Ability to produce Maven repository for customers

---

Why PNC
=======
- Analyze community projects
    - Build should pass at first
    - Track all maven dependencies
    - Compare which artifacts are already in the system
    - Track also non mvn requests
- Re-use artifacts from other project
    - Help align version with our other products
    - Easier patching
- Local environment build coordinator
    - Easier work with moving dependencies versions
    - Uses same config file (handover doc) as on-line

---

Analyzing your project
======================
- Dependency Analysis
    - Check a project is using 'supported' versions for dependencies
    - Check what dependencies are already available within PNC
    - May be run as standalone tooling or configured on-line
    - Produce build descriptor to use for local builds (BUILD.json)
- Extensible set of QA checks to get advance notification of any problems integrating your project

---

Versioning
==========
- Project that is built needs a redhat-x suffix to avoid a GAV clash with external repositories
- Aim is to automate this and store productisation changes on a SCM branch
- Automatically change the version of the project
- Tooling to help with the alignment of dependencies

---

Use artifacts from other build systems (Brew)
=============================================
- Re-use already built artifacts
- Option to configure "trusted sources"
    - maven.repository.redhat.com

---

Coordinating local builds with PNC
==================================
- Describe all build details with a config file
    - SCM location, tag / commit-id
    - Build command line (maven profiles and other required parameters)
- Build project and dependencies from source with single command
    - Easier team work with moving versions
- Supports non Maven and non Java builds
- The ability to use the same isolated build environment

---

Build using on-line version
===========================
- BPM managed product pipe-line
    - External triggers (SCM update, CLI)
    - Pom manipulation to pick the latest version
    - Parallel builds
    - QA
    - Publishing
- Ability to import / export the build configuration (BUILD.json)
- Automatic Import
    - Tooling will be provided to assist building your Project inside PNC

---

Implementation Status
=====================
- “On-line” Build coordinator in place
    - Isolated reproducible environment
    - Maven dependency tracking and storing
    - Non Maven dependency tracking (WIP)
- Local Build Coordinator (WIP)
- Versioning tooling (WIP)
- Pipe-line (WIP)
    - JBPM/ESB

---


Thanks
======

### PNC
- [https://github.com/project-ncl/pnc](https://github.com/project-ncl/pnc)

### Presentation tool used
- https://github.com/gnab/remark/
