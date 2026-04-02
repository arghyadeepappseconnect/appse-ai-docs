---
title: "Teamwork"
slug: /app-integrations/teamwork/
---

Teamwork is a powerful project management platform built for teams to plan, track, and deliver work efficiently. Integrating Teamwork into appse ai enables you to build powerful agents and workflows with real-time project management capabilities including task creation, milestone tracking, people management, and much more.

---

## Set Up Credential

:::info

Before you create a credential for Teamwork using appse ai, ensure you have a Teamwork account and have registered an app in the Teamwork Developer Portal to obtain your Client ID and Client Secret.

:::

### Required Fields

You'll be asked to fill in the following details:

| Field           | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| Connection Name | A name to help you identify this connection                                 |
| Client ID       | Your OAuth 2.0 Client ID generated from the Teamwork Developer Portal       |
| Client Secret   | Your OAuth 2.0 Client Secret generated from the Teamwork Developer Portal   |

---

### Step-by-Step Guide

#### 1. Open the Credential Form

Click **Select a Credential** and choose **Teamwork** from the application list.

<img src="/img/credentials/teamwork/create-new-cred-teamwork.png" alt="appse ai Teamwork Select Credential" width="700"/>

<br/>

This opens the Teamwork credential form. Add your **Connection Name**.

<img src="/img/credentials/teamwork/configure-credientials.png" alt="appse ai Teamwork Connection Name" width="700"/>

#### 2. Navigate to the Teamwork Developer Portal

Go to your Teamwork Developer Portal by visiting:
```
https://{yourSiteName}.teamwork.com/developer
```


Sign in with your Teamwork account credentials.


<img src="/img/credentials/teamwork/teamwork-login.png" alt="appse ai Teamwork Connection Name" width="700"/>

#### 3. Create a New App

Once inside the Developer Portal, click **Create Your First App** (or **Create New App** if you already have existing apps).

Fill in the required details:

- **Name** — A name for your app. Example: `appse ai Integration`
- **Description** — A short description of what the app does.
- **Product(s)** — Select **Teamwork Projects**.

Click **Save** to create the app.

<img src="/img/credentials/teamwork/click-create-app-teamwork.png" alt="appse ai Teamwork Create App" width="700"/>

<img src="/img/credentials/teamwork/click-create-app-teamwork-redirect-url.png" alt="appse ai Teamwork Create App" width="700"/>

#### 4. Copy Your Client ID and Client Secret

Once your app is created, open it and go to the **Credentials** tab. You will find your **Client ID** and **Client Secret** here.

Copy both values.

<img src="/img/credentials/teamwork/client-id-client-secret.png" alt="appse ai Teamwork Copy Credentials" width="700"/>

#### 5. Paste Credentials in appse ai

Return to the appse ai credential form. Paste the copied **Client ID** and **Client Secret** into their respective fields and click **"Save"**.

appse ai will redirect you to the Teamwork consent screen. Review the requested permissions and click **Authorize** to complete the connection.

<img src="/img/credentials/teamwork/configure-credientials.png" alt="appse ai Teamwork Save Credential" width="700"/>

<br/>

:::warning

Keep your Client ID and Client Secret secure. Do not share them publicly. If you suspect your credentials have been compromised, you can regenerate them from the Teamwork Developer Portal at any time.

:::

---

## Triggers and Actions

Here is a list of the available triggers and actions for Teamwork:


### Triggers

- **On Company Created** — Fires whenever a new company is created in your Teamwork site. Use this to automatically kick off workflows when a new client or organization is added.

- **On Person Created** — Fires whenever a new person or contact is created in your Teamwork site. Use this to trigger onboarding workflows or sync contact data with other systems.

- **On Project Created** — Fires whenever a new project is created in your Teamwork site. Use this to automatically set up tasks, notify team members, or sync project data across platforms.

- **On Task Created** — Fires whenever a new task is created in your Teamwork site. Use this to trigger notifications, assign resources, or update external systems in real time.



### Actions

- **Add People to Project** — Add one or more people to an existing project in Teamwork. Useful for automating team assignments when a new project is created or when onboarding new members.

- **Complete Milestone** — Mark an existing milestone as complete in Teamwork. Use this to automatically close milestones when all related tasks are finished.

- **Complete Task** — Mark an existing task as complete in Teamwork. Use this to automatically close tasks based on events or conditions in your workflow.

- **Create Company** — Create a new company or client record in Teamwork. Use this to automatically add new clients when they are created in your CRM or other business tools.

- **Create Person** — Create a new person or contact in Teamwork. Use this to automatically sync contacts from external platforms such as CRMs, forms, or HR systems.

- **Create Project** — Create a new project in Teamwork. Use this to automatically spin up projects based on triggers from other tools like CRMs, support platforms, or form submissions.

- **Create Single Milestone** — Create a new milestone inside a project in Teamwork. Use this to automatically set key delivery dates and checkpoints when a project is created.

- **Create Subtask** — Create a new subtask under an existing task in Teamwork. Use this to automatically break down tasks into smaller actionable items based on workflow conditions.

- **Create Task** — Create a new task inside a task list in Teamwork. Use this to automatically generate tasks from triggers in external tools or other workflow steps.

- **Create Tasklist** — Create a new task list inside a project in Teamwork. Use this to automatically organize work by creating structured task lists when a new project is set up.

- **Un-complete Milestone** — Revert a completed milestone back to incomplete in Teamwork. Use this when a milestone needs to be reopened due to changes or additional work requirements.

- **Update Project** — Update the details of an existing project in Teamwork. Use this to automatically sync project information such as name, description, or status from external tools.

- **Update Single Milestone** — Update the details of an existing milestone in Teamwork. Use this to automatically adjust milestone deadlines, descriptions, or assignees based on workflow events.

- **Update Task** — Update the details of an existing task in Teamwork. Use this to automatically modify task properties such as due dates, priority, assignees, or descriptions.

- **Update Tasklist** — Update the details of an existing task list in Teamwork. Use this to automatically rename or reorganize task lists based on project changes or workflow conditions.

---

## Support

Need help? Contact our support team at [hello@appse.ai](mailto:hello@appse.ai)