# N8N Selfhosted Installation
Discover how to efficiently set up a virtual private server (VPS) using Hetzner Cloud and deploy N8N using Coolify, an intuitive GUI Docker manager. This guide provides step-by-step instructions to streamline your setup process.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/b5fefccf-a4cc-4614-a954-1ba67a8f2221.png)
## Step 1: Order a VPS from Hetzner Cloud
- Begin by ordering a VPS, specifically the **CAX11** model, from Hetzner Cloud. Utilize this [referral link](https://swiy.co/vps) to enjoy a 5-month free VPS offer. The average monthly cost post-offer is approximately $3.6.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/7a7d7ab6-174e-40a9-bf88-c21a2b7113be.png)
## Step 2: Select Your Server OS
- Choose **Docker CE** as your server operating system, which can be found in the APPS section.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/2837a903-7b21-445b-a2ff-728aedcbe9a4.png)
## Step 3: Install Coolify
- Once your server is ready, access the console and execute the following command:
```
  curl -fsSL https://cdn.coollabs.io/coolify/install.sh | bash 
```
After the installation, a dashboard URL like `http://xx.xx.xx.xx:8000` will be displayed. Access this URL to set up your Coolify account.
## Step 4: Create Database Containers
- Effortlessly create Postgres & Redis Containers. Coolify manages the entire setup, so no additional configuration is necessary.**Note:** Ensure your databases remain private and internal. Do not make them public.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/207194b7-4341-43da-9928-eeff7534fad0.png)
## Step 5: Configure N8N Application
- Add a new resource and select an application based on **Docker Compose**.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/8e767c61-93dc-4795-975b-42506bf3a336.png)
- Insert the following Docker Compose configuration.
```
  services:
  n8n:
    image: 'docker.n8n.io/n8nio/n8n:ai-beta'
    environment:
      - SERVICE_FQDN_N8N
      - 'N8N_EDITOR_BASE_URL=${SERVICE_FQDN_N8N}'
      - 'WEBHOOK_URL=${SERVICE_FQDN_N8N}'
      - 'N8N_HOST=${SERVICE_DOMAIN_N8N}'
      - 'GENERIC_TIMEZONE="Europe/Berlin"'
      - 'TZ="Europe/Berlin"'
      - 'DB_POSTGRESDB_DATABASE=${DB_POSTGRESDB_DATABASE}'
      - 'DB_POSTGRESDB_HOST=${DB_POSTGRESDB_HOST}'
      - 'DB_POSTGRESDB_PASSWORD=${DB_POSTGRESDB_PASSWORD}'
      - 'DB_POSTGRESDB_PORT=${DB_POSTGRESDB_PORT}'
      - 'DB_POSTGRESDB_SCHEMA=${DB_POSTGRESDB_SCHEMA}'
      - 'DB_POSTGRESDB_USER=${DB_POSTGRESDB_USER}'
      - 'DB_TYPE=${DB_TYPE}'
      - 'EXECUTIONS_MODE=${EXECUTIONS_MODE}'
      - 'N8N_LOG_LEVEL=${N8N_LOG_LEVEL}'
      - 'N8N_METRICS=${N8N_METRICS}'
      - 'QUEUE_BULL_PREFIX=${QUEUE_BULL_PREFIX}'
      - 'QUEUE_BULL_REDIS_DB=${QUEUE_BULL_REDIS_DB}'
      - 'QUEUE_BULL_REDIS_HOST=${QUEUE_BULL_REDIS_HOST}'
      - 'QUEUE_BULL_REDIS_PASSWORD=${QUEUE_BULL_REDIS_PASSWORD}'
      - 'QUEUE_BULL_REDIS_PORT=${QUEUE_BULL_REDIS_PORT}'
      - 'N8N_DIAGNOSTICS_ENABLED=${N8N_DIAGNOSTICS_ENABLED}'
      - 'N8N_VERSION_NOTIFICATIONS_ENABLED=${N8N_VERSION_NOTIFICATIONS_ENABLED}'
      - 'N8N_TEMPLATES_ENABLED=${N8N_TEMPLATES_ENABLED}'
      - 'EXTERNAL_FRONTEND_HOOKS_URLS=${EXTERNAL_FRONTEND_HOOKS_URLS}'
      - 'N8N_DIAGNOSTICS_CONFIG_FRONTEND=${N8N_DIAGNOSTICS_CONFIG_FRONTEND}'
      - 'N8N_DIAGNOSTICS_CONFIG_BACKEND=${N8N_DIAGNOSTICS_CONFIG_BACKEND}'
      - 'N8N_ONBOARDING_FLOW_DISABLED=${N8N_ONBOARDING_FLOW_DISABLED}'
    volumes:
      - 'n8n-data:/home/node/' 
```
## Step 6: Set Environment Variables
- After creating the container, navigate to the **Environment Variables** section and enable **Developer Mode** to view and edit all configurable options.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/cc77452a-228d-4509-be35-d5f0d7763c5c.png)
- Utilize the URLs copied from the Postgres & Redis setup to configure the respective environment variables.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/a9ef582d-bc8a-4fa7-95cd-f5fc5f0082f8.png)
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/1a3f1279-e81d-4bfd-921b-8bdff6b4391b.png)
final Env config will look like this example:
```tsx
DB_POSTGRESDB_DATABASE=postgres
DB_POSTGRESDB_HOST=k4o4wwk
DB_POSTGRESDB_PASSWORD=Ka36bNFBdHUtmvs3ZPKk2iWx8N
DB_POSTGRESDB_PORT=5432
DB_POSTGRESDB_SCHEMA=public
DB_POSTGRESDB_USER=postgres
DB_TYPE=postgresdb
EXECUTIONS_MODE=queue
EXTERNAL_FRONTEND_HOOKS_URLS=
N8N_DIAGNOSTICS_CONFIG_BACKEND=false
N8N_DIAGNOSTICS_CONFIG_FRONTEND=false
N8N_DIAGNOSTICS_ENABLED=false
N8N_LOG_LEVEL=verbose
N8N_METRICS=false
N8N_ONBOARDING_FLOW_DISABLED=true
N8N_TEMPLATES_ENABLED=true
N8N_VERSION_NOTIFICATIONS_ENABLED=true
QUEUE_BULL_PREFIX=N8N_
QUEUE_BULL_REDIS_DB=0
QUEUE_BULL_REDIS_HOST=xsksg8s
QUEUE_BULL_REDIS_PASSWORD=Si8oa82GpHLS44lw8Ssm
QUEUE_BULL_REDIS_PORT=6379
SERVICE_DOMAIN_N8N=rmQirts0xAxkgDAd
SERVICE_FQDN_N8N=http://n8n-n4cw2c.65.19.17.197.sslip.io
```
## Final Steps: Deploy and Enjoy N8N
- Once you have filled in your configurations, click **Save** and then **Deploy**.
![image](https://files.notice.studio/workspaces/8c8c2caf-fbf0-4d85-bcb7-8fb67110ece6/ba1c6241-5c8c-467e-a674-06db029f4d5d.png)
- Upon successful deployment, you can start using N8N. If it's your first time, you'll be directed to the registration page to set up an admin account.
## Additional Configurations and Tips
- This tutorial does not cover setting up a Cloudflare account, CNAME, Firewall, Webhooks, or Hetzner Firewall rules. These are essential for a secure and fully functional setup.
- You can rescale your server in the near future once your usage excused.
- To support N8N Project, you can also use their [cloud version](https://n8n.io/pricing/). which is hassle free and everything managed by them.
- If you need any help with N8N fixing and building workflows, use our GPT model made for N8N Assistance [here](https://swiy.co/n8n).
For more detailed information on environment variables and advanced configurations, refer to the [N8N Documentation](https://docs.n8n.io/hosting/environment-variables/environment-variables/).
