# oc-admin
This GitHub repository is an introduction to Red Hat OpenShift Administration. It aims to teach the basics of cluster & project adminstration.
## Content
- [Description](##Description)
- [Prerequisites](##Prerequisites)
- [User management](https://github.com/nerdingitout/oc-admin/blob/master/user-manage.md)
- [Limiting Resources](https://github.com/nerdingitout/oc-admin/blob/master/resources.md)
- [Resources](##Resources)
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
  
### Next Step: <a href= "https://github.com/nerdingitout/oc-admin/blob/master/user-manage.md">User management</a>


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
