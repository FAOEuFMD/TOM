# TOM Training Management System

TOM is a web app developed for the European Commission for the Control of Foot and Mouth Disease (EuFMD) that allows countries to manage their veterinarian training capacity. It supports the training capacity of member nations through a competency framework and provides recognition to individual learners. It also allows country managers to monitor the completion of training on a national scale.

This app is a prototype built with Vue, Node/Express, Tailwind CSS & D3.

See the deployed version here: https://eufmd-tom.com

See the documentation here: https://eufmd-fast-docs.onrender.com/

## Project setup

1. Clone the repository and create a .gitignore file.

#### .gitignore Settings

This project uses a `.gitignore` file to exclude certain files and directories from version control. Here’s a summary of what’s ignored:

- **Environment Files:** `.env`, `.env.example`, `.env.local`, `.env.production` – These files contain sensitive configuration and should not be committed to the repository.
- **Build Artifacts:** `dist/`, `build/` – Generated build artifacts and temporary files are excluded to keep the repository clean.
- **IDE Configurations:** `.vscode/`, `.idea/` – IDE-specific settings are ignored to avoid committing personal development environment configurations.
- **Dump files:** `.sql/` – Ignores plain SQL dump files because they often contain large amounts of data and are not typically useful to track in version control.

Please make sure to keep these files out of version control to avoid potential issues.

### Dependencies

3. Run `npm install` on the root folder to install dependencies related to Express.

4. `cd client` and run `npm install` to install dependencies related to Vue.

### Database prep

5. Create a `.env` file in the root directory of the project and fill in the necessary environment variables. Use the `.env.example` file as a template:

   ```sh
   cp .env.example .env
   ```

6. Create a folder in your root named dump-files. Export a MySQL dump file from the production database and move it to your dump-files folder.

7. Connect to MySQL and create a new local database called TOM. Exit the MySQL client.

8. Run `mysql -u root -p TOM < path/to/your/dump/file` to migrate the dump file into your local database.

9. Check that the migration was successful and that the tables for your local database contain the exported data.

### Development server

10. Run `npm start` in the project directory to start the Express server on port 5500.
11. `cd client` and run `npm run serve` to start the client server in development mode with hot reloading.

### JWT

12. Add your JWT secret to your `.env` file:

```

SUPER_SECRET=YOUR_SECRET

```

JSON Web Tokens (JWT) are a compact, URL-safe means of representing claims to be transferred between two parties. The tokens are designed to be secure and can be used for authentication and information exchange.

### Production build

13. Run `npm run build` in the client folder to create a production build in the server folder (`/server/public`).

### Deploying to AWS & Render

Deployment to both AWS and Render is managed through a Continuous Integration and Deployment (CI/CD) pipeline using CircleCI. The configurations for this pipeline are located in the `.circleci` folder in the root directory of this application.

The staging environment is hosted on Render, allowing for changes to be tested before they are deployed to production. The Render environment is connected to a staging database on AWS, where necessary changes and updates can be made.

14. Remember to update your environment variables on Render whenever they are changed locally to ensure the staging environment functions correctly. This ensures that the application behaves consistently across different environments.

Good luck!
