
This is a packer configuration that is designed to produce an Azure image with vault and consul installed. The image is created in the specified resource group in Azure.

The following variables are required to execute the Packer build:

| Name | Description |
|------|-------------|
| azure_resource_group_name | Name of an existing Azure resource group in which the VM image will be created. |
| consul_zip | Path to a ZIP file containing the desired Consul Enterprise release. |
| consul_version | String matching the version of Consul deployed in the image. |
| vault_zip | Path to a ZIP file containing the desired Vault Enterprise release. |
| vault_version | String matching the version of Vault deployed in the image. |
| owner | Email address or other identifier of who or what generated the VM image. |
| release | String defining the image release. |

Add these to a `vars.json` file to run with the `packer build` command with `-var-file` or directly in the `vault-consul.json` packer template.

A manual execution is like below:

	$ export ARM_SUBSCRIPTION_ID=<something>
	$ export ARM_TENANT_ID=<something>
	$ export ARM_CLIENT_ID=<something>
	$ export ARM_CLIENT_SECRET=<something>
	$ packer build vault-consul.json