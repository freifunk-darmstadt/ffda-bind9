Das ist unser Zonen-File für unbound.

In der unbound.conf muss die Domain ffda. noch als private Domain eingetragen werden,
so dass diese auf private IP-Bereiche zeigen darf.

Hierzu im server-Block folgendes einfügen:
```
    # handle .ffda tld
    private-address: fdca:ffee:ffda::/64
    private-domain: "ffda."
```

Außerdem muss das Zonen-File auf der Root-Ebene noch eingebunden werden.
```
    include: /etc/unbound/ffda.conf
```

Hierzu sollte die Konfiguration aus dem Git-Repository einfach gesymlinked werden.
