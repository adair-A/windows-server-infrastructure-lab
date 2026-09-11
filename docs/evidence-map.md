# Original evidence map

Source (kept outside this repository): `OS3 FinalWindowsServerfinaltranscript.srt` and timestamp-matched frames from `OS3 Final.mp4`.

| Feature | Timestamp | What the original walkthrough shows | Video confirmation | Selected evidence |
| --- | --- | --- | --- | --- |
| Lab roles | 00:00:09–00:00:41 | Two Windows servers and one domain client; service split described | Confirmed | [Architecture diagram](../diagrams/architecture.svg) |
| Static addressing | 00:00:49–00:01:17 | Server A internal IPv4 and DNS settings | Confirmed | [static-ip.png](../evidence/static-ip.png) |
| AD DS / forest | 00:01:50–00:02:22 | Domain-controller promotion described; domain visible in ADUC | Confirmed | [ad-users-ou.png](../evidence/ad-users-ou.png) |
| Users and OU | 00:02:19–00:03:02 | Domain users and `RestrictedUsers` OU | Confirmed | [ad-users-ou.png](../evidence/ad-users-ou.png) |
| Group Policy scope | 00:03:03–00:04:14 | OU-linked restrictions plus domain-wide wallpaper and drive mapping | Confirmed | [group-policy-links.png](../evidence/group-policy-links.png) |
| Applied GPO behavior | 00:04:24–00:06:13 | Restricted-user logon, wallpaper, mapped drive, blocked tools; comparison user described later | Confirmed | [mapped-drive.png](../evidence/mapped-drive.png), [registry-restriction.png](../evidence/registry-restriction.png) |
| DNS | 00:06:47–00:08:52 | DNS Manager zones and registered lab systems | Confirmed | [dns-records.png](../evidence/dns-records.png) |
| RRAS/NAT | 00:08:52–00:10:13 | Dual-NIC NAT interfaces and traffic in RRAS | Confirmed | [rras-nat.png](../evidence/rras-nat.png) |
| Client network validation | 00:11:47–00:12:46 | `ipconfig /all`, external ping, and hostname resolution | Confirmed | [client-ipconfig.png](../evidence/client-ipconfig.png), [dns-ping-validation.png](../evidence/dns-ping-validation.png) |
| DHCP | 00:12:51–00:15:19 | Scope, pool, lease, DNS/gateway options, and Server B addressing | Confirmed | [dhcp-address-pool.png](../evidence/dhcp-address-pool.png) |
| SMB share | 00:15:20–00:16:17 | Shared folder and Advanced Sharing configuration | Confirmed | [share-configuration.png](../evidence/share-configuration.png) |
| IIS | 00:16:39–00:19:51 | Custom site on Server A; inconsistent client attempt; successful load from Server B | Confirmed with limitation | [iis-validation.png](../evidence/iis-validation.png) |
