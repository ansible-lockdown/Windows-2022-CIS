# Windows Server 2022 CIS

## Configure a Microsoft Server 2022 machine to be [CIS](https://www.cisecurity.org/cis-benchmarks/) compliant

### Based on [ CIS Microsoft Windows Server 2022 v4.0.0 - 05-23-2025 ](https://www.cisecurity.org/cis-benchmarks/)

---

## Public Repository

![Org Stars](https://img.shields.io/github/stars/ansible-lockdown?label=Org%20Stars&style=social)
![Stars](https://img.shields.io/github/stars/ansible-lockdown/Windows-2022-CIS?label=Repo%20Stars&style=social)
![Forks](https://img.shields.io/github/forks/ansible-lockdown/Windows-2022-CIS?style=social)
![Followers](https://img.shields.io/github/followers/ansible-lockdown?style=social)
[![X URL](https://img.shields.io/twitter/url/https/x.com/AnsibleLockdown.svg?style=social&label=Follow%20%40AnsibleLockdown)](https://x.com/AnsibleLockdown)
![Discord Badge](https://img.shields.io/discord/925818806838919229?logo=discord)

![License](https://img.shields.io/github/license/ansible-lockdown/Windows-2022-CIS?label=License)

## Lint & Pre-Commit Tools

[![Pre-Commit.ci](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Windows-2022-CIS/pre-commit-ci.json)](https://results.pre-commit.ci/latest/github/ansible-lockdown/Windows-2022-CIS/devel)
![YamlLint](https://img.shields.io/badge/yamllint-Present-brightgreen?style=flat&logo=yaml&logoColor=white)
![Ansible-Lint](https://img.shields.io/badge/ansible--lint-Present-brightgreen?style=flat&logo=ansible&logoColor=white)

## Community Release Information

![Release Branch](https://img.shields.io/badge/Release%20Branch-Main-brightgreen)
![Release Tag](https://img.shields.io/github/v/tag/ansible-lockdown/Windows-2022-CIS?label=Release%20Tag&&color=success)
![Main Release Date](https://img.shields.io/github/release-date/ansible-lockdown/Windows-2022-CIS?label=Release%20Date)
![Benchmark Version Main](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Windows-2022-CIS/benchmark-version-main.json)
![Benchmark Version Devel](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Windows-2022-CIS/benchmark-version-devel.json)

[![Main Pipeline Status](https://github.com/ansible-lockdown/Windows-2022-CIS/actions/workflows/main_pipeline_validation.yml/badge.svg?)](https://github.com/ansible-lockdown/Windows-2022-CIS/actions/workflows/main_pipeline_validation.yml)
[![Devel Pipeline Status](https://github.com/ansible-lockdown/Windows-2022-CIS/actions/workflows/devel_pipeline_validation.yml/badge.svg?)](https://github.com/ansible-lockdown/Windows-2022-CIS/actions/workflows/devel_pipeline_validation.yml)
![Devel Commits](https://img.shields.io/github/commit-activity/m/ansible-lockdown/Windows-2022-CIS/devel?color=dark%20green&label=Devel%20Branch%20Commits)
![Open Issues](https://img.shields.io/github/issues-raw/ansible-lockdown/Windows-2022-CIS?label=Open%20Issues)
![Closed Issues](https://img.shields.io/github/issues-closed-raw/ansible-lockdown/Windows-2022-CIS?label=Closed%20Issues&&color=success)
![Pull Requests](https://img.shields.io/github/issues-pr/ansible-lockdown/Windows-2022-CIS?label=Pull%20Requests)

---

## Subscriber Release Information

![Private Release Branch](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Private-Windows-2022-CIS/release-branch.json)
![Private Benchmark Version](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Private-Windows-2022-CIS/benchmark-version.json)

[![Private Remediate Pipeline](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Private-Windows-2022-CIS/remediate.json)](https://github.com/ansible-lockdown/Private-Windows-2022-CIS/actions/workflows/main_pipeline_validation.yml)
![Private Pull Requests](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Private-Windows-2022-CIS/prs.json)
![Private Closed Issues](https://img.shields.io/endpoint?url=https://ansible-lockdown.github.io/github_windows_IaC/badges/Private-Windows-2022-CIS/issues-closed.json)

---

## Looking for support?

[Lockdown Enterprise](https://www.lockdownenterprise.com#GH_AL_WINDOWS_2022_cis)

[Ansible support](https://www.mindpointgroup.com/cybersecurity-products/ansible-counselor#GH_AL_WINDOWS_2022_cis)

### Community

On our [Discord Server](https://www.lockdownenterprise.com/discord) to ask questions, discuss features, or just chat with other Ansible-Lockdown users

---

## Caution(s)

This role **will make changes to the system** which may have unintended consequences. This is not an auditing tool but rather a remediation tool to be used after an audit has been conducted.

Check Mode is not supported! The role will complete in check mode without errors, but it is not supported and should be used with caution.

This role was developed against a clean install of the Windows 2022 Operating System. If you are implementing to an existing system please review this role for any site specific changes that are needed.

To use release version please point to main branch and relevant release for the cis benchmark you wish to work with.

## Notes

There are certain settings that, while they can be enforced in the registry, cannot be managed via ADMX and ADML files in Group Policy. This can happen for a few reasons:

1. Direct Registry Settings: Some policies aren’t intended to be configurable through the Group Policy Editor but can still be applied directly in the registry. These settings may not have a corresponding policy definition in ADMX/ADML files. For example, some Microsoft security features or settings introduced in recent updates may not yet be added to the official Group Policy templates.

2. Dynamic or Unsupported Settings: Some settings are dynamic or application-specific, meaning they don’t have the static structure needed for ADMX/ADML. Group Policy might not inherently support managing these settings, or it may require specific application policies that aren't in the standard templates.

3. Context-Specific Policies: Some policies might apply only under specific user or computer contexts. Settings under certain keys, especially under Software\Policies and Software\Microsoft, may rely on the application being directly aware of and respecting the policy. When they aren’t displayed in the Group Policy Editor, it could be because the setting isn’t universally applicable.

4. Windows Version Limitations: Even if settings appear in ADMX files, they might not show up or apply consistently if the version of Windows doesn’t fully support them. This is more common for features that are slowly rolled out across builds or have dependencies.

---

## Matching A Security Level For CIS

It is possible to only run level 1 or level 2 controls for CIS as well as other profile definitions that are set in the CIS release.
This is managed using tags:

- level1-domaincontroller
- level1-memberserver
- level2-domaincontroller
- level2-memberserver
- level1-domainmember
- ngws-domaincontroller
- ngws-memberserver

The control found in defaults main also need to reflect this as this control the testing that takes place if you are using the audit component.

### Next Generation Windows Security profile

Next Generation Windows Security (NGWS) is an optional CIS profile, not a third level.
Its eight controls - 18.9.5.x Device Guard and Credential Guard, and 18.9.26.2 LSA
protection - run only when `win22cis_ngws` is true (default false, in
`defaults/main/main.yml`), and the audit asserts them on the same switch, so the two
always agree. They need virtualization based security support on the host, so turn it
on deliberately. The ngws tags select within the profile; they do not enable it on
their own.

## Coming From A Previous Release

CIS release always contains changes, it is highly recommended to review the new references and available variables. This have changed significantly since ansible-lockdown initial release.
This is now compatible with python3 if it is found to be the default interpreter. This does come with pre-requisites which it configures the system accordingly.

Further details can be seen in the [Changelog](./ChangeLog.md)

## Stand-alone Servers

The benchmark is written for domain joined servers and says it is not intended for
standalone or workgroup systems. This role still runs on one, and treats it as a member
server wherever that is safe: 18 of the member server (MS only) controls apply to any
server that is not a domain controller.

The rest stay member server only:

- 2.2.22, 2.2.27 and 18.4.1 deny or filter network and Remote Desktop logon for local
  accounts. On a standalone server every account is local, so applying them cuts off
  remote administration - the benchmark carries that caution.
- LAPS (18.9.25.x), the Netlogon secure channel (2.3.6.1, 2.3.6.2), cached domain logons
  (2.3.7.6), domain controller unlock (2.3.7.8), 2.3.9.5, 18.6.21.2 and 18.9.28.4 need a
  domain to mean anything.

Section 1 account policy is applied on a standalone server only; on a domain member the
Default Domain Policy owns it.

## CIS GPO Compliance Method

GPO creation now lives in its own role, Windows-2022-CIS-GPO. This role applies the benchmark
directly to a host and no longer creates Group Policy Objects.

## Group Policy Objects

This role applies the benchmark directly to the host it runs against.

This role applies the benchmark directly to the host it runs against. It does not
create Group Policy Objects.

### GPOs are being addressed currently and will reside in a new repository once released.

## Settings Owned By Group Policy

A domain GPO always wins over a value written locally, whether that value is set in the
registry or through the security database. A domain controller refreshes computer policy
roughly every 5 minutes, and a member server every 90 minutes, so a local write to one of
these settings is reverted shortly after this role makes it. The role would otherwise report
a change on every run while the host never actually reaches the required state.

The settings below are defined by the default domain policies on a stock Active Directory
domain. Apply them in Group Policy, or with the Windows-2022-CIS-GPO role, not here.

| Control | Setting | Where it is owned |
|---------|---------|-------------------|
| 2.3.5.4 | `LDAPServerIntegrity` | Default Domain Controllers Policy pins this to `1`. CIS requires `2`, so the two genuinely conflict and this role cannot satisfy the control on a domain controller. It raises a warning instead of writing. |
| 2.3.6.1 | `RequireSignOrSeal` | Default Domain Controllers Policy, pinned to `1`. |
| 2.3.9.2 | `RequireSecuritySignature` | Default Domain Controllers Policy, pinned to `1`. |
| 2.3.9.3 | `EnableSecuritySignature` | Default Domain Controllers Policy, pinned to `1`. |
| Section 1 | Account Policy | The Default Domain Policy sets password and lockout policy for the domain. On a domain member the local `[System Access]` values are overwritten. |
| 2.3.11.6 | `ForceLogoffWhenHourExpire` | Domain scoped for the same reason as section 1. |

Only 2.3.5.4 conflicts with what CIS asks for. The other three registry values are pinned to
the value the benchmark already wants, so they agree today, but they are still owned by
policy rather than by this role and will not change if you alter them locally.

The role detects the domain cases it can and warns at run time: `prelim.yml` raises a warning
for section 1 and 2.3.11.6 when the host is domain joined, and 2.3.5.4 warns on a domain
controller. Those IDs appear in the warning summary printed at the end of the run.

## Auditing (beta)

**The audit component is in beta while we gather feedback.** It is usable and its
results are meaningful, and we would like to hear how it behaves on your estate.
Please raise an issue, or come and talk to us on the [Discord Server](https://www.lockdownenterprise.com/discord).
Remediation is unaffected - `run_audit` and `setup_audit` both default to `false`,
so none of this runs unless you ask for it.

This role is paired with `Windows-2022-CIS-Audit`, a set of syver specs generated
from this role by `scripts/generate_windows_audit.py`, so the audit asserts what
the role actually does rather than a separately maintained restatement of it.
441 of the benchmark's 444 controls are asserted. 2.2.34 and 2.3.10.9 build their
expected state from live host discovery and so have nothing fixed to assert
against, and 2.3.5.4 is owned by Group Policy on a domain controller (see
[Settings Owned By Group Policy](#settings-owned-by-group-policy)). Every control
and its reason code is listed in the audit repo's `coverage.json`.

### Switches

| Variable | Default | Effect |
|---|---|---|
| `setup_audit` | `false` | Place the syver binary and the audit content on the host |
| `run_audit` | `false` | Run the audit before and after remediation |
| `audit_only` | `false` | Run the pre-remediation audit, then stop without remediating |
| `fetch_audit_output` | `false` | Collect the result files after the run |

Pass these as JSON. `-e run_audit=true` sets the *string* `"true"`, which is
truthy by accident, and `-e audit_only=false` sets the string `"false"`, which is
also truthy and does the opposite of what it reads like.

```bash
# stage the binary and content, remediate nothing
ansible-playbook site.yml -e '{"setup_audit": true}'

# audit the host and stop
ansible-playbook site.yml -e '{"run_audit": true, "audit_only": true}'

# remediate with a before and after audit
ansible-playbook site.yml -e '{"run_audit": true}'
```

### Requirements

`syver.exe` is never committed to this repository. The default
`get_audit_binary_method: download` fetches it from the public release named in
`audit_bin_version` (v0.11.1) and verifies the published SHA256. Keep that digest
set: `win_get_url` checks it, and that check is what stands between a compromised
mirror and every audited host running someone else's binary elevated. No Windows
ARM64 asset is published for v0.11.1, so `ARM64_checksum` is deliberately empty
and a download on such a host fails the lookup rather than fetching an amd64
binary.

To supply your own build instead, set `get_audit_binary_method: copy` and point
`audit_bin_copy_location` at it; it defaults to `syver-windows-amd64.exe` in this
role directory.

The audit content defaults to `audit_content: get_url`, which downloads the
`benchmark_v4.0.0` branch of the audit repository as a zip. To test local content
instead, set `audit_content: copy` and point `audit_conf_source` at a checkout of
`Windows-2022-CIS-Audit` on the controller.

## Documentation

- [Read The Docs](https://ansible-lockdown.readthedocs.io/en/latest/)
- [Getting Started](https://www.lockdownenterprise.com/docs/getting-started-with-lockdown#GH_AL_WINDOWS_2022_cis)
- [Customizing Roles](https://www.lockdownenterprise.com/docs/customizing-lockdown-enterprise#GH_AL_WINDOWS_2022_cis)
- [Per-Host Configuration](https://www.lockdownenterprise.com/docs/per-host-lockdown-enterprise-configuration#GH_AL_WINDOWS_2022_cis)
- [Getting the Most Out of the Role](https://www.lockdownenterprise.com/docs/get-the-most-out-of-lockdown-enterprise#GH_AL_WINDOWS_2022_cis)

## Requirements

**General:**

- Basic knowledge of Ansible, below are some links to the Ansible documentation to help get started if you are unfamiliar with Ansible

  - [Main Ansible documentation page](https://docs.ansible.com)
  - [Ansible Getting Started](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html)
  - [Tower User Guide](https://docs.ansible.com/ansible-tower/latest/html/userguide/index.html)
  - [Ansible Community Info](https://docs.ansible.com/ansible/latest/community/index.html)
- Functioning Ansible and/or Tower Installed, configured, and running. This includes all of the base Ansible/Tower configurations, needed packages installed, and infrastructure setup.
- Please read through the tasks in this role to gain an understanding of what each control is doing. Some of the tasks are disruptive and can have unintended consequences in a live production system. Also, familiarize yourself with the variables in the defaults/main/ files.

**Technical Dependencies:**

- Windows 2022 - Other versions are not supported
- Python3 Ansible run environment
- python-xmltodict
- pywinrm or pypsrp

Package 'python-xmltodict' is required if you enable the OpenSCAP tool installation and run a report. Packages python(2)-passlib and python-jmespath are required for tasks with custom filters or modules. These are all required on the controller host that executes Ansible.

## Role Variables

This role is designed so that the end user should not have to edit the tasks themselves. All customizing should be done via the defaults/main/ files or with extra vars within the project, job, workflow, etc.

## Tags

There are many tags available for added control precision. Each control has its own set of tags noting what level, what OS element it relates to, whether it's a patch or audit, and the rule number. Additionally, NIST references follow a specific conversion format for consistency and clarity.

### Conversion Format for NIST References:

  1. Standard Prefix:

    - All references are prefixed with "NIST".

  2. Standard Types:

    - "800-53r5" references are formatted as NIST800-53R5 (with 'R' capitalized). Only Rev 5 is tagged.
    - "800-171" references are formatted as NIST800-171.

  3. Details:

    - Section and subsection numbers use periods (.) for numeric separators.
    - Parenthetical elements are separated by underscores (_), e.g., IA-5(1)(d) becomes IA-5_1_d.
    - Subsection letters (e.g., "b") are appended with an underscore.

### Example of Tag Usage:
Below is an example of the tag section from a control within this role. Using this example, if you set your run to skip all controls with the tag smb, this task will be skipped. Conversely, you can choose to run only controls tagged with smb.

```sh
      tags:
        - level1-domaincontroller
        - level1-memberserver
        - rule_18.4.2
        - patch
        - smb
        - NIST800-171_3.4.2
        - NIST800-171_3.4.6
        - NIST800-171_3.4.7
        - NIST800-53R5_CM-6
        - NIST800-53R5_CM-7
```

### Conversion Examples in Use:
  - 800-53r5 IA-5(1)(d) -> NIST800-53R5_IA-5_1_d
  - 800-53r5 AC-17(2) -> NIST800-53R5_AC-17_2
  - 800-53r5 CM-6b. -> NIST800-53R5_CM-6_b
  - 800-171 3.5.2 -> NIST800-171_3.5.2

By maintaining this consistent tagging structure, it becomes easier to filter and manage tasks based on specific controls and compliance requirements.

## Community Contribution

We encourage you (the community) to contribute to this role. Please read the rules below.

- Your work is done in your own individual branch. Make sure to Signed-off-by and GPG sign all commits you intend to merge.
- All community Pull Requests are pulled into the devel branch
- Pull Requests into devel will confirm your commits have a GPG signature, Signed-off-by, and a functional test before being approved
- Once your changes are merged and a more detailed review is complete, an authorized member will merge your changes into the main branch for a new release

## Pipeline Testing

uses:

- ansible-core 2.16
- ansible collections - pulls in the latest version based on requirements file
- runs the audit using the devel branch
- This is an automated test that occurs on pull requests into devel
- self-hosted runners using OpenTofu

## Local Testing

  - Ansible
    - ansible-core 2.20.0 - python 3.13

## Credits and Thanks

Massive thanks to the fantastic community and all its members.

This includes a huge thanks and credit to the original authors and maintainers.
