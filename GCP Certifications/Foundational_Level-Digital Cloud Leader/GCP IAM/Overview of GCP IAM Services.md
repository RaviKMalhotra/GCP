# GCP IAM Services
- GCP IAM Documentation Link - https://cloud.google.com/iam/docs/overview

# IAM Overview
- IAM is a tool to manage fine-grained authorization for Google Cloud.
- In other words, it lets you control who can do what on which resources.

## Access in Google Cloud

- Every action in Google Cloud requires certain permissions. 
- When someone tries to perform an action in Google Cloud—for example, create a VM instance or view a dataset—IAM first checks to see if they have the required permissions.
- If they don't, then IAM prevents them from performing the action.
- Giving someone permissions to a principal or an entitiy in IAM involves the following three components:
1. Principla: The identity of the person or system that you want to give permissions to
2. Role: The collection of permissions that you want to give to the principal
3. Resource: The Google Cloud resource that you want to let the desired pricnipal access

- To give the principal permission to access the resource, you grant them (principal) the role (collection of permissions) on the resource.
- You grant these roles using _an_allow policy_

## Principals
- In Google Cloud you control access for principals. 
- Principals represent one or more identities that have authenticated to Google Cloud.
- There are a variety of types of principals in IAM, but they can be divided into two broad categories:
  - **Human Users:**
     - Some IAM principal types represent human users. You use these principal types for managing your employees' access to Google Cloud resources.
     - Principal types that represent human users include Google Accounts, Google groups, and federated identities in workforce identity pools.
  - **Workloads:**
    - Some IAM principal types represent workloads.
    - You use these principal types when managing your workloads' access Google Cloud resources.
    - Principal types that represent workloads include service accounts and federated identities in a workload identity pool.
   
## Principal Types in Details
IAM supports the following types of principals:
- Google Accounts
- Google groups
- Google Workspace accounts
- Service accounts
- Cloud Identity domains
- allAuthenticatedUsers
- allUsers
- One or more federated identities in a workspace identity pool
- One or more federated identities in a workload identity pool
- A set of Google Kubernetes Engine pods
- Resource Manager principla ses


## Permissions and roles

- Permissions determine what operations are allowed on a resource.
- In IAM, permissions are typically represented in the form service.resource.verb.
- Often, permissions correspond one-to-one with REST API methods—for example, the resourcemanager.projects.list permission lets you list Resource Manager 
  projects.
- You can't directly grant permissions to a principal.
- Instead, you give principals permissions by granting them roles.
- Roles are collections of permissions.
- When you grant a role to a principal, you give that principal all of the permissions in that role.
- There are three types of roles:
  
**- Basic roles:**
  
  - **Highly permissive** roles that provide broad access to Google Cloud services.
  - These roles can be useful for testing purposes, but shouldn't be used in production environments.
  - Basic roles are highly premissive roles.
  - Caution: Basic roles contain thousands of permissions across all Google Cloud services.
  - In production environment, do not grant basic roles unless there is no alternatives.
  - Instead, grant the most limited predefined roles or custom roles that meet your needs.
  - The Basic roles in IAM are:
    - Admin (roles/admin)
    - Writer (roles/writer), and 
    - Reader (roles/reader)
   
**- Predefined roles:**

  - In addition to the basic roles, IAM provides additional predefined roles that give granular access to specific Google Cloud resources.
  - These roles are created and maintained by Google.
  - Google automatically updates their permissions as necessary, such as when Google Cloud adds new features or services.
  - You can grant multiple roles to the same user, at any level of the resource hierarchy.
  - For example, the same user can have the Compute Network Admin and Logs Viewer roles on a project, and also have the Pub/Sub Publisher role on a Pub/Sub 
    topic within that project. 
  - These Roles that are managed by Google Cloud services.
  - These roles contain the permissions needed to perform common tasks for each given service.
  - For example, the Pub/Sub Publisher role (roles/pubsub.publisher) provides access to publish messages to a Pub/Sub topic.

- **Custom roles:**
  
  - IAM also lets you create custom IAM roles.
  - Custom roles help you enforce the principle of least privilege, because they help to ensure that the principals in your 
    organization have only the permissions that they need.
  - Custom roles are user-defined, and allow you to bundle one or more supported permissions to meet your specific needs.
  - When you create a custom role, you must choose an **organization or project to create it in.**
  - You can then grant the custom role on the organization or project, as well as any resources within that organization or 
    project.
  - You can only create 300 per organization and 300 per project.
  - You can only grant a custom role within the project or organization in which you created it. You cannot grant custom roles on 
    other projects or organizations, or on resources within other projects or organizations.
  - Note: You cannot define custom roles at the folder level. If you need to use a custom role within a folder, define the custom 
    role at the organization level.
  - You create a custom role by combining one or more of the supported IAM permissions.
  - Roles that you create that contain only the permissions that you specify.
  - You have complete control over the permissions in these roles.
  - However, they have a higher maintenance burden than predefined roles.
  - And there's a limit to the number of custom roles that you can have in your project and in your organization.

## When to use Custom Roles
- In most situations, you should be able to use predefined roles instead of custom roles.
- Predefined roles are maintained by Google, and are updated automatically when new permissions, features, or services are added 
  to Google Cloud.
- In contrast, custom roles are not maintained by Google; when Google Cloud adds new permissions, features, or services, your 
  custom roles will not be updated automatically.
- However, you might want to create a custom role in the following situations:
    - A principal needs a permission, but each predefined role that includes that permission also includes permissions that the 
      principal doesn't need and shouldn't have.
    - You use role recommendations to replace overly permissive role grants with more appropriate role grants. In some cases, you        might receive a recommendation to create a custom role.
    - 
## IAM Policy Types
- Identity and Access Management (IAM) offers several types of policies to help you control which resources principals can access.
- IAM offers the following types of policies:
  - Allow policies
  - Deny policies
  - Principal access boundary (PAB) policies
 
## Allow Policies
- To grant principals access to resources, use IAM allow policies.
- Allow policies let you grant access to resources in Google Cloud.
- **Allow policies are made up of role bindings and metadata. **
- Role bindings specify which principals should have a certain role on the resource.
- Allow policies are always attached to a single resource.
- After you attach an allow policy to a resource, the policy is inherited by that resource's descendants.
- To create and apply an allow policy, you identify a resource that accepts allow policies, then use that resource's setIamPolicy 
  method to create the allow policy.
- All principals in the allow policy are granted the specified roles on the resource and all of the resource's descendants.
- Each resource can have only one allow policy attached to it.

## Deny policies
- Identity and Access Management (IAM) deny policies let you set guardrails on access to Google Cloud resources.
- With deny policies, you can define deny rules that prevent certain principals from using certain permissions, **regardless of the roles they're granted.**

This page provides an overview of deny policies and deny rules. To learn how to create and update deny policies, see Deny access to resources.

How deny policies work
Deny policies are made up of deny rules. Each deny rule specifies the following:

A set of principals that are denied permissions
The permissions that the principals are denied, or unable to use
Optional: The condition that must be true for the permission to be denied
When a principal is denied a permission, they can't do anything that requires that permission, regardless of the IAM roles they've been granted. This is because IAM always checks relevant deny policies before checking relevant allow policies. For details, see policy evaluation.

To specify where you want a deny policy to apply, you attach it to a project, folder, or organization. When a deny policy is attached to one of these resources, the principals in the policy can't use the specified permissions to access the resource, or any of the resource's descendants. To learn more about where you can attach a deny policy, see Attachment point on this page.

You can attach multiple deny policies to a single resource. This lets you create separate deny policies for different types of deny rules. For example, you could put compliance-related deny rules in one policy, then use another policy for other deny rules. Each deny policy is evaluated independently of all other deny policies.

Each resource can have up to 500 deny policies. Together, these deny policies can contain a total of 500 deny rules.
## Reader Role (roles/reader)
## Writer Role (roles/writer)
## Admin Role (roles/admin)
## How to Determine if a Permission is included in a basic, predefined or custom role.
