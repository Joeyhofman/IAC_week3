# Playbook uitvoeren
Draai het playbook met:

``` bash
ansible-playbook -i inventory.ini playbooks/03_multi_group.yml
```

## Variabelen
De playbook taken gebruiken group_vars om pakketnamen en services te parametriseren:
* **group_vars/app.yml**
  * `app_package`: naam van het chrony-pakket (bijv. chrony).
  * `app_service`: naam van de chrony-service (bijv. chronyd of chrony, afhankelijk van Distro).

* **group_vars/db.yml**
   * `db_package`: naam van het pakket voor de DB-groep (hier: curl).

Zo kan hetzelfde playbook werken op verschillende distros door alleen de variabelen aan te passen.

# Dry-run en observaties
``` bash
ansible-playbook -i inventory.ini playbooks/03_multi_group.yml --check
```

Observaties bij `--check`:

* **Pakketinstallatie**: Ansible kan meestal voorspellen of er een wijziging nodig is, maar niet altijd (bijv. wanneer package metadata ontbreekt).
* **Services**: In check-mode kan Ansible niet garanderen of een service daadwerkelijk gestart zou worden, het meldt alleen een verwachte wijziging.
