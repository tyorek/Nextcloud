  Services
   * nextcloud: The main Nextcloud application, using the latest official image.
   * db: A MariaDB database for Nextcloud, also using the latest official image.

  Configuration
   * Networking: Both services are connected on a custom bridge network named nextcloud_network.
   * Data Persistence: Data for Nextcloud and MariaDB is stored in named volumes (nextcloud_data and db_data
     respectively) to ensure data is not lost when containers are recreated.
   * Environment: The Nextcloud service is pre-configured to connect to the db service. It's also set up to be
     accessed via HTTPS. You will likely need to change the OVERWRITEHOST value to
     your own domain name.
   * Ports: The Nextcloud container's port 80 is mapped to the host's port 80.

  Usage
  To use this configuration:
   1. Save the code as docker-compose.yml.
   2. It is highly recommended to change the default passwords in the environment section for both services for
      security reasons.
   3. Run docker-compose up -d in the same directory.
   4. Access your Nextcloud instance at the address you configured.
