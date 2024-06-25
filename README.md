## Contents

- [Project Description](#project-description)
- [Prerequisites](#prerequisities)
- [How to Install](#how-to-install)
- [How to Use](#how-to-use)
- [Deploy on Vercel](#deploy-on-vercel)

## Project Description

The tool is a chatbot receiving applications for a job. It asks the prescreening questions defined by the recruiter. It also parses and memorizes the company documents to answer questions from the candidate. If the chatbot does not know the answer it emails the question to the recruiter.

The answers of the candidates are stored in a Google Sheet file.

The users can self-deploy the backend to Vercel.

Company documents are stored in Upstash Vector.

Chat history is stored in Upstash Redis.

The users need to provide a JSON to configure the chatbot. (job-config.json)

Feel free to create issues on the repository.

## Prerequisities

1. Create an Upstash Vector Index.
2. Create an Upstash Redis Database.
3. Get an OpenAI API Key.
4. Get an email address and a password. (Provide the email address, password, and email service type while creating the .env file.)
5. Create a Google service account and enable Google Sheets and Google Drive API. (Provide service account email to GOOGLE_CLIENT_EMAIL and private key to GOOGLE_PRIVATE_KEY while creating the .env file.)
6. Fill and upload the job-config.json file to Google Drive.
7. Create a folder on Google Drive to receive uploaded CVs.
8. Create a Google Sheets document to store applicant answers

## How to Install

To install the project on your local device in order to make changes or run it, you can follow these steps:

1. Install the source code to your device

```bash
git clone git@github.com:upstash/QuickApply.git
```

2. Go to the project folder

```bash
cd QuickApply
```

3. Install `next` if not installed already

```bash
npm install next
```

4. Create a `.env` file and fill it with your API keys.

```bash
# .env

UPSTASH_REDIS_REST_URL="..."
UPSTASH_REDIS_REST_TOKEN="..."
OPEN_AI_API_KEY="..."
UPSTASH_VECTOR_REST_URL="..."
UPSTASH_VECTOR_REST_TOKEN="..."
EMAIL="..."
EMAIL_PASSWORD="..."
EMAIL_SERVICE="gmail"
GOOGLE_PRIVATE_KEY="..."
GOOGLE_CLIENT_EMAIL="..."
GOOGLE_SHEET_ID="..."
GOOGLE_DRIVE_ID="..."
MODEL_NAME="..."
CONFIG_FILE_ID="..."
```

5. Run the project

```bash
npm run dev
```

6. Go to `https://localhost:3000/`

## How to Use

Once you run the program, you will be greeted by the AI-powered assistant's welcome message.

After answering the assistant's questions, it will ask you to upload your CV.

When you upload your CV, it will allow you to ask questions about the job.

The applicant must indicate he or she has no further questions to the assistant to finish the application process and save the application.

## Deploy on Vercel

You can deploy to project using the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js using the button below.

[![Deploy with Vercel](https://vercel.com/button)]()
