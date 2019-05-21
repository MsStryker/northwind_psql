# Docker Northwind Database Container for Postgres

Create a [northwind](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/linq/downloading-sample-databases) 
database in a docker container, adapted for PostgreSQL.

**NOTE:** This setup is **NOT** suitable for a production environment. This is only suitable
as an example and allow you to practice your SQL knowledge. Why? Username and password should
never be checked into source control, but they are here for simplicity.

## Entity Relationship Diagram (ERD)

The initial ERD for Microsoft SQL is as follows:

![Entity Relationship Diagram Microsoft SQL](assets/ERD_SQL_Initial.png)
*SQL ERD*

Some modifications have been made for PostgreSQL and they are as follows:

![Entity Relationship Diagram](assets/ERD.png)
*PostgreSQL ERD*


## Requirements

- [Docker](https://www.docker.com/get-started)

## Installation

```bash
$ docker-compose up
```

Once installed you should be able to go to the `Adminer` page at http://localhost:8080, where
you should see the login.

![Adminer Login Page](assets/adminer_login.png)
*Adminer Login Page*

You should enter the environment variables you have specified in your `docker-compose.yml` to login.

## Inner Join

```postgresql
SELECT orders.order_id, customers.contact_name
  FROM orders
  INNER JOIN customers ON orders.customer_id = customers.customer_id;
```
