<p align="center">
  <picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/dkrasnovdev/siberiana-public-assets/main/assets/siberiana-logo-dark-background.svg">
  <img src="https://raw.githubusercontent.com/dkrasnovdev/siberiana-public-assets/main/assets/siberiana-logo-dark-background.svg" width="240" height="90" alt="Logo for Siberiana">
</picture>
</p>

<p align="center">
  Сибириана | Агрегатор историко-культурного наследия Енисейской Сибири.
</p>

````markdown
# Siberiana Keycloak Setup

This repository contains configuration files and instructions for setting up a Keycloak instance along with a PostgreSQL database using Docker Compose.

## Prerequisites

Before you begin, ensure you have the following installed:

- Docker
- Docker Compose

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/dkrasnovdev/siberiana-keycloak.git
   cd siberiana-keycloak
   ```
````

2. Copy the `.env.example` file and rename it to `.env`. Fill in the required environment variables with appropriate values.

   ```bash
   cp .env.example .env
   # Edit .env file with your configuration
   ```

3. Configure Keycloak Realm (Optional):

   If you wish to customize the Keycloak realm, you can modify the `keycloak/siberiana-realm.json` file.

4. Build and Start the Services:

   ```bash
   docker-compose up -d
   ```

   This will start the Keycloak and PostgreSQL containers.

5. Access Keycloak:

   Keycloak admin console will be available at: `http://localhost:8080`. Use the admin credentials specified in your `.env` file to log in.

6. Clean Up:

   To stop and remove the containers, run:

   ```bash
   docker-compose down
   ```

## Files

- `docker-compose.yml`: Docker Compose configuration for Keycloak and PostgreSQL services.
- `.env.example`: Example environment variables file. Create a `.env` file based on this template.
- `keycloak/keycloak.conf`: Keycloak configuration settings.
- `keycloak/siberiana-realm.json`: Keycloak realm configuration.

## Customization

You can customize the configuration files to suit your specific requirements. Refer to the official documentation for Docker Compose and Keycloak for more advanced configurations.

## Troubleshooting

If you encounter any issues or have questions, please feel free to create an issue on this repository.
