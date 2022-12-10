# actions-setup-mysql

This action sets by MySQL database for use in actions by:

- download a version of MySQL or MariaDB
- start mysqld

## Usage in Workflow file

```yaml
- name: Setup MySQL 8
      uses: karimz1/actions-setup-mysql@v1.14.1.1
      with:
        mysql-version: '8.0.31'
        my-cnf: |
          innodb_log_file_size=256MB
          innodb_buffer_pool_size=512MB
          max_allowed_packet=16MB
          max_connections=50
          local_infile=1
```

Sample how you can access the mysql action service in your application (appConfigSample.json)

``appConfigSample.json``
``` json
{
 "mysqlconnectionString": "server=localhost;port=3306;uid=root;pwd=;database=DbName;"
}
```

Login:
  - User: `root`
  - Pass: ``(Leave it empty like in the appConfigSample.json)``
  - Port: ``3306``

## Configuration

### `mysql-version`

The version of MySQL or MariaDB.

Available Versions are:

- MySQL
    - `8.0`
    - `5.7`
    - `5.6`
- MariaDB
    - `10.9`
    - `10.8`
    - `10.7`
    - `10.6`
    - `10.5`
    - `10.4`
    - `10.3`
    - `10.2`
    
    

# Credits 
This is a fork from [shogo82148](https://github.com/shogo82148/actions-setup-mysql) to create custom mysql releases, for learning purposes.
