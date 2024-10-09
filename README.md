# Setup Drupal 11 on locally using MAMP and Composer on macOS

## Development Environment

* MacOS Sequoia 15.0.1
* MAMP PRO 7.1
  * Apache 2.4.58
  * PHP 8.3.10
  * MySQL 8.0.35
* Composer 2.8.1

## Steps

1. Install [MAMP](https://www.mamp.info/en/windows/).

2. Install [Composer](https://getcomposer.org) using `Homebrew`.

   ```bash
   brew composer
   ```

3. Set ports on MAMP (Option).

   Default ports are `Apache port: 8888`  and  `MySQL  port: 8889`, or set port to  `Apache port: 80` and  `MySQL  port: 3306`.

4. Open `Terminal` and navigate to document root.

   for MAMP PRO, path is `/Users/YOUR USER NAME/Sites`.

   for MAMP, path is `/Application/MAMP/htdocs`.

5. Create an initial Drupal project using composer ([Using Composer to Install Drupal and Manage Dependencies](https://www.drupal.org/docs/develop/using-composer/manage-dependencies)).

   ```bash
   composer create-project drupal/recommended-project your-project-name
   ```

6. Set document root on MAMP to `/Users/your-user-name/Sites/your-project-name/web` or `/Application/MAMP/htdocs/your-project-name/web`.

7. Start servers on MAMP.

8. Create a database from command line. Or using `phpMyAdmin` ([Create a database](https://www.drupal.org/docs/getting-started/installing-drupal/create-a-database)).

   ```bash
   /Applications/MAMP/Library/bin/mysql -u root -p
   ```

   ```mysql
   mysql> CREATE DATABASE your_database CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
   ```

9. Create a user for database. Or using existing user and set privileges up).

   ```mysql
   mysql> CREATE USER your_user@localhost IDENTIFIED BY 'your_password';
   mysql> GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES ON your_database.* TO 'your_user'@'localhost' IDENTIFIED BY 'your_password';
   mysql> FLUSH PRIVILEGES;
   ```

10. Open http://your-host-name and following the steps to install Drupal.
