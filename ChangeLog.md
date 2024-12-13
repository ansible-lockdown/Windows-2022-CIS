# ChangeLog

## Release 2.0.1

December 2024 Updates
- Updated 1.1.2 When logic
- Issues Addressed:
  - [#51](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/51) - Thank you @msachikanta
  - [#50](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/50) - Thank you @msachikanta
  - [#48](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/48) - Thanks @animatco
  - [#45](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/45) - Thanks @Crombell95
  - [#32](https://github.com/ansible-lockdown/Windows-2022-CIS/issues/32) - Thanks @RomainPisters (Verified It has been addressed.)
- PR's Addressed:
  - [#53](https://github.com/ansible-lockdown/Windows-2022-CIS/pull/53/files) - Thanks @tgoetheyn

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
