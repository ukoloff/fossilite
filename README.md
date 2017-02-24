# fossilite
SSH multi-user access to Fossil repos

## Hints

### Running Fossil

```sh
fossil sqlite3 -R repo "Replace Into user(login, pw, cap) Values('vasya', '!', 'g')"
fossil sqlite3 -R repo "Replace Into config(name, value) Values('remote_user_ok', 1)"
export REMOTE_USER=vasya
fossil http repo
```

### Groups

Group contains **two** lists:
included users and excluded ones.

In/excluding user to group:

Mode | Syntax
:---:| ---
  +  | user
  -  | -user *or* !user

In/excluding group to group:

Included|Excluded|Syntax
 :---:  |  :---: | ---
    +   |    +   | N/A
    +   |        | +@group
    +   |    -   | @group
        |    +   | +!@group
        |        | N/A
        |    -   | -!@group
    -   |    +   | !@group
    -   |        | -@group
    -   |    -   | N/A
