## 🚀 Deployment Guide

Siren can be deployed seamlessly using GitHub Actions with Cloudflare Workers.

### ⚙️ CI/CD via GitHub Actions

1. **Create a KV Namespace**

   - Go to Cloudflare Dashboard → Workers → KV.
   - Create a new namespace named `SIREN`.

2. **Configure `wrangler.toml`**

   - Add the KV namespace to your config file:
     ```toml
     [[kv_namespaces]]
     binding = "SIREN"
     id = "YOUR_KV_NAMESPACE_ID"
     ```

3. **Generate API Token**

   - [Create an API Token](https://developers.cloudflare.com/fundamentals/api/get-started/create-token/) with:
     - Permissions: Workers & KV Storage

4. **Set GitHub Repository Secret**

   - Navigate to: GitHub → Your Repo → Settings → Secrets and variables → Actions
   - Add a new secret:
     - Name: `CLOUDFLARE_API_TOKEN`
     - Value: Your API token

5. **Enable GitHub Actions**

   - Open the **Actions** tab on GitHub.
   - Enable workflows if prompted.

6. **Trigger Deployment**

   - Push any commit or manually trigger the deployment workflow.

7. **Access Your Siren Instance**
   - Visit: `https://<YOUR-WORKERS-SUBDOMAIN>.workers.dev`

8. **U must edit**
