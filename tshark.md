## Basics Flags
-i to select interface
-w to write out capture
-Y to filter
-T format output
-e field to print

## Example use

### Extract to file
`tshark -r <filename> -T fields -e frame.number -e ip.src -e ip.dst -e tcp.port -E header=y -E separator=, > analysis.csv`

### Hunting DNS
`tshark -r <filename> -Y "dns.flags.response == 0" -T fields -e dns.qry.name`

### Top Talker
`tshark -r <filename> -z conv,ip -q`

## Tshark Live

### HTTP Monitoring
`tshark -i <interface> -n -Y "http.request" -T fields -e ip.src -e http.post -e http.request.uri`

### TCP Retransmission
`tshark -1 <interface> -Y "tcp.analysis.retransmission"`

### Grepping Data
`tshark -r <filename> -Y "frame contains \"password\"" -V` 
