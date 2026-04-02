---
title: "Monday.com"
slug: /app-integrations/monday-com/
---

Monday.com is a work management and CRM platform that helps teams plan, track, and collaborate on projects, pipelines, and customer relationships. Integrating Monday.com into appse ai enables you to manage boards, items, contacts, and deals through automated workflows.

## Set Up Credential

:::info
To use the Monday.com API, you need a Monday.com account and a Personal API Token.
:::

### Required Fields

You'll be asked to fill in the following details:

| Field           | Description                                          |
| --------------- | ---------------------------------------------------- |
| Connection Name | A name to help you identify this connection          |
| API Token       | Your Monday.com Personal API Token                   |

### Step-by-Step Guide

#### 1. Open the Credential Form

Click **Select a Credential** and choose **Monday.com** from the application list.

<img src="\img\credentials\monday-com\monday-create-new-connection.png" alt="appse ai Monday.com Select Credential" width="700"/>

<br/>

This opens the Monday.com credential form. Add your **Connection Name**.

<img src="\img\credentials\monday-com\monday-connection-name.png" alt="appse ai Monday.com Connection Name" width="700"/>

#### 2. Sign In / Create an Account

Go to [https://monday.com](https://monday.com) and sign in or sign up for a free account.

#### 3. Open the Developer Center

Click on your **Profile Picture** in the top right corner and select **Developers**.

<img src="\img\credentials\monday-com\monday-developers.png" alt="appse ai Monday.com Developers" width="700"/>
<br/>

#### 4. Navigate to Developer Center

In the Developer Center, click on **API Tokens** at the bottom

<img src="\img\credentials\monday-com\monday-access-token.png" alt="appse ai Monday.com Access Tokens" width="700"/>
<br/>

#### 5. Copy Your API Token

Click **Show** next to your GraphQL API Token and copy it.

<img src="\img\credentials\monday-com\monday-copy-token.png" alt="appse ai Monday.com Copy Token" width="700"/>
<br/>

:::warning
Keep your **API Token** safe. Do not share it publicly or commit it to version control. If compromised, you can regenerate it from the same page — note that regenerating will immediately invalidate the old token.
:::

#### 6. Paste into appse ai

Return to the appse ai credential form and paste your **API Token** into the **API Token** field. Click **Save**. Your Monday.com credential should now be connected.

<img src="\img\credentials\monday-com\monday-paste-token.png" alt="appse ai Monday.com Paste Token" width="700"/>
<br/>

---

## Triggers and Actions

Here is a list of the available actions for Monday.com:

### Actions

- **Create Board** — Create a new board in Monday.com with a specified name and visibility type (public, private, or shareable).

- **Create Column** — Add a new column to an existing board. Supports types including Text, Email, Phone, Status, Date, People, and more.

- **Create Group** — Create a new group (section) on a board to categorize and organize items.

- **Create Item** — Create a new item on a board from a group with a name.

- **Delete Board** — Permanently delete a board and all its items from Monday.com.

- **Delete Group** — Permanently delete a group and all its items from a board in Monday.com.

- **Delete Item** — Permanently delete an item from a board. Use the Get Item action to get the item ID.

- **Get Board** — Retrieve the details and metadata of a specific board by its ID.

- **Get Columns** — Retrieve all columns of a specified board. Use this to find column IDs needed for updating item values.

- **Get Groups** — Retrieve all groups within a specified board.

- **Get Items by Board** — Retrieve all items from a specified board including their column values.

- **Get Items by Group** — Retrieve all items from a specific group within a board.

- **Update Board** — Update an existing board's attributes such as name or description.

- **Update Item Single Column** — Update a single column value of an existing item without affecting any other columns. Use the Get Columns action to find the column ID.

---
## Support

Need help? Contact our support team at [hello@appse.ai](mailto:hello@appse.ai)