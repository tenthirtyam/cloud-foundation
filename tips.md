# Tips


## Cloud Builder
### Reset VMaware Cloud Builder for reuse.
Login to the Cloud Builder virtual appliance via SSH and run the following:

	curl -X GET http://localhost:9080/bringup-app/bringup/sddcs/test/deleteAll

## SDDC Manager
### Set Workload Domains to use **medium** NSX-T Manager nodes.
Open the properties file.

`	root@m01-sddc01 [ /home/vcf ]#vi /opt/vmware/vcf/domainmanager/config/application-prod.properties`

   Add the following properties and save.

`	nsxt.manager.formfactor=medium
	nsxt.management.resources.validation.skip=true`

   Restart the Domain Manager service.
    
	root@m01-sddc01 [ /home/vcf ]# systemctl restart domainmanager
	root@m01-sddc01 [ /home/vcf ]# systemctl status domainmanager