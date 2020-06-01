# CREATE CONFIGURATION


## Enter Configuration

	configure

## Define the BGP ASN and Router ID

	set protocols bgp 65000 parameters router-id 192.168.3.1

## Define the ASN and BGP Neighbors

	set protocols bgp 65000 neighbor 172.27.11.2 remote-as 65001
	set protocols bgp 65000 neighbor 172.27.11.2 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.27.11.2 timers holdtime 12
	set protocols bgp 65000 neighbor 172.27.11.2 timers keepalive 4
	set protocols bgp 65000 neighbor 172.27.11.3 remote-as 65001
	set protocols bgp 65000 neighbor 172.27.11.3 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.27.11.3 timers holdtime 12
	set protocols bgp 65000 neighbor 172.27.11.3 timers keepalive 4
	set protocols bgp 65000 neighbor 172.27.12.2 remote-as 65001
	set protocols bgp 65000 neighbor 172.27.12.2 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.27.12.2 timers holdtime 12
	set protocols bgp 65000 neighbor 172.27.12.2 timers keepalive 4
	set protocols bgp 65000 neighbor 172.27.12.3 remote-as 65001
	set protocols bgp 65000 neighbor 172.27.12.3 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.27.12.3 timers holdtime 12
	set protocols bgp 65000 neighbor 172.27.12.3 timers keepalive 4

	set protocols bgp 65000 neighbor 172.37.11.2 remote-as 65001
	set protocols bgp 65000 neighbor 172.37.11.2 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.37.11.2 timers holdtime 12
	set protocols bgp 65000 neighbor 172.37.11.2 timers keepalive 4
	set protocols bgp 65000 neighbor 172.37.11.3 remote-as 65001
	set protocols bgp 65000 neighbor 172.37.11.3 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.37.11.3 timers holdtime 12
	set protocols bgp 65000 neighbor 172.37.11.3 timers keepalive 4
	set protocols bgp 65000 neighbor 172.37.12.2 remote-as 65001
	set protocols bgp 65000 neighbor 172.37.12.2 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.37.12.2 timers holdtime 12
	set protocols bgp 65000 neighbor 172.37.12.2 timers keepalive 4
	set protocols bgp 65000 neighbor 172.37.12.3 remote-as 65001
	set protocols bgp 65000 neighbor 172.37.12.3 password 'VMware1!'
	set protocols bgp 65000 neighbor 172.37.12.3 timers holdtime 12
	set protocols bgp 65000 neighbor 172.37.12.3 timers keepalive 4

	set protocols bgp 65000 neighbor 172.27.11.2 soft-reconfiguration inbound
	set protocols bgp 65000 neighbor 172.27.11.3 soft-reconfiguration inbound
	set protocols bgp 65000 neighbor 172.27.12.2 soft-reconfiguration inbound
	set protocols bgp 65000 neighbor 172.27.12.3 soft-reconfiguration inbound

	set protocols bgp 65000 neighbor 172.37.11.2 soft-reconfiguration inbound
	set protocols bgp 65000 neighbor 172.37.11.3 soft-reconfiguration inbound
	set protocols bgp 65000 neighbor 172.37.12.2 soft-reconfiguration inbound
	set protocols bgp 65000 neighbor 172.37.12.3 soft-reconfiguration inbound

## Advertise the Management Networks

	set protocols bgp 65000 network 172.16.11.0/24

## Commit and Save Configuration.

	commit ; save

# DELETE CONFIGURATION


	configure
	
	delete protocols bgp 65000 parameters router-id 192.168.3.1
	
	delete protocols bgp 65000 neighbor 172.27.11.2 remote-as 65001
	delete protocols bgp 65000 neighbor 172.27.11.2 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.27.11.2 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.27.11.2 timers keepalive 4
	delete protocols bgp 65000 neighbor 172.27.11.3 remote-as 65001
	delete protocols bgp 65000 neighbor 172.27.11.3 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.27.11.3 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.27.11.3 timers keepalive 4
	delete protocols bgp 65000 neighbor 172.27.12.2 remote-as 65001
	delete protocols bgp 65000 neighbor 172.27.12.2 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.27.12.2 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.27.12.2 timers keepalive 4
	delete protocols bgp 65000 neighbor 172.27.12.3 remote-as 65001
	delete protocols bgp 65000 neighbor 172.27.12.3 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.27.12.3 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.27.12.3 timers keepalive 4

	delete protocols bgp 65000 neighbor 172.37.11.2 remote-as 65001
	delete protocols bgp 65000 neighbor 172.37.11.2 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.37.11.2 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.37.11.2 timers keepalive 4
	delete protocols bgp 65000 neighbor 172.37.11.3 remote-as 65001
	delete protocols bgp 65000 neighbor 172.37.11.3 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.37.11.3 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.37.11.3 timers keepalive 4
	delete protocols bgp 65000 neighbor 172.37.12.2 remote-as 65001
	delete protocols bgp 65000 neighbor 172.37.12.2 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.37.12.2 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.37.12.2 timers keepalive 4
	delete protocols bgp 65000 neighbor 172.37.12.3 remote-as 65001
	delete protocols bgp 65000 neighbor 172.37.12.3 password 'VMware1!'
	delete protocols bgp 65000 neighbor 172.37.12.3 timers holdtime 12
	delete protocols bgp 65000 neighbor 172.37.12.3 timers keepalive 4

	delete protocols bgp 65000 neighbor 172.27.11.2 soft-reconfiguration
	delete protocols bgp 65000 neighbor 172.27.11.3 soft-reconfiguration
	delete protocols bgp 65000 neighbor 172.27.12.2 soft-reconfiguration
	delete protocols bgp 65000 neighbor 172.27.12.3 soft-reconfiguration

	delete protocols bgp 65000 neighbor 172.37.11.2 soft-reconfiguration
	delete protocols bgp 65000 neighbor 172.37.11.3 soft-reconfiguration
	delete protocols bgp 65000 neighbor 172.37.12.2 soft-reconfiguration
	delete protocols bgp 65000 neighbor 172.37.12.3 soft-reconfiguration

	commit ; save

# Troubleshooting

## Show BGP Neighboors and Advertised / Received Routes

	show ip bgp summary
	show ip bgp
	show ip bgp neighbors 172.27.11.2 advertised-routes
	show ip bgp neighbors 172.27.11.2 received-routes
	show ip bgp neighbors 172.27.12.2 advertised-routes
	show ip bgp neighbors 172.27.12.2 received-routes
	show ip bgp neighbors 172.37.11.2 advertised-routes
	show ip bgp neighbors 172.37.11.2 received-routes
	show ip bgp neighbors 172.37.12.2 advertised-routes
	show ip bgp neighbors 172.37.12.2 received-routes

# Help

See [EdgeRouter - Border Gateway Protocol (BGP)](https://help.ubnt.com/hc/en-us/articles/205222990-EdgeRouter-Border-Gateway-Protocol-BGP-)