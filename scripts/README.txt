==================================VM_IP_ADDRESS================================
user    ->  student6
back1   ->  192.168.1.64
back2   ->  192.168.1.107
db1     ->  192.168.1.24
db2     ->  192.168.1.136

====================================DEPLOYMENT=================================
--------------------------------------Backend----------------------------------
1.  Copy on back-VM first_configure.sh, user_configure.sh and basic_configure.sh
2.  Launch first_configure.sh
    a.  user_configure.sh
    b.  basic_configure.sh

3.  cd $PROJECT_DIR/server/scripts (PROJECT_DIR value see in basic_configure.sh)

4.  Launch nginx_configure.sh

5.  Launch wsgi_configure.sh

6.  Create file $PROJECT_DIR/server/src/config.json
    Example of configuration file:
    {
        "DATABASES": [
            {
                "host": "<ip_address>",
                "user": "<user_name>",
                "password": "<password>",
                "db": "<db_name>"
            },
            {
                "host": "<ip_address>",
                "user": "<user_name>",
                "password": "<password>",
                "db": "<db_name>"
            }
        ]
    }

7.  Restart services:
    -   necessarily: uwsgi(necessarily),
    -   optionally: nginx.

--------------------------------------Database---------------------------------
1.  Copy on db-VM first_configure.sh, user_configure.sh and basic_configure.sh

2.  Launch first_configure.sh
    a.  user_configure.sh
    b.  basic_configure.sh

3.  cd $PROJECT_DIR/server/scripts (PROJECT_DIR value see in basic_configure.sh)

4.  Launch mysql_configure.sh
    a.  Change root password for mysqld@instance01, mysqld@instance02
    b.  Creates databases and users
    c.  Make remote access to mysqld@instance01, mysqld@instance02
