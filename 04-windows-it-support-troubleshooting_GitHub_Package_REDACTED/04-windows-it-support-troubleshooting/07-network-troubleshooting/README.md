# 07 — Network Configuration & Connectivity Tests

## Objective
Inspect the VM's network configuration and test gateway, public IP, and DNS connectivity.

## Commands used
```powershell
ipconfig /all
Get-DnsClientServerAddress -AddressFamily IPv4
ping 10.0.2.2
ping 8.8.8.8
nslookup google.com
```

## Observed configuration
| Parameter | Value in latest capture |
|---|---|
| Adapter | Intel(R) PRO/1000 MT Desktop Adapter |
| DHCP | Enabled |
| IPv4 | 10.0.2.15 |
| Subnet mask | 255.255.255.0 |
| Default gateway | 10.0.2.2 |
| DHCP server | 10.0.2.2 |
| DNS server | 192.168.100.1 |

The `10.0.2.15` address and `10.0.2.2` gateway are consistent with the observed VirtualBox NAT configuration.

## Test results
| Test | Observed result |
|---|---|
| Ping gateway `10.0.2.2` | 3 replies received, 0% loss |
| Ping public IP `8.8.8.8` | 4 replies received, 0% loss; average about 22 ms |
| `nslookup google.com` | Successful; IPv4 and IPv6 addresses returned |
| DNS client configuration | `192.168.100.1` in the latest capture |

## DNS discrepancy to investigate
An earlier `ipconfig /all` capture showed DNS `192.168.1.1`. Later `ipconfig /all`, `Get-DnsClientServerAddress`, and `nslookup` showed `192.168.100.1`. The cause has not been established. No manual DNS changes have been made.

## Current conclusion
Basic gateway connectivity, public IP connectivity, and DNS resolution were successful at the time of testing.

## Next exercise — pending
A controlled DNS failure simulation and recovery exercise is planned but has **not** been performed. Do not describe it as completed until the VM-only test is carried out and evidence is captured.


## Privacy treatment of evidence
The published screenshots conceal the adapter MAC address, IPv6 link-local address, DHCPv6 IAID/DUID identifiers, and private DNS server address. The lab IPv4 address, subnet, and VirtualBox gateway remain visible because they are useful evidence for the NAT connectivity exercise.
