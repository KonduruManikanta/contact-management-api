This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.js`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel




Here's a sample `README.md` file for your project based on the requirements provided:

---

# Contact Management API

This project is a simple Contact Management API built with Next.js and SQLite, designed to handle contact information with file upload capabilities.

## Table of Contents
- [Setup Instructions](#setup-instructions)
- [Running the Backend Server](#running-the-backend-server)
- [Database Schema](#database-schema)
- [API Documentation](#api-documentation)
- [Database Setup](#database-setup)
- [Additional Information](#additional-information)

---

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/contact-management-api.git
   cd contact-management-api
   ```

2. **Install dependencies**:
   Ensure you have Node.js installed, then run:
   ```bash
   npm install
   ```

3. **Set up environment variables**:
   - Create a `.env.local` file in the root directory.
   - Add the following variables with your values:
     ```plaintext
     JWT_SECRET=your-secret-key
     EMAIL_USER=your-email@gmail.com
     EMAIL_PASS=your-email-password
     BASE_URL=http://localhost:3000
     ```

### Running the Backend Server

To start the development server:

```bash
npm run dev
```

- The server will run on [http://localhost:3000](http://localhost:3000).

### Database Schema

The database schema is defined as an ER Diagram:

- **Contacts Table**
  - `id`: UUID (Primary Key)
  - `firstName`: String
  - `lastName`: String
  - `email`: String (unique)
  - `phoneNumber`: String
  - `createdAt`: Date
  - `updatedAt`: Date

- **Files Table**
  - `id`: UUID (Primary Key)
  - `fileName`: String
  - `filePath`: String
  - `uploadedAt`: Date
  - `contactId`: Foreign Key (references Contacts table)

![ER Diagram](./docs/ER-diagram.png) _(Ensure this image is present in your `docs` folder)_

### API Documentation

Here's how to test the endpoints in Postman:

#### Base URL:
```
http://localhost:3000/api
```

1. **Upload a File**

   - **Method**: POST
   - **URL**: `/upload`
   - **Body**: `form-data`
     - **Key**: `file` (Type: File)
     - Select the file you want to upload.
   - **Response**:
     ```json
     {
       "message": "File uploaded successfully!"
     }
     ```

2. **Get All Contacts**

   - **Method**: GET
   - **URL**: `/contacts`
   - **Response**:
     ```json
     [
       {
         "id": "12345",
         "firstName": "John",
         "lastName": "Doe",
         "email": "john.doe@example.com",
         "phoneNumber": "1234567890",
         "createdAt": "2024-10-10T10:00:00Z",
         "updatedAt": "2024-10-10T10:00:00Z"
       }
     ]
     ```

3. **Create a New Contact**

   - **Method**: POST
   - **URL**: `/contacts`
   - **Body** (JSON):
     ```json
     {
       "firstName": "John",
       "lastName": "Doe",
       "email": "john.doe@example.com",
       "phoneNumber": "1234567890"
     }
     ```
   - **Response**:
     ```json
     {
       "id": "12345",
       "message": "Contact created successfully!"
     }
     ```

#### Importing Postman Collection
You can import the provided Postman collection in `docs/ContactManagementAPI.postman_collection.json` for easier testing of API endpoints.

### Database Setup

1. **Initial Setup**
   - SQLite is used as the database. The database file will be automatically created upon running the project for the first time.

2. **Migrations**
   - You may need to run migrations manually if the database schema changes. Run the following command to sync migrations:
     ```bash
     npm run migrate
     ```



This `README.md` file provides all necessary steps and documentation for setting up and working with the Contact Management API.

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
#   c o n t a c t - m a n a g e m e n t - a p i 
 
 
