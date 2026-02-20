## basic important Flags
-I if monitor mode
-p if turn of Promiscuous mode
-f to filter
-s to snaplen(max data cap)
-a stop condition like (files, filesize, packet, duration)
-b ring buffer
-B buffered in ram


## Example Command

### Normal Capture
dumpcap -i <interface> -w <path/filename> -b files:<Num> -b filesize:<Num>
~/add -p to turn of promiscuous mode

### Monitor Capture
dumpcap -I <phy0.mon> -w <path/filename> -b files:<Num> -b filesize:<Num>

### Header only use snap lenght
dumpcap -i <interface> -s 96 -w <path/filename>
