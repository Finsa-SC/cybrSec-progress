# systemctl

### Manage Service
start service
```bash 
systemctl start [service]
```

stop service
```bash
systemctl stop [service]
```

restart service
```bash
systemctl restart [service]
```

show service status
```bash
systemctl status [service]
```

---

### Set up Service at Boot Time

automatically activate at boot
```bash
systemctl enable [service]
```
inactive at boot time
```bash
systemctl disable [service]
```
Check if the service is set to automatic
```bash
systemctl is-enable [service]
```

---

### Monitoring Unit

show active unit
```bash
systemctl list-units
```
show all unit and status
```bash
systemctl list-unit-files
```
checking if the service is running
```bash
systemctl is-active [service]
```

---

### Service Configuration 

open service file configuration
```bash
sudo systemctl edit [service].service
```
> copy only what you want to configure into the empty field provided, **don't put it under the warning** where the file below it will never be executed, just rewrite only the configuration you want to change in the safe zone

#### some standard configurations__

- `ProtectHome=yes`: untuk membuat user didalam tidak dapat mengakses home ataupun root directory, jika user memaksa maka dia tidak akan mendapat daftar apa apa.
- `ProtectSystem`: Untuk pembatasan user dalam pengaksesan folder
- `NoNewPrevileges=yes`: Service tidak akan pernah bisa menaikan tingkat kekuasaannya/naik menjadi super user(root)
- `PrivateTmp`: Membuat Temporary khusus yang terpisah denga /tmp biasanya
