# Deploy node.js app in Google Cloud Run using Github Action

> This project demonstrate how to deploy node.js sample app in Google Cloud Run using Github Action

## 🚀 Features

- ✨ Google cloud acount setup
- ⚡ Cloud Run
- 🔒 How to deploy node app from local

## 🛠 Tech Stack

- Node.js
- Express
- Google Cloud(Cloud Run)

## 🧑‍💻 Local Setup
- Create free account in google cloud if not already have(for demo or testing)
- Login to Google cloud console, create a new project, or can use existing one
- Link billing account to project if not already linked
- Enable Artifact Registry, Cloud Run, Cloud Run Admin
- Create Repo in Artifact Registry
- Create a service account(with permission Cloud Run Admin, Artifact Registry Administrator, Service Account User), create a key, download the key in local
- Add GitHub Secrets to your repo:  Repo → Settings → Secrets and variables → Actions → New repository secret(Add all required env variable.) 
		PROJECT_ID = your project ID,
		GCP_SA_KEY = contents of key.json (JSON string),
		SERVICE = your desired service name (my-node-service),
		REGION = e.g. us-central1,
        GAR_NAME = <Artifact Registry Repo name>
- Create a simple node.js app with Dockerfile
- Create a .github/workflows/deploy.yml file in root of your node app
- Every time you push to main branch GitHub Actions will - Builds a Docker image of your app, Pushes it to Google Artifact Registry, Deploys it to Cloud Run (all these steps need to specify in deploy.yml file)
- When you push to GitHub, app will be deployed to Cloud Run
- After deployed you will get app url, run in browser if any issue add required permission.
- Don’t forget to delete all resources once done if using for demo/testing purpose.


## 📦 Installation

```bash
# Clone the repo
git clone https://github.com/rupachowrasia/node-gcp-cloud-run-deploy-with-github-action.git

# Move into the project directory
cd node-gcp-cloud-run-deploy-with-github-action

# Install dependencies
npm install

# Run the app
npm run start
