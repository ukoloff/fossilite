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
