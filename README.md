# GitHub Actions RDP Access

This repository contains a GitHub Actions workflow that sets up Remote Desktop Protocol (RDP) access to a Windows runner using Ngrok for tunneling.

## How It Works

The workflow performs the following steps:

1. Sets up a Windows environment in GitHub Actions
2. Downloads and installs the latest Ngrok v3 client
3. Configures RDP (Remote Desktop Protocol) access on the machine
4. Creates a local user account for RDP login
5. Establishes a secure tunnel with Ngrok to allow remote RDP access

## Requirements

To use this workflow, you'll need:

1. A GitHub account with access to GitHub Actions
2. An Ngrok account and authtoken (free or paid)

## Setup Instructions

1. **Fork this repository** to your own GitHub account.

2. **Add your Ngrok authtoken as a secret:**

   - Go to your repository → Settings → Secrets and variables → Actions
   - Create a new repository secret named `NGROK_AUTH_TOKEN`
   - Paste your Ngrok authtoken as the value

3. **Run the workflow:**

   - Go to the Actions tab in your repository
   - Select the "CI" workflow
   - Click "Run workflow"

4. **Connect via RDP:**
   - When the workflow runs, look for the Ngrok public URL in the logs
   - Use an RDP client (like Windows Remote Desktop Connection) to connect
   - Login credentials:
     - Username: `zrdpadmin`
     - Password: `P@ssw0rd!`

## Important Notes

- The RDP session will only be active while the GitHub Actions workflow is running
- GitHub Actions has a timeout limit (6 hours maximum)
- This configuration uses Ngrok v3, which is required for newer Ngrok accounts
- For security reasons, consider changing the default password in the workflow

## Troubleshooting

If you encounter issues:

- Make sure your Ngrok authtoken is correctly added as a repository secret
- Check that your Ngrok account is active and functioning
- Review the workflow logs for any errors during setup

## Legal Notice

This project is for educational and testing purposes only. Please comply with GitHub's Terms of Service and Acceptable Use Policies.
