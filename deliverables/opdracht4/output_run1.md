ansible-playbook -i inventory.ini playbooks/04_idempotence_guardrails.yml

PLAY [Idempotence & Guardrails] *********************************************************************************************************************************************************************************

TASK [Gathering Facts] ******************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host app1 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [app1]
[WARNING]: Platform linux on host db1 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [db1]
[WARNING]: Platform linux on host app2 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [app2]

TASK [Ensure /tmp/demo.txt exists] ******************************************************************************************************************************************************************************
changed: [app2]
changed: [app1]
changed: [db1]

TASK [Copy config file to /etc/demo.conf] ***********************************************************************************************************************************************************************
changed: [app1]
changed: [app2]
changed: [db1]

TASK [Check if /tmp/demo.txt exists] ****************************************************************************************************************************************************************************
ok: [app1]
ok: [app2]
ok: [db1]

TASK [Assert that /tmp/demo.txt exists] *************************************************************************************************************************************************************************
ok: [app1] => {
    "changed": false,
    "msg": "/tmp/demo.txt is aanwezig."
}
ok: [app2] => {
    "changed": false,
    "msg": "/tmp/demo.txt is aanwezig."
}
ok: [db1] => {
    "changed": false,
    "msg": "/tmp/demo.txt is aanwezig."
}

TASK [Gather service facts] *************************************************************************************************************************************************************************************
ok: [db1]
ok: [app2]
ok: [app1]

TASK [Assert that ssh is enabled] *******************************************************************************************************************************************************************************
ok: [app1] => {
    "changed": false,
    "msg": "ssh service is enabled."
}
ok: [app2] => {
    "changed": false,
    "msg": "ssh service is enabled."
}
ok: [db1] => {
    "changed": false,
    "msg": "ssh service is enabled."
}

PLAY RECAP ******************************************************************************************************************************************************************************************************
app1                       : ok=7    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
app2                       : ok=7    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
db1                        : ok=7    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
