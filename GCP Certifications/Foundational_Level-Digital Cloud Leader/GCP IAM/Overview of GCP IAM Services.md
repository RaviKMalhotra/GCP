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
  
- Basic roles:
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

You can grant multiple roles to the same user, at any level of the resource hierarchy. For example, the same user can have the Compute Network Admin and Logs Viewer roles on a project, and also have the Pub/Sub Publisher role on a Pub/Sub topic within that project. 
  - Roles that are managed by Google Cloud services.
  - These roles contain the permissions needed to perform common tasks for each given service.
  - For example, the Pub/Sub Publisher role (roles/pubsub.publisher) provides access to publish messages to a Pub/Sub topic.

- Custom roles:
  - Roles that you create that contain only the permissions that you specify.
  - You have complete control over the permissions in these roles.
  - However, they have a higher maintenance burden than predefined roles.
  - And there's a limit to the number of custom roles that you can have in your project and in your organization.
    
 
## Reader Role (roles/reader)

## Writer Role (roles/writer)

## Admin Role (roles/admin)

## How to Determine if a Permission is included in a basic, predefined or custom role.
- 
