*Because sharing open hardware projects should be like sharing open software projects*
# About the Distributed OSHW Framework (DOF)

**The DOF (Distributed OSHW Framework)** is a methodology for documenting and sharing Open Source Hardware (OSHW); an approach to model the "source" of an OSHW project, developed by [Mach 30](http://mach30.org/).

---

## Use the DOF to unlock OSHW's potential

Open source software (OSS) has decades of accumulated practice: collaboration workflows, documentation conventions, modularity patterns, and flexible tooling. Without a framework like the DOF, OSHW projects largely can't participate in any of that. The DOF is our answer to that gap, a way to treat hardware source the way OSS treats code, so the same solutions start applying.

### Improve collaboration for project maintainers and contributors

In OSS, contributors and maintainers work through diffs, you see exactly what changed, review it, and merge it. It works because source code is text, and text is diffable. OSHW projects historically haven't had an equivalent. The DOF structures hardware project data so that changes between versions are visible and reviewable in the same way, through diffs. 

### Achieve greater documentation standards
In software, the README, changelog, and structured docs live right alongside the code and are versioned with it, keeping documentation drift in check. Yet in hardware we see docs as separate files, updated inconsistently, with no clear record of why a design decision was made or what changed between versions. By modeling hardware projects as source, docs belong in the repo, they version alongside the design, and the history of the project becomes legible.

### Get reuse and modularity

In software, if a library solves a problem well, you don't copy-paste it into every project that needs it, you declare it as a dependency and pull it in. Hardware hasn't had a clean equivalent to this. The DOF introduces composability for hardware: a subcomponent like a 3D printer extruder can live in its own standalone repository and be treated as a package. Multiple projects (say, D3D-Pro and D3D-Universal) can both depend on it independently, get updates when it improves, and contribute back to a single shared design. Managing subcomponents this way is optional, but it's what makes a hardware ecosystem rather than a pile of one-off projects.

### Maintain portability

We provide reference implementation tooling that uses git, npm, and gradle However, the methodology is tool-agnostic and can be migrated to other version control, package management, and build tools. Our documentation contains everything a developer needs to use their own stack. 

*Our approach was driven by feedback from the community. See our [user stories & community feedback](https://dof-initiative.github.io/oshw-pm-user-stories)*.

---

Watch [J Simmons](https://thejsimmons.com/) talk **Fire, Smoke and Open Source Hardware** at [SCALE 2023](https://www.socallinuxexpo.org/scale/20x/presentations/fire-smoke-and-open-source-hardware):

[![J Simmons talk Fire, Smoke and Open Source Hardware](https://img.youtube.com/vi/qIMT--XEZiM/hqdefault.jpg)](https://www.youtube.com/watch?v=qIMT--XEZiM)

Dr. Simmons discusses the Mach 30's Shepard Test Stand as a case study demonstrating that open source software practices can be applied to aerospace hardware, detailing the project's successes, lessons learned, and need for future work, such as the creation of the DOF and related projects.

---

## Projects in Development
To advance the adoption and effectiveness of the DOF, we are actively developing and maintaining several complementary projects, each addressing a key aspect of DOF documentation, modeling, and tool support.
- [yaml-datastore](https://github.com/dof-initiative/yaml-datastore): The library for storing and manipulating data across multiple YAML files. Developed to meet the needs of m30ml, which requires handling of data spread across multiple YAML files and directories.
- m30ml: A lightweight YAML-based MBSE modeling language, to create structured ontologies (e.g. user stories, activities) needed for DOF. Loosely inspired by SysML v2, but intended for filesystem use.
- [m30pm](https://github.com/dof-initiative/m30pm): Minimum viable tooling to support defining and executing the next generation of the methodology (to be defined using a domain specific LinkML schema). CRUDs schemas and data described in m30ml. To support CRUD operations for complex projects, m30pm will use yaml-datastore.
- [linkml schema](https://github.com/dof-initiative/linkml-schema): Fork of linkml schema to make it compatible with npm.

## Legacy projects for Reference
- [DOF Repository](https://github.com/dof-initiative/dof-legacy): The legacy implementation and reference for the Distributed OSHW Framework (DOF) methodology itself. This repository documents the principles, workflows, and best practices for DOF, serving both as a historical artifact and a foundation for ongoing tool and process development.
- [m30ml](https://github.com/dof-initiative/m30ml-legacy): The legacy specification and reference for m30ml models. The spec folder contains historical examples of structured ontologies we could support.
  
---

## Ready to build the future of OSHW?
Contribute ideas, code, and feedback.  [**Join the Discussion on GitHub**](https://github.com/dof-initiative/oshw-pm-user-stories/issues?q=is%3Aissue%20state%3Aopen%20-label%3Ahousekeeping)

[Mach 30 Distributed OSHW Framework Workspace (Kasm Image)](https://github.com/dof-initiative/kasm-dof-workspace) - This Kasm workspace is set up with all DOF tooling. Use of the workspace recommended for Mach 30 volunteers and contributors, as it ensures a consistent, reproducible developer environment. 

---

## Frequently Asked Questions

**Q: What is the value of OSHWA certification and how does the DOF support it?**  

A: OSHWA (Open Source Hardware Association) certification helps the community identify hardware projects that meet the widely accepted definition of open source hardware. The DOF methodology was developed to align with this [definition](https://oshwa.org/resources/open-source-hardware-definition/) and support the [requirements of the OSHW community](https://dof-initiative.github.io/oshw-pm-user-stories/).

**Q: Is the DOF a tool?**  

A: No, the DOF is a methodology you can use with any tools or platforms. Like [Docs-as-Code](https://www.writethedocs.org/guide/docs-as-code/) is a methodology, one could consider the DOF as Docs-as-Models-as-Code; the framework treats documentation as a model, managed just like source code.  
- **Docs-as-Models:** Your docs are a structured, machine-queryable model of your hardware.
- **Models-as-Code:** These models live in your repository, versioned, reviewable, and forkable like any codebase.

**Q: I'm interested in using the DOF for my hardware project, how do I get started?**

A: The DOF is still in development, as we are currently working on completing the tooling. However you can look at an example projects in legacy DOF to get an idea (see next question). 

**Q: Are there example projects available?**

A: Yes, there are a couple of example projects using the legacy tooling: 

- [D3D 3D Printer](https://github.com/AlexandriaLittle/d3d-pro) Models a 3D printer design by contributor Alexandra Little for the Open Source Ecology D3D project which renders to https://alexandrialittle.github.io/d3d-pro/.

- [Sealion Mission Architecture](https://github.com/odu-cga-cubesat/sealion-mission-architecture) Ground station & flight software architecture for the joint CubeSat mission between Old Dominion University & Coast Guard Academy. Includes commentary on where the legacy tooling needs to be improved. 

**Q: Are there any active communities or forums to discuss DOF devlopment?**

A: Yes: 
- [Discord](#) (Coming Soon)
- [**GitHub Issues**](https://github.com/dof-initiative/oshw-pm-user-stories/issues?q=is%3Aissue%20state%3Aopen%20-label%3Ahousekeeping)
