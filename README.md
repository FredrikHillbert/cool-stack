# cool-stack

A customizable Remix Run stack built with `Coolify` and `Hetzner` in mind! This stack uses **PostgreSQL** as its database in both local development and production environments.

---

## Features

- **Remix Framework**: Built-in routing, data loading, and server-side rendering.
- **Database**: PostgreSQL for both local and production environments.
- **Deployment**: Easy deployment using [Coolify](https://coolify.io/) and Hetzner Cloud.
- **ORM**: Prisma for database migrations and queries.
- **Environment**: Works seamlessly on both Windows and Unix-based systems.

---

## What's in the Stack?

cool-stack includes a curated selection of tools and frameworks to make development and deployment smooth and efficient:

- **[Remix](https://remix.run/)**: A full-stack web framework for building dynamic and fast web applications.
- **[Prisma](https://www.prisma.io/)**: A modern database toolkit for working with SQL databases.
- **[PostgreSQL](https://www.postgresql.org/)**: Robust and scalable SQL database for production.
- **[Coolify](https://coolify.io/)**: A self-hosting platform for easy app deployment on Hetzner and other cloud providers.
- **[Tailwind CSS](https://tailwindcss.com/)**: Utility-first CSS framework for rapid UI development.
- **Environment-Specific Configurations**: `.env` support for local and production settings.
- **TypeScript (Optional)**: Ensures type safety and better developer experience.

---

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_GITHUB/cool-stack.git
cd cool-stack
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Set Up Environment Variables
Copy the example .env file:

```bash 
cp .env.example .env
```
Update .env with your local PostgreSQL connection details:
```bash
DATABASE_URL=postgresql://postgres:yourpassword@localhost:5432/coolstack_dev
```
Replace yourpassword with the password you set for your PostgreSQL user.

#### 3.1 Setting Up PostgreSQL for Local Development (Windows) - Optional
1. Download and Install PostgreSQL:

    * Visit the PostgreSQL download page and install the appropriate version for your system.
    * During installation, set a password for the postgres user and take note of the installation directory.

2. Add PostgreSQL to PATH:

    * Add the bin folder of your PostgreSQL installation to your system's PATH variable. Example: C:\Program Files\PostgreSQL\<version>\bin.

3. Start PostgreSQL:

    * Open the pgAdmin GUI tool to manage your PostgreSQL server.
    * Alternatively, start the service manually:
      * Open the Services app (Win + R, type services.msc).
      * Find the PostgreSQL service, right-click, and select Start.

4. Create a Database:

* Open a Command Prompt or psql shell and run:
```bash
psql -U postgres
```

* Create a development database:
```sql
CREATE DATABASE yourDatabaseName;
```

* (Optional) Create a separate user for your application:
```sql
CREATE USER yourDatabaseName_user WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE yourDatabaseName_user TO yourDatabaseName;
```
### 4. Database Setup

Run the Prisma migrations:
```bash
npx prisma migrate dev --name init
```

See the locally deployed database:
```bash
npx prisma studio
``` 

# Deploying to Production
### Prerequisites
1. **Coolify** installed on your Hetzner server.
2. A **PostgreSQL** database set up (either on Hetzner or self-hosted).

###  Deployment Steps
1. Add a new Node.js app in Coolify.
2. Configure the following environment variables in Coolify:
    * DB_PROVIDER=postgresql
    * DATABASE_URL=postgresql://USER:PASSWORD@HOST:PORT/DATABASE

3. Trigger the deployment using Coolify’s interface or GitHub Actions.

# Contributing
Feel free to open issues or pull requests to improve the `cool-stack` template!

License
MIT
