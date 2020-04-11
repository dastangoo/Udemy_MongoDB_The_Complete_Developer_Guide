```bash
brew tap mongodb/brew
brew install mongodb-community@4.2
mongod --config /usr/local/etc/mongod.conf
brew services start mongodb/brew/mongodb-communit
mongo
mongod --dbpath <db_path>
vim /usr/local/etc/mongod.conf
```
