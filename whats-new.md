---

copyright:
  years: 2019, 2020
lastupdated: "2020-07-21"

keywords: schematics activity tracker events, schematics events, schematics audit, schematics audit events, schematics audit logs

subcollection: schematics

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:download: .download}
{:preview: .preview}

# What's new in {{site.data.keyword.bpshort}}?
{: #new-in-schematics}

Learn about the latest changes to the {{site.data.keyword.bplong_notm}} service that are grouped by month.

## July 2020
{: #july-2020}

|Date|Description|
|-----|-----------|
|9 July 2020|<ul><li>**Stop apply support**: {{site.data.keyword.bplong_notm}} now supports stopping a {{site.data.keyword.bpshort}} apply action that currently runs against your workspace from the console and the API. For more information, see [Managing resource lifecycles](/docs/schematics?topic=schematics-manage-lifecycle) or use the [`DELETE /v1/workspaces/{id}/actions/{action_id}`](/apidocs/schematics#stop-a-schematics-apply-action) API. </li><li>**New {{site.data.keyword.bpshort}} locations**: You can now create {{site.data.keyword.bpshort}} workspaces in the Frankfurt or London location by using the location selector from the {{site.data.keyword.bpshort}} console or targeting the matching {{site.data.keyword.cloud_notm}} region from the CLI. For more information, see [Locations and service endpoints](/docs/schematics?topic=schematics-locations) and [Where is my data stored?](/docs/schematics?topic=schematics-secure-data#pi-location)</li></ul> |

## June 2020
{: #june-2020}

|Date|Description|
|-----|-----------|
|26 June 2020|**Ansible provisioner support**: You can now use the Ansible provisioner with {{site.data.keyword.bplong_notm}} to deploy software on {{site.data.keyword.cloud_notm}} resources or perform actions against your resources, such as shutting down a virtual server instance. For more information about how to use the Ansible provisioner, see the following blogs: <ul><li>[Discover best practice VPC configuration for application deployment](https://developer.ibm.com/articles/secure-vpc-access-with-a-bastion-host-and-terraform/)</li><li>[Learn about repeatable and reliable end-to-end app provisioning and configuration](https://developer.ibm.com/articles/application-deployment-with-redhat-ansible-and-ibm-cloud-schematics/). </li></ul>   |
|25 June 2020|**Version 1.8.0 of the {{site.data.keyword.cloud_notm}} Provider plug-in available**: The {{site.data.keyword.cloud_notm}} Provider plug-in for Terraform version 1.8.0 is now enabled in {{site.data.keyword.bplong_notm}}. For more information about the version, see the [release notes](https://github.com/IBM-Cloud/terraform-provider-ibm/releases/tag/v1.8.0){: external}. For an overview of supported {{site.data.keyword.cloud_notm}} resources and data sources, see the [{{site.data.keyword.cloud_notm}} Provider plug-in reference](/docs/terraform?topic=terraform-index-of-terraform-resources-and-data-sources).| 
|22 June 2020|**Upload Terraform templates as TAR files**: You can now provide your Terraform template by uploading a TAR file from your local machine. This feature is supported from the CLI or API. For more information, see the [`ibmcloud schematics workspace upload`](/docs/schematics?topic=schematics-schematics-cli-reference#schematics-workspace-upload) command or [`PUT /v1/workspaces/{id}/templates/{template_id}/template_repo_upload`](/apidocs/schematics#upload-a-tar-file-to-your-workspace) API.|

## May 2020
{: #may-2020}

|Date|Description|
|-----|-----------|
|8 May 2020|**New EU API endpoint**: You can now choose to create your {{site.data.keyword.bpshort}} workspaces in the US or Europe. Depending on the location that you choose, your {{site.data.keyword.bpshort}} actions run in either the US (`us-south` or `us-east`) or in Europe (`eu-de` or `eu-gb`). The location that you choose for your workspace is independent from the location where you want to provision your resources. For more information, see [Locations and service endpoints](/docs/schematics?topic=schematics-locations). |

## April 2020
{: #april-2020}

|Date|Description|
|-----|-----------|
|17 April 2020|<ul><li><strong>Terraform v0.12 support</strong>: You can now choose to run your infrastructure code with Terraform version 0.11 or 0.12. With Terraform version 0.12, the syntax for configuration files changed. Make sure that you use the syntax that is compatible with the Terraform version that you want to use. To migrate your Terraform configuration files from version 0.11 to version 0.12, see [Migrating your Terraform configuration files from version 0.11 to version 0.12](/docs/terraform?topic=terraform-setup_cli#tf-0.12-migration).  </li><li><strong>New workspace creation flow</strong>: The workspace creation flow is now [a two-step process](/docs/schematics?topic=schematics-workspace-setup#create-workspace). First, you create the workspace without connecting it to a GitHub or GitLab repository. Then, you add the details of your GitHub or GitLab repository, retrieve input variables, and let {{site.data.keyword.bpshort}} scan your Terraform configuration files for syntax errors. With the change of the workspace creation flow, [new workspace states](/docs/schematics?topic=schematics-workspace-setup#workspace-states) are introduced as well.</li></ul> |