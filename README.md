This is a simplified example of ansible deployment to servers with both Linux and Windows environments.

The whole process looks like this: A commit or merge on github triggers a webhook, which is sent to Jenkins. Jenkins runs the required ansible playbook depending on the environment. The example omits blue/green deployment, prod/stage deployment and so on to simplify the example.

To run a playbook from the terminal use:
```
ansible-playbook path/to/ansible/repo/playbooks/deploy/linux-service1/deploy.yml -e e_host=${HOST} -e e_service_name=${SERVICE_NAME} -e e_jenkins_job_name=${JENKINS_JOB_NAME} -e e_jenkins_build_number=${JENKINS_BOILD_NUMBER}
```

Project tree:
```
.
├── inventories
│   ├── group_vars
│   │   ├── linux
│   │   └── windows
│   └── main-hosts
├── playbooks
│   └── deploy
│       ├── linux-service1
│       │   └── deploy.yml
│       └── windows-service1
│           └── deploy.yml
└── roles
    └── extra_vars_check
        └── tasks
            └── main.yml
```
