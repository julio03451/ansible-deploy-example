This is a simplified example of ansible deployment to servers with both Linux and Windows environments.

The whole process looks like this: A commit or merge on github triggers a webhook, which is sent to Jenkins. Jenkins runs the required ansible playbook depending on the environment. The example omits blue/green deployment, prod/stage deployment and so on to simplify the example.

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
