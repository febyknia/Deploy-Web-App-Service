
>👩🏻‍💻Feby 🗓 22 May 2025

# WEB APP SERVICE DEPLOY  
---
## **A. Introduction**

This project demonstrates how to deploy a **Python-based web application** (e.g. Flask or FastAPI) to **Microsoft Azure App Service**. This project aims to show how to create and deploy Python web applications to **Azure App Service**, a cloud platform that allows us to easily run web applications without having to manually manage infrastructure.
<img width="1020" alt="Screenshot 2025-05-22 022605" src="https://github.com/user-attachments/assets/ee3906c1-f933-48d4-8553-3fbcb5f60a99" />

## **B. Program Code**
Create a file `requirements.txt`:

```
flask
```

Create a file `runtime.txt`:

```
python-3.11
```

Log in to Azure

```bash
az login
```

Create Resource Group & App Service Plan

```bash
az group create --name MyResourceGroup --location "East US"

az appservice plan create --name MyPlan --resource-group MyResourceGroup --sku FREE
```

Create Web App

```bash
az webapp create --resource-group MyResourceGroup \
  --plan MyPlan \
  --name my-flask-app-demo \
  --runtime "PYTHON|3.12" \
  --deployment-local-git
```

Push Code to Azure

```bash
git init
git add .
git commit -m "initial commit"
git remote add azure https://<username>@my-flask-app-demo.scm.azurewebsites.net/my-flask-app-demo.git
git push azure master
```

Access Your Web App

```
https://my-flask-app-demo.azurewebsites.net
```

