# configuring PostgreSQL in Heroku

1. **provisioning heroku-postgresql addon in heroku.**

```text
heroku addons:create heroku-postgresql:<PLAN_NAME>
```

&lt;PLAN\_NAME&gt;:use **hobby-dev** for a free plan. after provisoning, heroku will add a DATABASE\_URL config var to your app's configuration, which can be confirmed by command

```text
heroku config
```

2. **create table from sql file.**

First, run the following to get your database's name

```text
heroku pg:info --app <name_of_app>
```

In the output, note the value of "Add-on", which should look something like this:

```text
Add-on:                postgresql-angular-12345
```

Then, issue the following command:

```text
heroku pg:psql <Add-on> --app <name_of_app> < my_sql_file.sql
```

For example \(assuming your sql commands are in file test.sql\):

```text
heroku pg:psql postgresql-angular-12345 --app my_cool_app < test.sql
```



### reference:

{% embed url="https://devcenter.heroku.com/articles/heroku-postgresql\#provisioning-heroku-postgres" %}

{% embed url="https://stackoverflow.com/questions/48180282/how-to-populate-a-heroku-postgresql-database-with-a-sql-file" %}



