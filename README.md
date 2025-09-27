## Blog-Backend-REST-API-NestJS-Prisma

A simple backend REST API for a blog built using NestJS, Prisma, PostgreSQL and Swagger.

### Installation

1. Install dependencies: `npm install`
2. Start a PostgreSQL database with docker using: `docker-compose up -d`.
   - If you have a local instance of PostgreSQL running, you can skip this step. In this case, you will need to change the `DATABASE_URL` inside the `.env` file with a valid [PostgreSQL connection string](https://www.prisma.io/docs/concepts/database-connectors/postgresql#connection-details) for your database.
3. Apply database migrations: `npx prisma migrate dev`
4. Start the project: `npm run start:dev`
5. Access the project at http://localhost:3000/api

### Manual Installation (Without Docker)

If you can't or don't want to use Docker, you can set up the PostgreSQL database locally.

**Requirements:**

- **PostgreSQL** server installed and running on your local machine.
- An empty database created (e.g., `prisma`).

**Steps:**

1.  **Clone the Repository and Install Dependencies:**

    ```bash
    git clone https://github.com/prisma/blog-backend-rest-api-nestjs-prisma.git
    cd blog-backend-rest-api-nestjs-prisma
    npm install
    ```

    _(Note: If you encounter an `ECONNRESET` error, you can try `npm config set registry https://registry.npmmirror.com/` before `npm install`.)_

2.  **Configure the Database Connection:**
    Create a file named **`.env`** in the root of the project and use the connection URL for your local server.

    ```
    # Make sure to replace 'your_user', 'your_password', and 'db_name'
    DATABASE_URL="postgresql://your_user:your_password@localhost:5432/db_name?schema=public"
    ```

3.  **Apply Prisma Migrations:**
    Prisma will read the schema and create the necessary tables in your local PostgreSQL database.

    ```bash
    npx prisma generate
    npx prisma migrate dev
    ```

4.  **Start the NestJS Application:**
    ```bash
    npm run start:dev
    ```
    The API will be available at `http://localhost:3000/api`.
