# Installing WordPress and WooCommerce

This introduction will walk you through the process of installing WordPress, setting up WooCommerce, creating WooCommerce API keys (wc_key and wc_secret), and how to add sample products.

For your WordPress website setup, I show you three different methods: LocalWP, MAMP, and Docker Compose.

Of course, there are more methods, but in the end, it all depends on your preferences and what you want to use.

## Prerequisites

Before you begin, ensure that you have the following prerequisites installed on your computer:

- [LocalWP](https://localwp.com/) (for LocalWP method)
- [MAMP](https://www.mamp.info/) (for MAMP method)
- [Docker](https://www.docker.com/) (for Docker Compose method)

Or if you already have your own wordpress site go to:

[Setting Up WooCommerce - section](#setting-up-woocommerce)

[Creating WooCommerce API Keys - section](#creating-woocommerce-api-keys)

[How To Add Sample Products - section](#how-to-add-sample-products)


## Method 1: LocalWP

1. Download and install LocalWP on your computer from the [official website](https://localwp.com/).

2. Launch LocalWP and create a new site.
   
3. Choose the desired PHP version, MySQL version, and site name during the setup.

4. Click on the "Start Site" button to create your WordPress site.

5. Follow the on-screen instructions to set up your WordPress site, including creating an admin account and site title.

6. Access your WordPress site by clicking the "View Site" button within LocalWP.

7. Follow the on-screen instructions to complete the WordPress installation, including creating an admin account and site title.

## Method 2: MAMP

1. Download and install MAMP from the [official website](https://www.mamp.info/).

2. Launch MAMP and start the Apache and MySQL servers.

3. Download WordPress from [wordpress.org](https://wordpress.org/download/) and unzip the files to a folder in your MAMP "htdocs" directory (e.g., `htdocs/wordpress`).

4. Create a new MySQL database for your WordPress site using the phpMyAdmin interface provided by MAMP.

5. Rename the `wp-config-sample.php` file in the WordPress folder to `wp-config.php`.

6. Edit the `wp-config.php` file and update the database configuration with the database name, username, and password created in step 4.

7. Open your web browser and navigate to `http://localhost:8888/wordpress` (or the appropriate port and directory where you installed WordPress).

8. Follow the on-screen instructions to complete the WordPress installation, including creating an admin account and site title.

9. Once the installation is complete, you can access your WordPress site by navigating to `http://localhost:8888/wordpress`.

## Method 3: Docker Compose

1. Install Docker on your computer from [Docker's official website](https://www.docker.com/).

2. Create a directory for your WordPress project and navigate to it using your terminal.

3. Create a `docker-compose.yml` file in your project directory with the following content:

```yaml
version: '3'
services:
  wordpress:
    image: wordpress
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepassword
      WORDPRESS_DB_NAME: exampledb
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: examplepassword
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepassword
```
4. Open your terminal and navigate to the project directory.

5. Run the following command to start the Docker containers: docker-compose up -d

6.Once the containers are up and running, open your web browser and navigate to http://localhost:8080.

7.Follow the on-screen instructions to complete the WordPress installation, including creating an admin account and site title.


### Setting Up WooCommerce

1. Log in to your WordPress dashboard using the admin account you created.

2. Navigate to Plugins in the WordPress dashboard.

3. Search for WooCommerce and install the WooCommerce plugin.

4. Activate WooCommerce.

5. Follow the WooCommerce setup wizard to configure your online store, including payment gateways, shipping options, and product settings. Most of them are not required; you don't need to fill them out, so you can just skip the whole thing and go to the next section. I only recommend one thing, which is choosing some shipping option; without it, you won't be able to make an order.

### Creating WooCommerce API Keys

1. Log in to your WordPress dashboard.

2. Go to WooCommerce > Settings.

3. Click on the Advanced tab within WooCommerce settings.

4. Click on the REST API sub-tab.

5. Click the "Add Key" button to create a new API key.

6. Fill in the required information, such as description and permissions.

7. Click "Generate API Key."

8. The Consumer Key (wc_key) and Consumer Secret (wc_secret) will be generated. Make sure to copy and store them securely.

### How To Add Sample Products

 To add sample products to your site, you can follow the instructions on the [official WooCommerce website](https://woocommerce.com/document/importing-woocommerce-sample-data/).
