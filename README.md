# config_runner
Ansible Playbook to deploy configurations to different network devices.

Error handling on Juniper so if the commet fails, a rollback 0 is performed to remove the candidate config from becoming stale.

Summary report afterwards shows successes, failures, and other information for remediation.
