# Traefik Configuration

This is a sample configuration file for running Traefik with Docker.

## Prerequisites

- Docker installed on your machine

## Usage

1. Clone this repository to your local machine.

2. Open a terminal and navigate to the cloned repository.

3. Run the following command to start Traefik:

    ```bash
    docker-compose up -d
    ```

4. Traefik will now be running on port 80 for HTTP and port 443 for HTTPS. You can access the Traefik dashboard by visiting `http://localhost:8080` in your web browser.

5. To secure the Traefik dashboard with basic authentication, update the `traefik.http.middlewares.auth-basic.basicauth.users` label in the `docker-compose.yml` file with your desired username and hashed password.

6. Restart Traefik using the following command:

    ```bash
    docker-compose restart traefik
    ```

7. The Traefik dashboard will now require authentication to access.

## Configuration

The `docker-compose.yml` file contains the configuration for running Traefik with Docker. You can modify the configuration as per your requirements.

### Certificates

Traefik uses Let's Encrypt to automatically generate SSL certificates. Make sure to replace the `email` field in the `traefik.http.routers.traefik-dash-secure.tls.certresolver=myresolver` label with your own email address.

### Middleware

The `traefik.http.middlewares.redirect-to-https` middleware is used to redirect HTTP requests to HTTPS. You can customize this middleware as per your needs.

The `traefik.http.middlewares.auth-basic` middleware is used to secure the Traefik dashboard with basic authentication. Update the `users` field with your desired username and hashed password.

## Troubleshooting

If you encounter any issues while running Traefik, please refer to the official documentation for troubleshooting steps.

## License

This project is licensed under the [MIT License](LICENSE).
