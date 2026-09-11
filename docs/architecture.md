# Architecture

## Topology

The original walkthrough demonstrated three Windows systems on an internal network:

| Component | Services or behavior | Addressing shown |
| --- | --- | --- |
| Server A | AD DS, DNS, Group Policy management, RRAS/NAT, SMB share, IIS | Internal interface: `192.168.1.10`; a second adapter connected toward the external network |
| Server B | Domain member and DHCP server | `192.168.1.11`; gateway and DNS pointed to Server A |
| Domain client | Domain logon, GPO application, mapped drive, DHCP/DNS/routing validation | DHCP-assigned `192.168.1.100/24` |

The forest/domain name shown in the walkthrough was `fl2026corp.com`.

## Traffic and service relationships

1. The domain client and Server B used Server A for DNS.
2. Server B supplied DHCP leases and scope options to the internal network.
3. DHCP scope options pointed clients to Server A for their default gateway and DNS service.
4. Server A used two network adapters and RRAS/NAT to route traffic between the internal and external sides.
5. Active Directory and Group Policy on Server A centrally managed domain identities and client settings.
6. Server A exposed the shared folder and IIS site to other lab systems.

The internal network was `192.168.1.0/24`. The diagram shows service placement and network connections.

## Evidence

- [Static addressing on Server A](../evidence/static-ip.png)
- [DNS records for lab systems](../evidence/dns-records.png)
- [RRAS/NAT console](../evidence/rras-nat.png)
- [DHCP address pool](../evidence/dhcp-address-pool.png)
