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

### - Build using on-line version (Handover to Prod)

### -

### -

### -


---

Productization requirements
===========================
- off-line (internal) reproducibility
    - scm clone / sync
    - capture all dependencies
        - maven
        - other http

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
    - easier work with moving dependencies versions
    - uses same config file (handover doc) as on-line

---

Coordinating local builds with PNC
==================================
- Local build will provide the ability to use the same isolated build environment
- Ability to import / export the build configuration (e.g. through a BUILD.json file)

---

Analyzing your project
======================
- Dependency Analysis
    - Check a project is using 'supported' versions for dependencies.
    - Check what dependencies are already available within PNC.
    - May be run as standalone tooling or configured on-line
    - produce local build descriptor BUILD.json ?
- Automatic Import
    - Tooling will be provided to automatically create the relevant BuildConfigurations for your Project

---

Build using on-line version (Handover to Prod)
==============================================
- (BUILD.json ?)

---

Versioning
=======================
- Project that is built needs a redhat-x suffix to avoid a GAV clash
- Aim is to automate this and store productisation changes on a SCM branch.
- Tooling to change the version of the project is still in development.
    - Some elements of current tooling (POM Manipulation Extension) may be used.
- Tooling should also handle alignment of dependencies
    - Design of this (e.g. how to handle picking the correct versions is currently under discussion).


---

Use artifacts from other build systems (Brew)
=============================================
- May use already built artifacts
- Will access maven.repository.redhat.com for 'released' artifacts

---

Implementation Status
======================
- “On-line” Build coordinator in place
- local Build Coordinator (WIP)
- pipe-line WIP
    - JBPM/ESB

---


Thanks
======

### PNC
- [https://github.com/project-ncl/pnc](https://github.com/project-ncl/pnc)

### Presentation tool used
- https://github.com/gnab/remark/
