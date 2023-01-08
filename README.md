# Kubernetes CKA Note

## Cluster Architecture, Installation & Configuration

> RBAC defines policies for users, groups, and processes by allowing or
disallowing access to manage API resources. Enabling and configuring
RBAC is mandatory for any organization with a strong emphasis on
security. 

> For the exam, you need to understand the involved RBAC API
resource types and how to create and configure them in different scenarios.

RBAC helps with implementing a variety of use cases:
- Establishing a system for users with different roles to access a set of
Kubernetes resources.

- Controlling processes running in a Pod and the operations they can
perform via the Kubernetes API.
- Limiting the visibility of certain resources per namespace.

![rbac](images/IMG_0079.PNG)

- Subject: The user or process that wants to access a resource.
- Resource: The Kubernetes API resource type e.g. a Deployment or
node.
- Verb: The operation that can be executed on the resource e.g. creating
a Pod, or deleting a Service.