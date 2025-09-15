ansible all -a "ping -c 10.50.10.2"
[WARNING]: Platform linux on host app2 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
app2 | FAILED | rc=1 >>
ping: invalid argument: '10.50.10.2'non-zero return code
[WARNING]: Platform linux on host db1 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
db1 | FAILED | rc=1 >>
ping: invalid argument: '10.50.10.2'non-zero return code
[WARNING]: Platform linux on host app1 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
app1 | FAILED | rc=1 >>
ping: invalid argument: '10.50.10.2'non-zero return code