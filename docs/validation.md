# Validation

These checks were recorded in the original lab walkthrough.

| Capability | Validation method | Supported result |
| --- | --- | --- |
| Domain identity | Logged into the Windows client with two domain accounts | Both accounts were usable; the accounts received different policy behavior based on scope |
| OU-scoped Group Policy | Attempted restricted tools as the restricted user | Registry Editor displayed a message that editing was disabled by the administrator; other restrictions were demonstrated in the walkthrough |
| Domain-wide Group Policy | Inspected the signed-in desktop and File Explorer | Configured wallpaper and mapped shared drive appeared for the domain user |
| DHCP | Ran `ipconfig /all` on the client, then inspected DHCP Manager | Client showed a lease and the expected DHCP/DNS/gateway relationships; DHCP Manager showed the scope and lease |
| DNS | Used a hostname-based ping during client command-line testing | The hostname resolved and returned replies in the recorded test |
| NAT/routing | Used ping from the internal client and inspected RRAS/NAT | External connectivity returned replies; RRAS showed the configured interfaces and traffic |
| File sharing | Opened the mapped drive on the domain client | Shared files were visible through the mapped location |
| IIS | Opened the Server A site from Server B | The custom page loaded from another lab system |

## Representative proof

### Client addressing

![Client ipconfig output](../evidence/client-ipconfig.png)

The client received `192.168.1.100/24` from DHCP server `192.168.1.11`, with `192.168.1.10` as both gateway and DNS server.

### DNS and routed connectivity

![Ping and DNS validation](../evidence/dns-ping-validation.png)

### Restricted-user behavior

![Registry Editor blocked by administrator policy](../evidence/registry-restriction.png)

### Evidence limitation

The IIS site did not load reliably during one client attempt; the page later loaded from Server B. The recording did not establish why the client attempt failed.
