---
layout: post
title:  "Install and config PostgreSQL on CentOS 6"
date:   2016-06-23 22:31:07 +0800
categories: CentOS PostgreSQL
---

## Install PostgreSQL

1. Install PostgreSQL yum repository.
    ```
    yum install http://yum.postgresql.org/9.4/redhat/rhel-6-x86_64/pgdg-redhat94-9.4-1.noarch.rpm
    ```

2. Install and initialize PostgreSQL
    ```
    yum install postgresql94-server postgresql94-contrib
    service postgresql-9.4 initdb
    chkconfig postgresql-9.4 on
    service postgresql-9.4 start
    ```

2. Configure PostgreSQL

    ```
    su - postgres
    psql
    ```

    ```SQL
    # create database named 'book'
    CREATE DATABASE book;

    # create user named 'tom' with password 'password'
    CREATE USER tom WITH PASSWORD 'password';

    # grant user tom all privileges on database book
    GRANT ALL PRIVILEGES ON DATABASE book TO tom;

    # quit
    \q
    ```
