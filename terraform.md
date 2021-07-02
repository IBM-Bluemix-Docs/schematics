---

copyright:
  years: 2021
lastupdated: "2021-05-19"

subcollection: schematics

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}


# Setting up Terraform for {{site.data.keyword.bplong_notm}} 
{: #terraform-setup}

Terraform on {{site.data.keyword.cloud}} enables predictable and consistent provisioning of {{site.data.keyword.cloud_notm}} services so that you can rapidly build complex, multi-tier cloud environments following Infrastructure as Code (IaC) principles. Similar to using the {{site.data.keyword.cloud_notm}} CLI or API and SDKs, you can automate the provisioning, update, and deletion of your {{site.data.keyword.bplong}} services instances by using HashiCorp Configuration Language (HCL).
{: shortdesc}

Looking for a managed Terraform on {{site.data.keyword.cloud_notm}} solution? Try out [{{site.data.keyword.bplong_notm}}](/docs/schematics?topic=schematics-getting-started). With {{site.data.keyword.bpshort}}, you can use the Terraform scripting language that you are familiar with, but you don't have to worry about setting up and maintaining the Terraform command line and the {{site.data.keyword.cloud_notm}} Provider plug-in. {{site.data.keyword.bpshort}} also provides pre-defined Terraform templates that you can easily install from the {{site.data.keyword.cloud_notm}} catalog.
{: tip}

Before you begin, make sure that you have the [required access](/docs/schematics?topic=schematics-access) to create and work with {{site.data.keyword.bplong_notm}} workspace. 

1. Follow the [Terraform on {{site.data.keyword.cloud_notm}} getting started tutorial](/docs/ibm-cloud-provider-for-terraform) to install the Terraform CLI and configure the {{site.data.keyword.cloud_notm}} Provider plug-in for Terraform. The plug-in abstracts the {{site.data.keyword.cloud_notm}} APIs that are used to provision, update, or delete {{site.data.keyword.bpshort}} resources. 

2. Create a Terraform configuration file that is named `main.tf`. In this file, you add the configuration to create a {{site.data.keyword.bpshort}} workspace by using HashiCorp Configuration Language (HCL).

   The following example use the `API Gateway Endpoint` and `API Gateway Endpoint Subscription` resources to create an endpoint for a given OpenAPI definition. To create a subscription it allows the user to input a single openAPI document or a directory of documents.
   Then creates the {{site.data.keyword.bplong_notm}} workspace `testmyworkspace` in the `default` resource group in your region. This workspace points to a Terraform template of your choice that requires the Terraform version `terraform_v0.13`. 
   
   ```terraform
   resource "ibm_schematics_workspace" "schematics_workspace" {
     name = "testmyworkspace"
     description = "Creating workspace and provisioning cloudant database instance ."
     location = "us-east"
     resource_group = "default"
     template_type = "terraform_v0.13"
    }

   ```
   {: codeblock}
   
3. Export your `IC_API_KEY`, `IAAS_CLASSIC_USERNAME`, and `IAAS_CLASSIC_API_KEY` in your local machine to access the credentials to create workspace and provisioning the instance. For more information, to create these keys, see [Creating and API Keys](https://cloud.ibm.com/docs/account?topic=account-userapikey#create_user_key).

   If the path environment variable for these keys are set, you can confirm your settings and ignore this step.
   {: note}

    ```
    $ export IC_API_KEY="<Provide your API key>”
    $ export IAAS_CLASSIC_USERNAME="<Provide your classic username>"
    $ export IAAS_CLASSIC_API_KEY="<Provide your classic API key>"
    ```
    {: pre}

4. Initialize the Terraform CLI. 

   ```
   terraform init
   ```
   {: pre}

5. Create a Terraform execution plan. The Terraform execution plan summarizes all the actions that need to be run to create the {{site.data.keyword.bpshort}} workspace in your account.

   ```
   terraform plan
   ```
   {: pre}

6. Create the {{site.data.keyword.bpshort}} workspace instance and IAM access policy in {{site.data.keyword.cloud_notm}}.

   ```
   terraform apply
   ```
   {: pre}

  For more information, about troubleshooting the terraform apply command errors, see [find the root cause of why Schematics apply is failing](/docs/schematics?topic=schematics-nullresource-errors).
  {: note}

7. From the [{{site.data.keyword.bpshort}} dashboard](https://cloud.ibm.com/schematics), check your `testmyworkspace` is created. And the resources are provisioned from the [{{site.data.keyword.bplong_notm}} resource list](https://cloud.ibm.com/resources){: external}.

8. Verify that the access policy is successfully assigned. For more information, see [Reviewing assigned access in the console](/docs/account?topic=account-assign-access-resources#review-your-access-console).

## What's next?
{: #terraform-setup-next}

Now that you successfully created your first {{site.data.keyword.bpshort}} workspace with Terraform on {{site.data.keyword.cloud_notm}}, you can choose between the following tasks: 

  - Learn how to create an [{{site.data.keyword.bplong_notm}} job](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/schematics_job){: external} resource to run your Terraform template in IBM Cloud.
  - To run Ansible playbooks in {{site.data.keyword.cloud_notm}} check out the [{{site.data.keyword.bplong_notm}} action](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/schematics_action){: external} resource.
  - Explore other supported Terraform resources and data sources for [{{site.data.keyword.bplong_notm}}](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/schematics_action){: external} or check-out other arguments and attributes that you can use for the Terraform resources that were used in this example.