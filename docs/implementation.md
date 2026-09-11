# Implementation

## Identity and policy

Server A was assigned a static internal address before AD DS and DNS were configured. It was promoted to a domain controller for the new `fl2026corp.com` forest. Active Directory Users and Computers showed domain users and a `RestrictedUsers` OU.

Group Policy Management showed separate scopes:

- An OU-linked policy applied user restrictions to the restricted account.
- Domain-linked policies applied the lab wallpaper and mapped a shared drive at logon.
- A second user outside the restricted OU was used as a comparison account.

The client demonstration showed the resulting wallpaper, mapped drive, and blocked administrative tools. The comparison account could open tools that were blocked for the restricted user.

![Active Directory users and OU](../evidence/ad-users-ou.png)

![Group Policy links and scope](../evidence/group-policy-links.png)

## Core network services

DNS Manager showed the domain forward lookup zone and host records for the lab systems. The client later resolved an external hostname during command-line validation.

DHCP was hosted separately on Server B. DHCP Manager showed an active IPv4 scope, address pool, issued lease, and scope options. The options identified Server A as the internal gateway and DNS server and included the domain name.

![DNS records](../evidence/dns-records.png)

![DHCP address pool](../evidence/dhcp-address-pool.png)

## Routing and services

Server A used a dual-NIC design. Routing and Remote Access was configured with NAT to connect the internal lab network to the external side. The RRAS console displayed the NAT interfaces and traffic counters.

I shared the `Shared` folder on Server A using Advanced Sharing. A domain-wide GPO mapped it as drive `S:` at logon, and the client could open the folder and see its files.

IIS on Server A hosted a small custom HTML page. The page was shown loading from Server B by addressing the Server A site directly.

![Shared-folder configuration](../evidence/share-configuration.png)

![Mapped drive on the domain client](../evidence/mapped-drive.png)

![IIS page accessed from another server](../evidence/iis-validation.png)
