
This is a packer configuration that is designed to produce an Azure image. The image is created in the specified resource group in Azure.

The following variables are required to execute the Packer build:

| Name | Description |
|------|-------------|
| resource_group_name | Name of an existing Azure resource group in which the VM image will be created |
| app_name | Name of the image/application being created |
| azure_location | Region where the image will be created, and pull existing resources from |
| owner | Email address or other identifier of who or what generated the VM image |
| release | String defining the image release |

Add these to a `vars.json` file to run with the `packer build` command with `-var-file` or directly in the `centos.json` packer template.

A manual execution is like below:

	$ export ARM_SUBSCRIPTION_ID=<something>
	$ export ARM_TENANT_ID=<something>
	$ export ARM_CLIENT_ID=<something>
	$ export ARM_CLIENT_SECRET=<something>
	$ packer build -var-file=vars.json centos.json