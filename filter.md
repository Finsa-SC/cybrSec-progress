## Capture Filter
#### 🏠 Host/IP

- Spesific IP
```bash
host 192.168.1.1
```

- Only Sender
```bash
src host 192.168.1.1
```

- One Network
```bash
net 192.168.1.0/24
```

#### 🛣️ Filter Protocol/Port
- HTTP
```bash
port 80
```

- HTTPS
```bash
port 443
```

- DNS
```bash
udp port 53
```

- ICMP
```bash
icmp
```

## 🧠 Logic Operator
#### Capture Operator
- and
- or
- not

#### Display Filter
- &&  |  and
- ||  |  or
- !   |  not
