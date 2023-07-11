Postgres Psql Common Operations Demo
================================

```
brew install postgresql
```

```
pg_ctl init -D ./db
pg_ctl -D ./db -l logfile start
psql postgres
```

```
create user "demo";
create database "postgres-psql-common-operations-demo";
alter user "demo" with encrypted password '123456';
grant all privileges on database "postgres-psql-common-operations-demo" to "demo";
```

```
\l
\c "postgres-psql-common-operations-demo"


create table users
(
	id serial not null
		constraint users_pk
			primary key,
	username text,
	email text
);

alter table users owner to demo;

\dt

insert into users (id, username, email)
values (default, 'aaa', 'aaa@test.com');

select * from users;
```

```
drop table users;

\c postgres

drop database "postgres-psql-common-operations-demo";
```

