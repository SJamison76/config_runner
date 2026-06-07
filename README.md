# config_runner
Ansible Playbook to deploy configurations to different network devices.

Error handling on Juniper so if the commit fails, a rollback 0 is performed to remove the candidate config from becoming stale. Works on any network device since we are sending raw commands directly in the commands.txt file.

Summary report afterwards shows successes, failures, and other information for remediation.


Looking at Phase 5c in the file:
======================================================================
CHANGE WINDOW SUMMARY
======================================================================
Executed    : 2026-06-06 14:32:01
Vendor      : cisco
Commands    : ./commands.txt
Targets     : ./targets.txt

TOTALS
------
Total Targets   : 10
Reachable       : 8
Unreachable     : 2
Commit Failures : 0

Clean Success   : 8

======================================================================
UNREACHABLE DEVICES (manual follow-up required)
======================================================================
  10.1.1.1
  10.1.1.2

======================================================================
CLEAN SUCCESS
======================================================================
  10.1.1.3
  10.1.1.4
  ...
