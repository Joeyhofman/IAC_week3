nsible all -a "ping -c 10.50.10.2"
app1 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: ssh: connect to host 10.50.10.2 port 22: Connection timed out",
    "unreachable": true
}
app2 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: ssh: connect to host 10.50.10.3 port 22: Connection timed out",
    "unreachable": true
}
db1 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: ssh: connect to host 10.50.10.4 port 22: Connection timed out",
    "unreachable": true
}