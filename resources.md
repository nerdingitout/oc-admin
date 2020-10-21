## Limiting Resources
As an administrator, you can use quotas and limit ranges to set constraints to limit the number of objects or amount of compute resources that are used in your project. This can help you better manage and allocate resources across all projects, and ensure that no projects are using more than is appropriate for the cluster size.<br>
As a developer, you can also set requests and limits on compute resources at the pod and container level.<br>
The following sections help you understand how to manage your resource quota and limit ranges for your projects and pods.

### Resource Quotas
In this section, we will set limits to resources on the project level.</br>
Go to <b>Administration → Resource Quotas</b>, then click <b>Create Resource Quota</b>. You will be redirected to <b>Create Resource Quota</b> page.<br>
![resource quotas](https://user-images.githubusercontent.com/36239840/96685579-5f4b8280-138e-11eb-8f45-1559bc03f5f6.JPG)
Once created, you will be redirected to <b>project-quota</b> overview page, you will notice that there aren't any consumed resources, and that's because we haven't built or deployed applications on the project yet.<br>
![quota overview](https://user-images.githubusercontent.com/36239840/96686968-4d6adf00-1390-11eb-82be-438a340ecdce.JPG)

### Limit Ranges
n this section, we will set limits to resources on a pod level.<br>
Go to <b>Administration → Limit Ranges</b>, click <b>Create Limit Range</b>, you can specify the default memory and CPU container limits and requests, for now, you can just go with the default values.
![limit range](https://user-images.githubusercontent.com/36239840/96687148-8a36d600-1390-11eb-8449-eb54ffb86f7a.JPG)
