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
  - Human Users:
     - Some IAM principal types represent human users. You use these principal types for managing your employees' access to Google Cloud resources.
     - Principal types that represent human users include Google Accounts, Google groups, and federated identities in workforce identity pools.
  - Workloads:
