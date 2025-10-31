# Windows Containers on OpenShift

Showroom-based workshop for running Windows containers on OpenShift, compatible with OCP 4.20+.

## Overview

This workshop teaches OpenShift administrators how to deploy and manage Windows containers alongside Linux workloads in a hybrid cluster environment.

### What You'll Learn

- **Windows Machine Config Operator (WMCO)**: Install and configure the operator to enable Windows node support
- **Hybrid Cluster Setup**: Deploy Windows nodes alongside existing Linux infrastructure
- **Windows Workload Deployment**: Run Windows containers on OpenShift
- **Networking**: Understand Windows-specific networking requirements
- **Storage**: Configure persistent storage for Windows containers
- **Monitoring & Troubleshooting**: Manage Windows nodes and workloads

### Prerequisites

- OpenShift 4.20+ cluster with admin access
- Understanding of basic OpenShift concepts
- Familiarity with Windows Server concepts helpful but not required

---

## Workshop Structure

This is a focused, single-module workshop:

**Module**: Windows Containers
- Installing the Windows Machine Config Operator
- Creating Windows MachineSet
- Deploying Windows workloads
- Networking configuration
- Monitoring Windows nodes

**Duration**: Approximately 60-90 minutes

---

## Repository Structure

```
openshift-windows-workshop-showroom/
├── default-site.yml          # Antora playbook
├── content/
│   ├── antora.yml           # Antora component config
│   └── modules/
│       └── ROOT/
│           ├── nav.adoc     # Navigation
│           ├── pages/
│           │   └── windows-containers.adoc
│           └── images/
│               └── windows-containers/
│                   ├── wmco-card.png
│                   ├── wmcodiagram.png
│                   └── ...
└── README.md
```

---

## Local Development

```bash
# Install Antora
npm install -g @antora/cli@3.1 @antora/site-generator@3.1

# Build the workshop
antora default-site.yml

# Serve locally
cd public && python3 -m http.server 8080
# Visit: http://localhost:8080
```

---

## Deployment

This workshop is deployed using the `ocp4_workload_showroom` AgnosticD workload.

### AgnosticV Configuration

```yaml
ocp4_workload_showroom_content_git_repo: https://github.com/jnewsome97/openshift-windows-workshop-showroom.git
ocp4_workload_showroom_content_git_repo_ref: main
ocp4_workload_showroom_content_antora_playbook: default-site.yml
```

### Deployment Components

- **Content**: This Git repository
- **Terminal**: `quay.io/rhpds/openshift-showroom-terminal-ocp:latest`
- **Framework**: Modern Showroom with RHDP theme v0.0.1
- **Deployment**: Helm chart from showroom-deployer

---

## OCP 4.20 Compatibility

All workshop content and CLI tools are compatible with OpenShift 4.20.1.

### Windows Node Requirements

- **OpenShift Version**: 4.20+
- **Windows Server Version**: Windows Server 2019 LTSC or 2022
- **WMCO Version**: Compatible with OCP 4.20
- **Cloud Platform**: AWS, Azure, or vSphere (platform-specific requirements apply)

---

## Related Workshops

For comprehensive OpenShift administration training, see:
- [OpenShift Operations Workshops](https://github.com/jnewsome97/openshift-ops-workshops-showroom) - Full admin training with multiple variants

---

## Credits

This workshop content is based on the original [Windows Containers Quickstart](https://github.com/RedHatWorkshops/windows-containers-quickstart) by Red Hat Workshops, adapted for the modern Showroom framework with Antora.

---

## Theme

Uses RHDP Showroom theme v0.0.1 with modern Red Hat branding.
