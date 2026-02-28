# systemctl

#### Manage Service
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

#### Set up Service at Boot Time

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

#### Monitoring Unit

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
