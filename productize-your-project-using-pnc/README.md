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
- BUILD.json

---

Analyzing your project
======================
- DA
    - configure on-line
    - produce local build descriptor BUILD.json ?

---

Build using on-line version (Handover to Prod)
==============================================
- (BUILD.json ?)

---

Versioning and patching
=======================
- PME

---

Use artifacts from other build systems (Brew)
=============================================
- use already built artifacts

---

Status
======
- “On-line” Build coordinator in place
- local Build Coordinator (WIP)
- pipe-line WIP
    - JBPM/ESB
- An open question is versioning (PME)
- product patching - what to rebuild if deep dependency is updated
    - an option is to use version ranges

---


Thanks
======

### PNC
- [https://github.com/project-ncl/pnc](https://github.com/project-ncl/pnc)

### Presentation tool used
- https://github.com/gnab/remark/
