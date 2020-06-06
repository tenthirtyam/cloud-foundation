# Tips


## Cloud Builder
### Reset VMaware Cloud Builder for reuse.
Login to the Cloud Builder virtual appliance via SSH and run the following:

	curl -X GET http://localhost:9080/bringup-app/bringup/sddcs/test/deleteAll

### Skip BGP Validation
Bypass the BGP validation by modifying the JSON input specification. 

The EBGP component need to be excluded from the run by adding a top level 
element `"excludedComponents"` in the JSON input specification:

`{
  "excludedComponents": ["EBGP"]
}`

* Obtain the current JSON file that is used for the Bring-up execution:
* Search for a file `/tmp/sddcspec-<uuid>.json`. If the JSON file is not found *(e.g. CloudBuilder reboot)*, generate a new JSON input specification using the XLS on the CloudBuilder VM console:

`cd /opt/vmware/sddc-support/cloud_admin_tools/JsonGenerator/
`

`/opt/vmware/sddc-support/sos --jsongenerator --jsongenerator-design vcf-ems --jsongenerator-input <path-to-xls>`

As a result the JSON input specificationis generated: 

`/opt/vmware/sddc-support/cloud_admin_tools/Resources/vcf-ems.json`

* Update the JSON input specification to include the correct data.
* Obtain the UUID of the failing execution:

Look inside the latest log file `/opt/vmware/bringup/logs/vcf-bringup-debug.log` and search for *“End of Orchestration with FAILURE for Execution ID <uuid>”*.

The `uuid` part of the above log is the ID of the run that you need to retry.

* Execute the following command on the Cloudbuilder VM to retry the execution with the modified JSON input specification:

` curl -X POST http://localhost:9080/bringup-app/bringup/sddcs/<uuid> -H "Content-Type: application/json" -d "@<path-to-json>"`

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