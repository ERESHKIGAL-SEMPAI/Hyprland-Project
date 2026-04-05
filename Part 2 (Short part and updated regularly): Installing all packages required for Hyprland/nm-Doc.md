# Documentation on Network Manager
[NetworkManager](https://fr.wikipedia.org/wiki/NetworkManager) is a tool designed to "simplify" the use of one or more networks on GNU/Linux or any other Unix-based system.
## Command-line tool : nmcli

### View connection status
```bash
$ nmcli general status # overall status
$ nmcli device status # nlist of interfaces
$ nmcli connection show # saved connections
```

### WI-FI
```bash
$ nmcli radio wifi on                          # Enables the Wi-Fi interface
$ nmcli device wifi list                       # scan networks
$ nmcli device wifi connect "SSID" password "mdp" # connects to the network
```

### Ethernet
```bash
$ nmcli connection add type ethernet ifname eth0 con-name "myconnection"
$ nmcli connection up "myconnection"
```

### Static IP
```bash
$ nmcli connection modify "ma-connexion"
   ipv4.method manual
   ipv4.addresses "192.168.1.100/24"
   ipv4.gateway "192.168.1.1"
   ipv4.dns "1.1.1.1,8.8.8.8"

$ nmcli connection up "myconnection"
```

### Enable / Disable a connection
```bash
$ nmcli connection up "myconnection"
$ nmcli connection down "myconnection"
$ nmcli device disconnect eth0
```

## Interactive Interface : nmtui
```bash
$ nmtui # It allows you to connect, modify, or delete connections via a simple ncurses interface.
```

## Troubleshooting
```bash
$ systemctl status NetworkManager          # check the service
$ journalctl -u NetworkManager -f          # real-time logs
$ nmcli device show eth0                   # interface details
$ ping -c 3 1.1.1.1                        # test connectivity
```
