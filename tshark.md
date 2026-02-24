## Basics Flags
-i to select interface
-w to write out capture
-Y to filter
-T format output
-e field to print

##

## Fields
#### Time
can use -t <u: utc|a: local>
- frame.time
- frame.time_epoch
- frame.time_delta
- frame.time_relative

#### Json
- json.value.string

#### Normal
- ip.src

## Example use

### Extract to file
```bash
tshark -r <filename> -T fields -e frame.number -e ip.src -e ip.dst -e tcp.port -E header=y -E separator=, > analysis.csv
```

### Hunting DNS
```bash
tshark -r <filename> -Y "dns.flags.response == 0" -T fields -e dns.qry.name
```

### Top Talker
```bash
tshark -r <filename> -z conv,ip -q
```

## Tshark Live

### HTTP Monitoring
```bash
tshark -i <interface> -n -Y "http.request" -T fields -e ip.src -e http.post -e http.request.uri
```

```bash
tshark -r <filename> -i3 -Y "http.request.method || http.response" -T fields -e frame.time -e frame.time_delta -e tcp.stream -e http.request.method -e http.response.code -e http.user_agent -E separator="|"
```

### TCP Retransmission
```bash
tshark -1 <interface> -Y "tcp.analysis.retransmission"
```

### Grepping Data
```bash
tshark -r <filename> -Y "frame contains \"password\"" -V
```

### Grep JSON Data
```bash
tshark -r <filename> -Y "json and frame.number == 62" -T fields -e http.file_data | xxd -r -p | jq
```

### Grep Activity
```bash
tshark -r /tmp/WIRESHARK_LOGS/traffic-log_00001_20260224174005.pcupng -Y "json and http.request.method == POST" -V | grep -E "Arrival Time|Source Address|Key:|String value:"
```
