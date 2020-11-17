# ado-agent

This project can be used to setup a docker hosted Azure DevOps agent. It will
start an Ubuntu Linux self-hosted agent.

---
## Prerequisites

+ Docker
+ docker-compose
+ git or git bash
+ Azure DevOps account

---

## Installation Steps:

+ Clone the ado-agent repository from here: [ado-agent][1]
    - ```bash
        git clone https://bcs5280@dev.azure.com/bcs5280/ado-tools/_git/ado-agent
        cd ado-agent
        ```

+ Edit the values in agent.env for your Azure DevOps account.

    - Use your own token from ADO -> User settings -> Personal access tokens.
The public access token needs the following custom scopes accessible by
choosing "Show all scopes".

    - Scopes:
        * Agent Pools (Read & manage)
        * Deployment Groups (Read & manage)

+ Start the agent:
    - ```bash
         export COMPOSE_FILE=development.yml
         docker-compose build --pull
         docker-compose up -d
    ```

[1]: https://dev.azure.com/bcs5280/ado-tools/_git/ado-agent "ado-agent"
