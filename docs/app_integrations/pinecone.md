---
title: "Pinecone"
slug: /app-integrations/pinecone/
---

Pinecone is a vector database designed for building scalable AI applications. It allows you to store, index, and search high-dimensional embeddings efficiently, making it ideal for semantic search and retrieval-augmented generation (RAG) use cases.

## Set Up Credential

:::info  
To use the Pinecone API, you need a Pinecone account and an active project with an index created.  
:::

### Required Fields

You'll be asked to fill in the following details:

| Field           | Description                                      |
| --------------- | ------------------------------------------------ |
| Connection Name | A name to help you identify this connection      |
| API Key         | Your Pinecone API Key                            |

### Step-by-Step Guide

#### 1. Open the Credential Form

Click **Select a Credential** and choose **Pinecone** from the application list.

<img src="\img\credentials\pinecone\pinecone-create-new-connection.png" alt="appse ai Pinecone Select Credential" width="700"/>

<br/>

This opens the Pinecone credential form. Add your **Connection Name**.

<img src="\img\credentials\pinecone\pinecone-connection-name.png" alt="appse ai Pinecone Connection Name" width="700"/>

#### 2. Sign In / Create an Account

Go to [https://www.pinecone.io](https://www.pinecone.io) and sign in or sign up. You can use Google sign-in for faster access.

#### 3. Open the Pinecone Console

Once logged in, open the [Pinecone Console](https://app.pinecone.io).

#### 4. Navigate to API Keys

From the left sidebar, click on **API Keys**.

<img src="\img\credentials\pinecone\api-keys.png" alt="appse ai Pinecone API Keys" width="700"/>
<br/>

#### 5. Create a New API Key

Click **Create API Key**, give it a name, and click **Create**.

<img src="\img\credentials\pinecone\create-api-key.png" alt="appse ai Pinecone Create API Key" width="700"/>
<br/>

#### 6. Copy Your API Key

Copy the API key immediately after creation.

:::warning
You will **not be able to see this key again** after closing the dialog. Store it somewhere safe before proceeding.
:::

<img src="\img\credentials\pinecone\copy-api-key.png" alt="appse ai Pinecone Copy API Key" width="700"/>
<br/>

#### 7. Create an Index (if not already created)

Go to the **Indexes** section and click **Create Index**. Provide:

- Index name
- Dimension (based on your embedding model)
- Metric (cosine, dotproduct, euclidean)
- Cloud and region (e.g. AWS, us-west-2)

<img src="\img\credentials\pinecone\create-index.png" alt="appse ai Pinecone Create Index" width="700"/>
<br/>

#### 8. Paste into appse ai

Return to the appse ai credential form:

- Copy your **API Key** from Step 6 and paste it into the **API Key** field.
- Go to **Indexes** → click on your index → copy the **Index URL** (e.g. `https://your-index-name-xxxx.svc.pinecone.io`) and paste it into the **Base URL** field.

Click **Save**. Your Pinecone credential should now be connected.

<img src="\img\credentials\pinecone\add-credentials.png" alt="appse ai Pinecone Add Credentials" width="700"/>
<br/>

---

## Triggers and Actions

Here is a list of the available actions for Pinecone:

### Actions

- **Upsert Documents** — Insert or update documents into a Pinecone index. Requires index name, document ID(s), text/content, embeddings, and optional metadata.

- **Search** — Perform semantic search over indexed documents. Requires index name, query text or embedding, top K results, and optional filters.

---

## Support

Need help? Contact our support team at [hello@appse.ai](mailto:hello@appse.ai)