This is a simplified example of ansible deployment to servers with both Linux and Windows environments.
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
