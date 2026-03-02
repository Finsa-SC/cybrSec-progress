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

- `ProtectHome=yes`: to prevent users inside from accessing the home or root directory, if the user forces it then he will not get any list.
- `ProtectSystem`: To limit user access to folders
- `NoNewPrevileges=yes`: Service will never be able to increase its power level/rise to super user (root)
- `PrivateTmp`: Create a special Temporary that is separate from the usual /tmp
