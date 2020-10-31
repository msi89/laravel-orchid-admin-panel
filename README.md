## About Orchid Laravel

Laravel Orchid is an open-source package (MIT license) to speed up development and create applications in the style of administration. It abstracts typical business application templates so that developers can quickly implement beautiful and elegant interfaces with little effort.

Some features:

-   **Form builder** - no need to describe HTML fields of the same type each time.
-   **Screen** - a comfortable balance between CRUD generation and tedious coding.
-   **Fields** - over 40 varieties.
-   **Permissions** - offers convenient management in development and support.
-   Menus, charts, notifications, etc.

[documentation](https://orchid.software/en/docs/)

## Installation

rights to the `storage` and `bootstrap/cache` directories

```bash
chmod -R o + w  storage
chmod -R o + w  bootstrap/cache
```

Add dependency

```bash
composer require orchid/platform
```

_Note._ If you just installed Laravel, you may need to generate a key with `command php artisan key:generate`

Note. You also need to create a new database, update the `.env` file with credentials, and add your application's URL to the variable `APP_URL`.

#### Platform installation

**Note.** The installation will overwrite the `app/Models/User model`.

Run the installation process by running the command:

```bash
php artisan orchid:install
```

#### Create admin user

To create a user with maximum permissions, you can run the following command with a `username`, `email`, and `password`:

```bash
php artisan orchid:admin admin admin@test.com password
```

#### Start local server

If you haven't installed a server (Nginx, Apache, etc.) to run the project, you can use the built-in server:

```bash
php artisan serve
```

Open a browser and go to `(http://localhost:8000/admin)`. If everything works, you will see the control panel login page. Later you can stop the server by pressing `Ctrl + C` in the terminal.

#### Publishing resources

By default, static files (css / js) are delivered via app routes. It is the best balance between configuration and change tracking, but you can specify web servers for distribution. To do this, you need to run a command that creates a symbolic link in the public directory. Please only use it if your web server is having problems:

```bash
php artisan orchid:link
```

#### Updating

While in the project directory, use `Composer` to update the package:

```bash
composer update orchid/platform --with-dependencies
```

**Note.** You can also update all your dependencies listed in the `composer.json` file by running `composer update`.
