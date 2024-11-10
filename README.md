![image](https://github.com/user-attachments/assets/8d6d2082-ebc3-402d-aacc-5a38f057a083)

# Shlink Docker
This will create everything needed to run Shlink in a Docker container including a container for a Cloudflare Tunnel and one for the MariaDB database.
This uses the official [Shlink image](https://github.com/shlinkio/shlink), the official [MariaDB image](https://github.com/MariaDB/mariadb-docker), the official [Shlink web client image](https://github.com/shlinkio/shlink-web-client), the official [Cloudflare tunnel image](https://github.com/cloudflare/cloudflared).

Use .env to define the variables.

### .env Variables
 - `CONTAINER_NAME` the name of your Shlink stack. There will be 4 containers spawned.
   - The one with `_app` appended to it is the Shlink application image that runs all of Shlink.
   - The one with `_db` appended to it is the MariaDB image for Shlink to store all the configurations.
   - The one with `_web_client` append to it is the Shlink web client image that gives you a nice UI to manage your short URLs.
   - The one with `_cf` appended to it is the Cloudflare tunnel image for the Shlink application.
 - `DB_NAME` the name of the MariaDB database that Shlink will use.
 - `DB_ROOT_PWD` the MariaDB root password.
 - `DB_USER` the database user that Shlink will use.
 - `DB_USER_PWD` the password for the database user that Shlink will use.
 - `SHORT_DOMAIN` the domain for the short URLs. (only include the FQDN)
 - `REDIRECT_DOMAIN` where invalid short links, direct visits to the short domain, or 404 pages will be sent. (this needs to start with https://)
 - `APP_PORT` the port that the Shlink application will run on and the port used with the Cloudflare tunnel.
 - `ADMIN_API` the initial API key that will be used to configure Shlink and will be preloaded to the Shlink Web Client.
 - `WEB_CLIENT_PORT` the port the Shlink web client will use.
 - `CF_TUNNEL_B64` the Base64 of the Cloudflare tunnel for Shlink.

 [More detailed documentation](https://thedxt.ca/2024/11/shlink-with-docker-and-cloudflare-tunnel/)
