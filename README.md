# 🔄 Miro ↔ Jira Server (On-Prem) Integration via OAuth 2.0

This guide walks you through integrating **Miro** with **Jira Server (on-premises)** using **OAuth 2.0** to enable the **Jira Cards** functionality inside Miro boards.

> ⚠️ This setup applies to **Jira Server/Data Center**, not Jira Cloud.

---

## 📚 Reference Documentation

- Official Miro help guide (for Jira OAuth setup):  
  [Miro ↔ Jira OAuth Setup Guide](https://help.miro.com/hc/en-us/articles/27689156602514-Connect-to-Jira-using-OAuth-1-0-Updated)

---

## 🔧 Part I – Jira On-Prem: Application Link Setup

1. Open your browser and go to:

https://<your-jira-server>/plugins/servlet/applinks/listApplicationLinks



2. If the **"Application Links"** section is not deleted or broken, click into it.

3. Click **Create Link**:
- Select **Atlassian Product**
- Enter this **Application URL**:  
  ```
  https://miro.com
  ```
- Click **Continue**

4. In the **Link Applications** dialog:
- Application Name: `Miro Jira Card`
- Application Type: `Generic Application`
- Confirm:
  - "You are creating a link from": your Jira server URL
  - "To this application": `https://miro.com`
- Click **Continue**

5. Once the link is created, you'll see `miro.com` listed in the **Application Links** section.

---

## ⚙️ Part II – Miro Admin Console Settings

1. Log into the **Miro Admin Console**

2. Navigate to:



Apps & Integrations → Add Apps



3. Search for **Jira Cards**

4. Under **Manage Apps**, locate the **Jira integration** and click **Settings**

5. Configure the app with the following:

| Field         | Value                        |
|---------------|------------------------------|
| Auth Type     | `OAuth 2.0`                  |
| Jira URL      | `https://abc-uat-null.com/`  |
| Make Default  | ✅ (checked)                 |

6. Click **Connect**

---

## 🔁 OAuth Callback URL Setup

1. When you click **Connect**, Miro will generate a **Redirect URI** (OAuth callback):

Example: 
https://integration.miro.com/api/external-auth-oauth2.callback

Copy the URL and update in the Jira-Card setting in Attlassian. 

THen reutnr to miro and  click **Connect**, 


