# Shell vs Modules — Afwegingen

Nooit shell gebruiken wanneer:
* Er een officiële Ansible-module bestaat die hetzelfde doet (bv. ansible.builtin.file, ansible.builtin.package, ansible.builtin.service).
* Idempotentie belangrijk is → shell-commando’s hebben geen ingebouwde state-checks.
* Je systeemonafhankelijkheid en herhaalbaarheid wilt behouden.

Wanneer shell wel acceptabel is:
* Als er geen geschikte Ansible-module bestaat.
* Voor tijdelijke of diagnostische commando’s (bv. shell: "uptime") maar alleen met duidelijke guardrails en changed_when: / creates: om idempotentie te behouden.

## Motivatie:
Theorie stelt dat Ansible’s kracht zit in declaratieve modules die gewenste state beschrijven. Shell breekt dit model, omdat je imperative logica uitvoert. Gebruik het alleen als laatste redmiddel, mét aanvullende checks.