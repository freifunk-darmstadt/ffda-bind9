Das ist unser Zonen-File für unbound.

In der unbound.conf muss die Domain ffda. noch als private Domain eingetragen werden,
so dass diese auf private IP-Bereiche zeigen kann.

Hierzu im server-Block folgendes einfügen:
    # handle .ffda top-level-domain
    private-address: fdca:ffee:ffda::/64
    private-domain: "ffda."

Außerdem muss das Zonen-File auf der Root-Ebene noch eingebunden werden.
    include: /etc/unbound/ffda.conf


Als DNS-Server stehen derzeit folgende Knoten zur Verfügung:
    Aktiv:
    - 0.dns.ffda / fdca:ffee:ffda::1 (hexa-)

    In Arbeit:
    - 1.dns.ffda / fdca:ffee:ffda::2 (fleaz) 
