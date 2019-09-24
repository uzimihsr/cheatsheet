# MySQL cheatsheet

## user
```
# username, hostnameの権限を確認
# hostnameを%に替えるとホストに関係なく情報がみられる
SHOW GRANTS FOR 'username'@'hostname';

# ログイン中のユーザの権限確認
SHOW GRANTS;
```
