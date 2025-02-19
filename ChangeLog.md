# ChangeLog

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
