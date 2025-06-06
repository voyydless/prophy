<p align="center">
   <img width="150" height="150" src="frontend/public/images/prophy-icon.png" alt="Prophy Logo">
</p>

<h1 align="center">MedPhys Hub</h1>

<div align="center">

![Status Badge](https://img.shields.io/badge/Status-In%20Progress-yellow)

</div>

<div align="center">

![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Django REST Framework](https://img.shields.io/badge/Django_REST_Framework-092E20?style=for-the-badge&logo=django&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Cypress](https://img.shields.io/badge/Cypress-17202C?style=for-the-badge&logo=cypress&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Redux](https://img.shields.io/badge/Redux-593D88?style=for-the-badge&logo=redux&logoColor=white)
![RTK Query](https://img.shields.io/badge/RTK_Query-593D88?style=for-the-badge&logo=redux&logoColor=white)
![Zod](https://img.shields.io/badge/Zod-3068B7?style=for-the-badge&logo=zod&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=json-web-tokens&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)
![DigitalOcean](https://img.shields.io/badge/DigitalOcean-0080FF?style=for-the-badge&logo=digitalocean&logoColor=white)

</div>

## Description

This application is a comprehensive web-based system designed for medical physicists at Prophy, providing a centralized platform to efficiently manage client data, schedule appointments, and organize institutional materials.

## Motivation

Companies providing medical physics services often lack a standardized tool to manage and organize data and business processes. Each company relies on its own methods, making it challenging for regulatory entities like ANVISA and CNEN to conduct audits effectively. Additionally, medical physicists frequently resort to manual processes for managing data and workflows, which are error-prone and time-consuming.

The goal of this project is to develop software that standardizes auditing processes and automates business workflows related to medical physics services. By doing so, it aims to enhance the security of healthcare services and improve the efficiency of medical physicists, ensuring better compliance and streamlined operations.

## Quick Start

### Set up a Python environment based on the `pyproject.toml` file:

1. **Install Poetry**:
   Poetry is a robust tool for dependency management and packaging in Python. To install it, follow the docs: [Poetry Installation](https://python-poetry.org/docs/#installation)

2. **Initialize the Project**:
   Navigate to your project directory containing the `pyproject.toml` file and run:

    ```bash
    poetry install
    ```

    This command will create a virtual environment and install the dependencies specified in the `pyproject.toml`.

### Set up the environment for the frontend:

1. **Install Node.js and npm**:

    - Download and install the latest Long-Term Support (LTS) version of Node.js from the official website: [https://nodejs.org/](https://nodejs.org/).
    - The Node.js installer includes npm (Node Package Manager), which you'll use to manage project dependencies.

2. **Install Project Dependencies**:

    - Inside of the `frontend` folder, run:

        ```bash
        npm install
        ```

        This command reads the `package.json` file and installs all specified dependencies into a `node_modules` folder.

### Set up the enviroment variables

#### Environment Variables for Backend

To run this Django project, specific environment variables must be configured in a `.env` file located at the `backend` folder. Below is a detailed explanation of all the environment variables required:

1. **DJANGO_SECRET_KEY**

-   **Description**: The secret key used by Django for cryptographic signing.
-   **Purpose**: This key ensures the security of cookies, tokens, and other cryptographic processes.
-   **Example**: `DJANGO_SECRET_KEY='<random_generated_secret_key>`
-   **Note**: This should be a long, unique, and randomly generated string. Never share it publicly.

2. **DEBUG**

-   **Description**: Controls whether the application is in debug mode.
-   **Purpose**: Debug mode is helpful during development but should always be set to `False` in production.
-   **Values**:
    -   `True`: Enables debug mode.
    -   `False`: Disables debug mode.
-   **Example**: `DEBUG=True`

3. **AUTH_COOKIE_SECURE**

-   **Description**: Determines whether the authentication cookie should only be sent over secure (HTTPS) connections.
-   **Purpose**: Enhances the security of cookies by restricting them to HTTPS.
-   **Values**:
    -   `True`: Only allow cookies over HTTPS.
    -   `False`: Allow cookies over both HTTP and HTTPS (useful for local development).
-   **Example**: `AUTH_COOKIE_SECURE=False`

4. **FRONTEND_URL**

-   **Description**: The URL of the frontend application that interacts with this Django backend.
-   **Purpose**: Used for configuring CORS and other integrations with the frontend.
-   **Example**: `FRONTEND_URL='http://localhost:3000'`

5. **DJANGO_ALLOWED_HOSTS**

-   **Description**: Specifies the host/domain names that this Django site can serve.
-   **Purpose**: Protects against HTTP Host header attacks.
-   **Values**: A comma-separated list of allowed hostnames.
-   **Example**: `DJANGO_ALLOWED_HOSTS='127.0.0.1,localhost'`

#### AWS Credentials for Email Services

The application uses AWS Simple Email Service (SES) for sending emails. The following environment variables are required to configure AWS SES:

6. **AWS_ACCESS_KEY_ID**

-   **Description**: Your AWS access key ID.
-   **Purpose**: Required for authenticating API requests to AWS services, including SES.
-   **Example**: `AWS_ACCESS_KEY_ID='your_aws_access_key_id'`

7. **AWS_SECRET_ACCESS_KEY**

-   **Description**: Your AWS secret access key.
-   **Purpose**: Required for authenticating API requests to AWS services, including SES.
-   **Example**: `AWS_SECRET_ACCESS_KEY='your_aws_secret_access_key'`

8. **AWS_SES_REGION_NAME**

-   **Description**: The AWS region where your SES service is configured.
-   **Purpose**: Specifies the AWS region for SES.
-   **Default**: `sa-east-1`
-   **Example**: `AWS_SES_REGION_NAME='us-east-1'`

#### Environment Variables for Frontend

To run the frontend application, only one variable must be set in a `.env` file located at `frontend` folder.

1. **NEXT_PUBLIC_HOST**

-   Description: The host URL for the backend application, used by the frontend to communicate with the backend API.
-   Purpose: Ensures the frontend correctly points to the backend application.
-   Example: `NEXT_PUBLIC_HOST=http://localhost:8000`

#### Notes

1. **Security**: Do not expose your `.env` file publicly or commit it to version control systems like Git.
2. **Production Configuration**: Ensure that `DEBUG` is `False` and `AUTH_COOKIE_SECURE` is `True` in production.
3. **Dynamic Configuration**: You can create separate `.env` files for different environments (e.g., `.env.production` and `.env.development`) and load them accordingly.

Ensure all required variables are properly set before running the application to avoid errors or insecure configurations.

### Set up database

1. Inside of the `backend` folder, run the migratios:

```bash
python manage.py makemigrations
```

```bash
python manage.py migrate
```

2. Run the script to populate the database with some example data:

```bash
./flush_and_populate_db.sh
```

### Run the application

1. In the `backend` folder, run:

```bash
python manage.py runserver
```

2. In a different terminal and inside the `frontend` folder, run:

```bash
npm run build && npm run start
```

If the environment variables were correctly set up, the application should be running in your local machine!

## Detailed Features

### User Authentication and Authorization

-   **Secure user registration and login system.**
-   **Role-based access control (RBAC) with the following user profiles:**
    -   **Prophy Manager:** Full access to all features.
    -   **Comercial**: Access to clients data (read-only), reports (read-only) and proposal of contracts (add/edit/read)
    -   **Internal Medical Physicist:** Access to most features, including client-specific data, institutional materials, and scheduling.
    -   **Client Manager:** Access to their own institution's data, equipment information, schedules (read-only), and invoices (read-only).
    -   **Unit Manager:** Assigned by a Client Manager to manage specific units, with access limited to their assigned units' data.
    -   **External Medical Physicist:** Limited access to schedules (read-only) and client data (read-only) associated with their assigned clients.

### Client Management

-   **Client Registration Form:**
    -   Allows approved clients to submit their information and request services.
-   **Client Dashboard:**
    -   Clients can register and manage their institution's information:
        -   CNPJ (Brazilian company ID)
        -   Institution details
        -   Contact details
        -   Units and responsible managers
        -   Equipment inventory
    -   Updating data needs approval from someone in the Prophy Staff
-   **Client Data Management (Internal Staff):**
    -   Internal staff can view, edit, review, and manage client data:
        -   Client details
        -   Units
        -   Equipments
        -   Invoices (including download options and payment status updates)
    -   Advanced filtering options for efficient data retrieval.

### Scheduling and Appointments

-   **Appointment Scheduling:**
    -   Internal staff can schedule appointments, specifying:
        -   Date and time
        -   Client
        -   Equipment involved
        -   Description of the service that will be provided
        -   Appointment status (scheduled, completed)
        -   Reports
    -   Google Calendar integration for seamless scheduling and reminders.
-   **Appointment Views:**
    -   Clients and assigned external physicists can view their scheduled appointments.
    -   Notifications and reminders via email and Google Calendar integration.

### Institutional Materials

-   **Material Management:**
    -   Internal staff can upload and manage institutional materials:
        -   PDFs
        -   Video links
        -   Categorization by client profile and diagnostic modality
    -   Access control to ensure only authorized users can view and download materials.

### Billing and Invoices

-   **Invoice Generation:**
    -   System generates invoices based on services provided.
    -   Internal staff can manage invoice details and payment status.
-   **Payment Tracking:**
    -   Clients can view their invoices, download copies, and upload payment confirmations.

## Project Status and Future Development

The project is actively in development. There's 4 stages of development:

-   [x] User authentication and client registration.
-   [ ] Client data management for both internal staff and clients _(actively under development)_.
-   [ ] Appointment scheduling and Reports.
-   [ ] Institutional materials management and access control.

Future development will include:

-   **Enhanced reporting and analytics.**
-   **Mobile app for clients and staff.**
-   **Continuous improvement based on user feedback.**

## 🤝 Contributing

If you'd like to contribute, please fork the repository and open a pull request to the `main` branch.
