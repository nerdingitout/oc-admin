## User management
As an Administrator, you can manage users, groups and roles in the cluster and projects. If you expand the <b>User Management</b> tab you will notice that the list you have includes subjects -which are users, groups, and service accounts-, roles and role bindings.<br>
- Roles are used to grant access for Users & Groups on cluster-wide or project-scope by policy rules, and they can be referenced by a RoleBinding. Users and groups can be bound to multiple roles at the same time.<br>
- A role binding grants the permissions defined in a role to a user or group (set of users). It holds a list of subjects (users, groups, or service accounts), and a reference to the role being granted. A RoleBinding grants permissions within a specific namespace whereas a ClusterRoleBinding grants that access cluster-wide.<br>
When you first go to <b>Role Bindings</b>, you will notice that there are three types of role bindings: Cluster-wide rolebinding, Namespace rolebinding and System rolebinding.<br>
#### Step 1: Create Group
In this step, we will be creating a <b>project-management-group</b>.
- Go to <b>User Management &#8594; Group</b>, then 'Create Group'. You will be to <b>Create Group</b> page where you will have to enter the YAML Definition. Change the name of the group to <b>project-management-group</b> then add the list of names of the users you want to add (for example I added my username which I took from Users tab and added other users).<br>
![manager group](https://user-images.githubusercontent.com/36239840/96365504-127b6800-1152-11eb-829f-1fb394cae840.JPG)
- Then you will be directed to <b>project-management-group</b> group overview. You can notice at the bottom the new users added like the in following image.<br>
![users group](https://user-images.githubusercontent.com/36239840/96365547-6e45f100-1152-11eb-8fcb-7d0a6c5d1635.JPG)

#### Step 2: Create a role.
In this step, we will create the role <b>project-manager</b> and this role gives access to read the pods in the project <b>my-first-project</b>.<br>
- We will be using one of the sample YAML templates that can be found to the right under "Samples", click on 'Try it' under 'Allow reading the resource in API group' and then change the name of the role from 'read-pods-within-ns' to 'project-manager'.
![role create](https://user-images.githubusercontent.com/36239840/96361525-83f9ed00-1137-11eb-93b7-d00c11f18bd0.JPG)
- Once created, you will be redirected to the role overview page.<br>

#### Step 3: Create Role Binding
In this step, we will be creating a <b>project-managers</b> RoleBinding and reference the role we created in the previous step.<br>

- Go to <b>User Management &#8594; Role Bindings</b>, and click on <b>Create Binding</b>.<br>
![role bindings](https://user-images.githubusercontent.com/36239840/96360209-02e92880-112c-11eb-986c-dfb48890f2a2.JPG)<br>

Binding Type will be <b>Namespace Role Binding</b>.
You can name it <b>project-managers</b> and pick the name of the namespace we are currently working on, in our case it's called <b>my-first-project</b>
Reference the role we created previously <b>project-manager</b>
For the subject, we will pick Group and write its name which is <b>project-management-group</b>, then click create.
![rolebinding](https://user-images.githubusercontent.com/36239840/96419871-c689fb00-1205-11eb-9605-6d8538074bf4.JPG)<br>
If you go to User Management → Role Bindings and search for project-managers in the filter you can find the newly created project-managers RoleBinding.<br>
![project managers search](https://user-images.githubusercontent.com/36239840/96420688-da822c80-1206-11eb-84e3-b7573e72c353.JPG)<br>
If you click on it and go to the YAML file, you can find its specifications and details. Spend some time to explore it, no need to make any changes to it.<br>
![RB YAML](https://user-images.githubusercontent.com/36239840/96420746-ed94fc80-1206-11eb-86dd-80cbf9466b29.JPG)<br>
You can also go to project-management-group and will find that the new RoleBinding has been successfully added to the group.<br>
![pm rb](https://user-images.githubusercontent.com/36239840/96420790-fc7baf00-1206-11eb-912d-9d834306d885.JPG)<br>

## Next Step: <a href="https://github.com/nerdingitout/oc-admin/blob/master/resources.md">Limiting Resources</a>
