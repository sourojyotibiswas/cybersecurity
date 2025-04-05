# Customize Wireshark

- make another separate profile
- add display filter buttons
- add custom columns
- change pane 3 as packet diagram or packet bytes, and see field values
- set custom coloring rules or set any filter as color
- go to packet details and prepare anything as filter, also add any property as column

# Capture Network Traffic and Save to files

- go to `capture` ->
- - `input` -> `manage interfaces`[ shows diff interfaces to capture packets which you can remove some according to choise ]
- - `snaplen` is the length of bytes you wanna capture per packet
- - `output` -> select a destination folder and file name then set how much data you want to store per file and the limitation of no. of files [`use a ring buffer`] -> `start`

# Command Line Capture

- using `dumpcap`
- `dumpcap -h ->` help
- `dumpcap -D ->` shows lsit of all available interfaces
- `dumpcap -i <iface_number>` -> selecting the interface from which you want to capture files
- `dumpcap -i <iface_number> -w <file_path>` -> where you want to save the pcapng file
- `dumpcap -i <iface_number> -w <file_path> -b filesize:<each_pcapng_file_size(in_KB)> -b files:<number_of_files>` -> output with ring buffer

# Where do we Capture Network Traffic

# How to Filter Traffic

- language we use for capture filter is diff from display filters

## Types of Filters in Wireshark

1. **Capture Filters** – Applied before packet capture to limit the type of packets collected.
2. **Display Filters** – Applied after capturing to filter the packets displayed.

## Capture Filters

- **Filter DNS Traffic**:
  ```
  udp port 53
  ```
- **Filter ARP Traffic**:
  ```
  arp
  ```
- **Filter TCP Traffic**:
  ```
  tcp
  ```
- **Filter Traffic from a Specific IP**:
  ```
  host 192.168.1.1
  ```
- **Filter IPv6 Traffic**:
  ```
  ip6
  ```

## Display Filters

- **Filter by Protocol**:
  ```
  arp
  ```
  ```
  ip
  ```
- **Filter by IP Address (Source or Destination)**:
  ```
  ip.addr == 192.168.1.1
  ```
- **Filter by TCP Conversation (Between Two IPs)**:
  ```
  ip.addr == 192.168.1.1 && ip.addr == 10.0.0.2
  ```
- **Filter by TCP Traffic Only**:
  ```
  tcp
  ```
- **Filter by TCP Port (HTTP and HTTPS)**:
  ```
  tcp.port in {80 443 8080}
  ```
- **Filter by Specific IP and TCP**:
  ```
  (ip.addr == 192.168.1.1 && ip.addr == 10.0.0.2) && tcp
  ```
- **Filter by Excluding Traffic (NOT Filter)**:
  ```
  !arp
  ```
  ```
  !(arp || ipv6)
  ```
- **Filter by Packet Content (Case-Sensitive)**:
  ```
  frame contains "google"
  ```
- **Filter by Packet Content (Case-Insensitive Using Regex)**:
  ```
  frame matches "(?i)google"
  ```

## Additional Tips

- **Right-click filtering**: Right-click on any field in a packet and select "Apply as Filter" for quick filtering.
- **Progressively refining filters**: Start with a broad filter and refine by adding more conditions.
- **Avoid overly specific capture filters**: Capturing too little data may cause you to miss important packets for analysis.
