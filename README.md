# oc-admin
This GitHub repository is an introduction to Red Hat OpenShift Administration. It aims to teach the basics of cluster & project adminstration.
## Description
There are mainly two perspectives on the web console: Administrator and Developer. You can also have different accounts with different permissions that are managed by the Administrator using cluster role binding or project role binding (we might bring it up later in the tutorial). <br>
In this tutorial, we will be focusing on learning various capabilities and commands to administer OpenShift cluster. If you take a look at the following image, you can notice multiple tabs in the menu to the left. In this tutorial we will be focusing on the functionality of some of these features.
![admin](https://user-images.githubusercontent.com/36239840/95733956-eb292480-0c93-11eb-85ef-0c1f1bbb83fa.JPG)

The Administrator perspective in the OpenShift cluster is responsible for managing the cluster resources, users, and projects. In this navigation menu, some of the following features are:

- Home: See an overview dashboard of the cluster that summarizes the cluster status, alerts, breakdown of the cluster capacity by CPU, memory storage, and network utilization, some details about cluster and cluster inventory, and top consumers by category.
- Operators: Explore operators and install them for your cluster and projects from the OperatorHub and navigate through installed Operators.
- Builds: Manage build configurations, builds, and image streams.
- Pipelines: View your pipelines, tasks, and resources related to the cluster and projects, where you can view their status and access them for more details.

In this tutorial, we will focus on the rest of features & capabilities of the Administrator.
## Prerequisites
- Create your free IBM Cloud account at: https://ibm.biz/BdqQSg 
- OpenShift 4 Cluster on IBM Cloud:
  - URL: <will be provided soon>
  - key: <will be provided soon>
## Create Project
First thing, we will need to create a new project because we will be perfoming some administration tasks on a project level as well.<br><br>
1- Go to <b>Home &#8594; Projects</b> and click on <b>Create Project</b> button.<br>
![projects](https://user-images.githubusercontent.com/36239840/96359099-bdbef980-111f-11eb-93bd-33323dbe8d8f.JPG)<br><br>
2- Enter the name of project, you can also add Display name and description if you would like, then click <b>Create</b>.<br>
![my project](https://user-images.githubusercontent.com/36239840/96359121-0bd3fd00-1120-11eb-80aa-cc72a3f48e8e.JPG)<br><br>
3- You will be lead to the Project Dashboard page, which looks like the following.
![project overview](https://user-images.githubusercontent.com/36239840/96359161-52c1f280-1120-11eb-9016-959df95b3c46.JPG)


## User management
As an Administrator, you can manage users, groups and roles in the cluster and projects. If you expand the <b>User Management</b> tab you will notice that the list you have includes subjects -which are users, groups, and service accounts-, roles and role bindings.<br>
- Roles are used to grant access for Users & Groups on cluster-wide or project-scope by policy rules, and they can be referenced by a RoleBinding. Users and groups can be bound to multiple roles at the same time.<br>
- A role binding grants the permissions defined in a role to a user or group (set of users). It holds a list of subjects (users, groups, or service accounts), and a reference to the role being granted. A RoleBinding grants permissions within a specific namespace whereas a ClusterRoleBinding grants that access cluster-wide.<br>
When you first go to <b>Role Bindings</b>, you will notice that there are three types of role bindings: Cluster-wide rolebinding, Namespace rolebinding and System rolebinding.<br>
#### Step 1: Create a role.
In this step, we will create the role <b>project-manager</b> and this role gives access to read the pods in the project <b>my-first-project</b>.<br>
- We will be using one of the sample YAML templates that can be found to the right under "Samples", click on 'Try it' under 'Allow reading the resource in API group' and then change the name of the role from 'read-pods-within-ns' to 'project-manager'.
![role create](https://user-images.githubusercontent.com/36239840/96361525-83f9ed00-1137-11eb-93b7-d00c11f18bd0.JPG)
- Once created, you will be redirected to the role overview page.<br>
#### Step 2: Create Group
In this step, we will be creating a <b>project-management-group</b>.
- Go to <b>User Management &#8594; Group</b>, then 'Create Group'. You will be to <b>Create Group</b> page where you will have to enter the YAML Definition. Change the name of the group to <b>project-management-group</b> then add the list of names of the users you want to add (for example I added my username which I took from Users tab and added other users).<br>
![manager group](https://user-images.githubusercontent.com/36239840/96365504-127b6800-1152-11eb-829f-1fb394cae840.JPG)
- Then you will be directed to <b>project-management-group</b> group overview. You can notice at the bottom the new users added like the in following image.<br>
![users group](https://user-images.githubusercontent.com/36239840/96365547-6e45f100-1152-11eb-8fcb-7d0a6c5d1635.JPG)

#### Step 3: Create Role Binding
In this step, we will be creating a <b>project-management-group</b> and reference the role we created in the previous step.

- Click on <b>Role Bindings</b> and click on <b>Create Binding</b>.
![role overview](https://user-images.githubusercontent.com/36239840/96361662-aa6c5800-1138-11eb-9777-cb91b2d80705.JPG)

![role bindings](https://user-images.githubusercontent.com/36239840/96360209-02e92880-112c-11eb-986c-dfb48890f2a2.JPG)



<!--- Workloads
Workloads, Networking, and Storage: View and manage resources like deployment, secrets, and the pods in your project.

## Networking
- Networking: View and manage the services and routes of your applications.

## Storage
- Storage: View and manage the persistent volumes in your project.

## Monitoring
- Monitoring: View alerts and perform ad hoc Prometheus queries.

## Compute
- Compute: View and manage compute resources like nodes, machines, and autoscalers.


## Administration
- Administration: View settings related to cluster administration, like details about the cluster, namespaces, cluster updates, quotas, and Custom Resource Definitions (CRDs).

--->

## Resources
- <a href="https://kubernetes.io/docs/reference/access-authn-authz/rbac/#:~:text=A%20role%20binding%20grants%20the,user%20or%20set%20of%20users.&text=A%20RoleBinding%20grants%20permissions%20within,Role%20in%20the%20same%20namespace.">Kubernetes Documentation</a>
- <a href="https://docs.openshift.com/container-platform/3.9/admin_guide/manage_users.html">Managing Users on OpenShift</a>
- <a href="https://docs.openshift.com/container-platform/3.9/admin_guide/manage_rbac.html">Managing RBAC</a>
