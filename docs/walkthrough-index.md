# Walkthrough index

Video: [Windows Server Infrastructure Lab walkthrough](https://youtu.be/TKzkftNywjQ)

The transcript and timestamp-matched source frames are kept outside this repository.

| Feature | Timestamp | What I did | Evidence |
| --- | --- | --- | --- |
| Lab roles | [00:00:09–00:00:41](https://youtu.be/TKzkftNywjQ?t=9) | Described the service split across two Windows servers and one domain client | [Architecture diagram](../diagrams/architecture.svg) |
| Static addressing | [00:00:49–00:01:17](https://youtu.be/TKzkftNywjQ?t=49) | Reviewed Server A's internal IPv4 and DNS settings | [static-ip.png](../evidence/static-ip.png) |
| AD DS / forest | [00:01:50–00:02:22](https://youtu.be/TKzkftNywjQ?t=110) | Described the domain-controller promotion and reviewed the domain in ADUC | [ad-users-ou.png](../evidence/ad-users-ou.png) |
| Users and OU | [00:02:19–00:03:02](https://youtu.be/TKzkftNywjQ?t=139) | Reviewed the domain users and `RestrictedUsers` OU | [ad-users-ou.png](../evidence/ad-users-ou.png) |
| Group Policy scope | [00:03:03–00:04:14](https://youtu.be/TKzkftNywjQ?t=183) | Reviewed the OU-linked restrictions and domain-wide wallpaper and drive-mapping policies | [group-policy-links.png](../evidence/group-policy-links.png) |
| Applied GPO behavior | [00:04:24–00:06:13](https://youtu.be/TKzkftNywjQ?t=264) | Tested the restricted-user logon, wallpaper, mapped drive, and blocked tools; described the comparison user later | [mapped-drive.png](../evidence/mapped-drive.png), [registry-restriction.png](../evidence/registry-restriction.png) |
| DNS | [00:06:47–00:08:52](https://youtu.be/TKzkftNywjQ?t=407) | Reviewed the DNS Manager zones and registered lab systems | [dns-records.png](../evidence/dns-records.png) |
| RRAS/NAT | [00:08:52–00:10:13](https://youtu.be/TKzkftNywjQ?t=532) | Reviewed the dual-NIC NAT interfaces and traffic in RRAS | [rras-nat.png](../evidence/rras-nat.png) |
| Client network validation | [00:11:47–00:12:46](https://youtu.be/TKzkftNywjQ?t=707) | Ran `ipconfig /all`, pinged an external address, and tested hostname resolution | [client-ipconfig.png](../evidence/client-ipconfig.png), [dns-ping-validation.png](../evidence/dns-ping-validation.png) |
| DHCP | [00:12:51–00:15:19](https://youtu.be/TKzkftNywjQ?t=771) | Reviewed the scope, pool, lease, DNS/gateway options, and Server B addressing | [dhcp-address-pool.png](../evidence/dhcp-address-pool.png) |
| SMB share | [00:15:20–00:16:17](https://youtu.be/TKzkftNywjQ?t=920) | Reviewed the shared folder and Advanced Sharing configuration | [share-configuration.png](../evidence/share-configuration.png) |
| IIS | [00:16:39–00:19:51](https://youtu.be/TKzkftNywjQ?t=999) | Reviewed the custom site on Server A; the client attempt was inconsistent, but I loaded the page from Server B | [iis-validation.png](../evidence/iis-validation.png) |
