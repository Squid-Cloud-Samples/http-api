# Integrate an HTTP API with Squid

This sample code accompanies a [tutorial](https://docs.squid.cloud/docs/tutorials/http-api/#create-an-api-integration) showing how to integrate an HTTP API with Squid Cloud and secure it using the Squid Backend SDK.

## Prerequisites

For this project you will need:

- NodeJS v18 or later.
- A Squid Cloud account and a Squid application. To sign up for Squid, go to [Squid Cloud Console](https://console.squid.cloud). Once signed up, you can create an application.
- The Squid Cloud CLI (`npm i @squidcloud/cli`).

## Setup

1. In the [Squid Cloud Console](https://console.squid.cloud) create a new app called `cat-facts`.

2. Follow the steps in the [tutorial](https://docs.squid.cloud/docs/tutorials/http-api/#create-an-api-integration) to create a new API integration in the Squid Cloud Console.

## Environment configuration

### Setting up your `.env` file

Tn the console **Overview** page, scroll to the **Backend project** section and select **Create .env file**. This provides you with the command to create the `.env` file required for this template to work and run.

Change to the backend directory, and install the required dependencies:

```bash
cd backend
npm install
```

Run the initialization command you copied from the console. The command has the following format:

```bash
squid init-env \
 --appId YOUR_APP_ID \
 --apiKey YOUR_API_KEY \
 --environmentId YOUR_ENVIRONMENT_ID \
 --squidDeveloperId YOUR_SQUID_DEVELOPER_ID \
 --region YOUR_REGION
```

## Running the application

### Starting the local backend server

To launch the local backend server of your Squid application, run the following command from the `backend` directory:

```bash
squid start
```

You'll see output similar to the following, indicating that your server is up and running:

```bash
> nodemon --watch ./src --exec ts-node -r tsconfig-paths/register src/main.ts
[Nest] 68047  - 03/15/2024, 7:55:23 PM     LOG [NestApplication] Nest application successfully started +1ms
```

### Launching the frontend server

Open a second terminal window. You should now have two terminal windows open: one running the local backend server, and one in which you will run the frontend. Initialize the frontend server by running the following commands:

```bash
cd frontend
npm install
npm run setup-env
```

To launch the frontend of your Squid application, run the following command from the `front` directory:

```bash
npm run dev
```

Verify that Vite server has started, providing URLs to access your app:

```bash
  VITE v5.1.6  ready in 149 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
```