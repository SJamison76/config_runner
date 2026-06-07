# config_runner
Ansible Playbook to deploy configurations to different network devices.

Error handling on Juniper so if the commit fails, a rollback 0 is performed to remove the candidate config from becoming stale. Works on any network device since we are sending raw commands directly in the commands.txt file. The first login fingerprints the device with a show version, and if it passes for what you have stated in the commands.txt file it will execute. if it doesnt pass, then it fails as seen below.

Summary report afterwards shows successes, failures, and other information for remediation.


```Looking at Phase 5c in the file:
======================================================================
CHANGE WINDOW SUMMARY
======================================================================
Executed    : 2026-06-06 14:32:01
Vendor      : cisco
Commands    : ./commands.txt
Targets     : ./targets.txt

TOTALS
------
Total Targets   : 8
Vendor Matched  : 6
Vendor Mismatch : 2  ← skipped, no commands sent

Reachable       : 5
Unreachable     : 1
Commit Failures : 0

Clean Success   : 5

======================================================================
VENDOR MISMATCH — SKIPPED (manual verification required)
======================================================================
  10.2.1.1
  10.2.1.2

======================================================================
UNREACHABLE DEVICES (manual follow-up required)
======================================================================
  10.1.1.1

======================================================================
CLEAN SUCCESS
======================================================================
  10.1.11.2
  10.1.11.3
  10.1.11.4
  10.1.11.5
  10.1.11.6
