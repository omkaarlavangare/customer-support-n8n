# Setup Guide

## Customer Support Over Email

After importing the workflow into n8n, complete the following steps:

### 1. Connect accounts
Create credentials in n8n for:
- OpenAI
- Gmail
- Pinecone

Go to **Credentials → New** and authenticate each service.

### 2. Configure Gmail trigger
Open the **Detect New Email** node:
- Select your Gmail account
- Optionally add filters to control which emails trigger the workflow

### 3. Set up Pinecone
In both Pinecone nodes:
- Replace `your-index-name`
- Replace `your-namespace`

Ensure:
- The index exists in Pinecone
- Dimensions match the embeddings configuration (512)

### 4. Review AI agent
Open **Customer Support Agent**:
- Customize the system message if needed (tone, branding, etc.)

### 5. Test the workflow
- Send an email to your connected Gmail
- The workflow should classify the email, generate a reply, and send it automatically

---

## Customer Support Chatbot (RAG with Google Drive)

After importing the workflow into n8n, complete the following steps:

### 1. Connect accounts
Create credentials for:
- OpenAI
- Google Drive
- Pinecone

### 2. Configure Google Drive folder
Open **Detect New Document**:
- Replace `REPLACE_WITH_YOUR_FOLDER_ID`
- Select a folder containing your documents (FAQs, policies, etc.)

New files added to this folder will be automatically processed.

### 3. Configure Pinecone
In both vector store nodes:
- Replace `your-index-name`
- Replace `your-namespace`

Ensure the index exists and matches embedding dimensions.

### 4. Upload documents
- Add a test document (PDF, text, etc.) to your configured Drive folder
- The workflow will process and store embeddings in Pinecone

### 5. Set up chat trigger
Open **Chat Trigger**:
- Replace `REPLACE_WITH_YOUR_WEBHOOK_ID` or regenerate it
- Use the webhook URL to send chat messages

### 6. Test the chatbot
- Send a request to the webhook
- The chatbot should retrieve relevant information and respond accordingly

---

## Troubleshooting

If the workflow is not working as expected, check:
- Credentials are properly connected
- Pinecone index and namespace are correct
- Documents have been uploaded and indexed
