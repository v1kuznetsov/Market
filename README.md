# Market

This project is my final task in BranderSchool on knowledge PHP, Symphony, Twig, Docker and Composer

## Installation

In the console, write:

```bash
    sudo docker compose up -d
```

\*If you have problems starting the MySQL and nginx containers, try:

```bash
    sudo service nginx stop
    sudo service mysql stop
```

In the same window write:

```bash
    sudo docker exec -it php-fpm bash

```

In the opened PHP container, write:

```bash
    composer install
    php bin/console doctrine:database:create
    php bin/console doctrine:migrations:migrate
```

Open a new console window and write:

```bash
    sudo docker exec -it mysql bash
```

Then write in the MySQL container:

```bash
    mysql -uroot -p
```

In the window that appears, write:

```mysql
    root
```

While in database, write:

```bash
    use market_test;
```

## Usage

After registration on the store page, add administrator rights to the desired user:

```bash
    update user set roles = JSON_OBJECT('admin', 'ROLE_ADMIN') where id=(your user number in the user table);
```

After this, an admin panel tab will appear in the header, accessible only to the administrator, from which you can add categories and products.

## License

[MIT](https://choosealicense.com/licenses/mit/)
