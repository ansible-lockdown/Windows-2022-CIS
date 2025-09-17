# ChangeLog

September 2025
  - Updated When For Control 18.4.6
  - Updated Title 2.3.10.10
  - Updated 2.3.6.5 Task
  - PR's Addressed:
    - [#79](https://github.com/ansible-lockdown/Windows-2022-CIS/pull/79/files) - Thanks @ShawnHardwick

## Release 4.0.0

June 2025
  - This Release is based on CIS Benchmark v4.0.0
  - Internal 90 Auto Promotion Workflows Added
  - Fixed Tags  from _ to . in he control numbers to align with other controls.
  - Issues Addressed:
    - Fixed GPO 18.9.26.2 to enter the correct registry entry.
  - CIS Control Changes Summary (v4.0.0 vs v3.0.0) - Please review them in the CIS documentation and adjust your playbooks.
    - Removed
      - 2.3.1.1: Accounts: Block Microsoft accounts removed; all controls in the section shifted up
      - 18.4.2: Removed; all subsequent controls moved up
      - 18.10.15.8: Removed in v4.0.0
      - 18.10.42.17: Removed in v4.0.0
    - Added
      - 2.3.11.8: Network security: LDAP client encryption requirements
      - 2.3.11.14: New control
      - 2.3.17.2: Valid variable checking
      - 18.4.6: Valid variable checking
      - 18.6.4.4: IPV6 DNS Servers
      - 18.6.7.1: Lanman Server SMB
      - 18.6.8.2: Lanman Workstation Encryption
      - 18.10.18.4: Malware Scan Override
      - 18.10.18.6: MSS Certificate Validation Bypass
      - 18.10.18.7: Windows Package Manager command line
      - 18.10.29.2: Mark of the Web tag
      - 18.10.43.4.1: Enable EDR in block mode
      - 18.10.43.8.1: Convert warn verdict
      - 18.10.43.10.1: Configure real-time protection during OOBE
      - 18.10.43.11.1.1.1: Configure Brute-Force Protection aggressiveness
      - 18.10.43.11.1.1.2: Configure Remote Encryption Protection Mode
      - 18.10.43.11.1.2.1: Remote Encryption Protection blocks threats
      - 18.10.43.13.1: Scan excluded files and directories
      - 18.10.43.13.4: Trigger a quick scan after X days
      - 18.10.43.17: Control whether exclusions are visible to local users
      - 18.10.58.2: Enable Basic feed authentication over HTTP
    - Updated
      - 2.2.38: Title updated in Remediate and GPO
      - 18.6.4.1: Replaced in v4.0.0
      - 18.7.2, 18.7.3, 18.7.5: Title updates
      - 18.9.13.1, 18.9.19.2: Title updates
      - 18.10.18.1: Level changed to Level 2
      - 18.10.28.2 → 18.10.29.3: Moved due to new 18.10.29.2
      - 18.10.42.6.1: Removed One of the ASR's
    - Renumbered / Moved
      - 18.10.5.1 → 18.10.6.1
      - 18.10.7.1–3 → 18.10.8.1–3
      - 18.10.8.1.1 → 18.10.9.1.1
      - 18.10.10.1 → 18.10.11.1
      - 18.10.12.1–3 → 18.10.13.1–3
      - 18.10.13.1 → 18.10.14.1
      - 18.10.14.1–2 → 18.10.15.1–2
      - 18.10.15.1–7 → 18.10.16.1–7
      - 18.10.17.x → 18.10.18.x
      - 18.10.25.x.x → 18.10.26.x.x
      - 18.10.36.x → 18.10.37.x
      - 18.10.40.x → 18.10.41.x
      - 18.10.41.x → 18.10.42.x
      - 18.10.42.5.x → 18.10.43.5.x
      - 18.10.42.x.x.x → 18.10.43.x.x.x
      - 18.10.50.x → 18.10.51.x
      - 18.10.55.x → 18.10.56.x
      - 18.10.56.x → 18.10.57.x
      - 18.10.57.x → 18.10.58.x
      - 18.10.58.x → 18.10.59.x
      - 18.10.62.x → 18.10.63.x
      - 18.10.75.x.x → 18.10.76.x.x
      - 18.10.79.x → 18.10.80.x
      - 18.10.80.x → 18.10.81.x
      - 18.10.86.x → 18.10.87.x
      - 18.10.88.x.x → 18.10.89.x.x
      - 18.10.89.x → 18.10.90.x
      - 18.10.91.x.x → 18.10.92.x.x
      - 18.10.92.x.x → 18.10.93.x.x
    - Structural Changes
      - Section 17: Credential Validation auditing now uses the GUID {0CCE923F-69AE-11D9-BED3-505054503030}
        - This makes auditing language-agnostic and more consistent across regional builds.

## Release 3.0.5
September 2025 Update
- Issues Addressed:
    - [#73](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/73) - Thank you @ShawnHardwick

## Release 3.0.4

May 2025 Update #2
  - Issues Addressed:
    - Fixed 1.1.6 to apply to all systems except for Domain Controllers. This is present in standalone version. - Thanks @mfortin
    - Re-Verified 18.10.79.2 Paths

## Release 3.0.3

May 2025 Update
  - Issues Addressed:
    - Fixed Control 18.6.14.1 For Missing RequirePrivacy=1 in Ansible Hardening. - Thanks @mfortin
    - Updated 18.10.56.3.10.2 value to 60000 from 6000 in remediate and GPO - Thanks @mfortin
    - Verified 18.10.79.2 Path In Remediate - Thanks @mfortin
    - Updated 18.10.93.4.1 ManagePreviewBuildsPolicyValue to 1. - Thanks @mfortin
    - Updated Pipelines Branches Trigger
    - Updated Readme with New Badges

## Release 3.0.2

February 2025 Update
  - Added new Readme Badges
  - General Typos and Fixes
  - All Workflows Updated
  - Fixed Control Tag for rule_2.3.10.9

## Release 3.0.0

December 2024 Update
  - Added the ability create tailored Group Policy Objects (GPOs) compliant with CIS benchmarks using Ansible.
    - Custom GPOs based around variables in defaults/main.
    - New variables for the GPO creation.
    - Turn on and off controls to add them to the GPOs.
    - More flexibility in the way the GPOs are created for Lvl1 and Lvl2.
  - Banner Update
  - Updated prelim Set system facts based on gather facts module naming.
  - Updated all win_regedit paths to reflect capitalized System/Software registry entries.
  - Removed all "state: present" (Default) value from the "win_regedit" module.
  - Updated tasks in the prelim and post to also headers matched the section.
  - Verified all controls meet new CIS standards for 3.0.0
  - Updated when's with "primary domain controller" to "domain controller"
  - Fixed meta for galaxy.
  - Added NIST Tags
  - PR's Addressed:
    - [#53](https://github.com/ansible-lockdown/Windows-2022-CIS/pull/53/files) - Thanks @tgoetheyn
  - Issues Addressed:
    - [#51](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/51) - Thanks @msachikanta
    - [#50](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/50) - Thanks @msachikanta
    - [#49](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/49) - Thanks @animatco
    - [#48](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/48) - Thanks @animatco
    - [#45](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/45) - Thanks @Crombell95
    - [#32](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/32) - Thanks @RomainPisters (Verified It has been addressed.)
    - Updated DisableBkGndGroupPolicy To 0 "Disabled" - Thanks @dennisharder-alight
    - Updated ManagePreviewBuildsPolicyValue To 0 "Disabled" - Thanks @dennisharder-al
    - Updated LegalNoticeCaption var with title fix - Thank you @rlmass
  - Control Changes (Please review them in the CIS documentation and adjust your playbooks.)
    - Added Controls win22cis_rule_2_3_11_11 - 13
    - Section 2 had controls that updated numbers.
    - Section 9 had controls removed from CIS in this version.
    - Section 18 had controls removed, added, and number updates (To many to list).
    - Section 19 had controls removed and updated numbering.
  - New Variable Options
      - 18.9.5.2
      - 18.9.25.1
      - 18.9.25.5
      - 18.9.25.6
      - 18.9.25.7
      - 18.9.25.8
      - 18.9.39.1

## Release 2.0.1

April 2024 Update
- Issues Addressed:
  - [#32](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/32) - Thank you @RomainPisters

March 2024 Update
- Thank you @MrSteve81 for the enhancements to this release!
  - Improved 19.x section logic for Windows local user SIDs and HKU support.
  - Reboot handler and logic Improvement with skip_reboot var feature.
  - win_skip_for_test var update with additional description and supported controls of 2.2.20, 2.2.25, and 2.2.26.
  - Mislabeled control fix for win22cis_rule_18_9_7_2
  - Improved logic for win22cis_cloud_based_system 1.2.x controls.

February 2024 Update
- Issues Addressed:
    - [#27](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/27) - Thank you @SwaffelSmurf
    - [#28](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/28) - Thank you @natilik-mikeguy
    - [PR26](https://github.com/ansible-lockdown/Windows-2022-CIS/pull/26) - Thank you @ai13f
    - Typo and bug fixes

## Release 2.0.0

September 2023
- This Release is based on CIS Benchmark v2.0.0

- Incorporated order fix for Lockout Controls:
  https://github.com/ansible-lockdown/Windows-2022-CIS/pull/16
- https://github.com/ansible/ansible/issues/62594

- Incorporated Disable Print Spooler Service: https://github.com/ansible-lockdown/Windows-2022-CIS/pull/19
