```bash
mongo
---
show dbs
use flight
show dbs
db.flightData.insertOnce({...})
db.flightData.find().pretty()
db.flightData.deleteOne({...})
db.flightData.deleteMany({...})
db.flightData.updateOne({}, {$set: {...}})
db.flightData.updateMany({}, {$set: {...}}) 
db.flightData.insertMany([...])
db.flightData.find({...}).pretty()
db.flightData.find({distance: {$gt: 900}})
db.flightData.update({...}, {...})
db.flightData.replaceOne({...}, {...})
db.passengers.insertMany([...])
db.passengers.find().pretty()
db.passengers.find().toArray()
db.passengers.find().forEach((passengerData) => {printjson(passengerData)})
db.passengers.find({}, {name: 1}).pretty()
db.passengers.find({}, {name: 1, _id: 0}).pretty()
db.passengers.findOne({name: "<someone>"}).hobbies
db.passentger.find({hobbies: "sports"}).pretty()
db.flightData.find({"status.description": "on-time"}).pretty()
db.flightData.find({"status.description.responsible": "on-time"}).pretty()
db.flightData.drop()
db.dropDatabase()
use shop
db.dropDatabase()
show dbs
use shop
db.products.insertOne({name: "A book", price: 12.99})
db.products.find().pretty()
db.products.insertOne({title: "T-Shirt", seller: {name: "John", age: 29}})
db.products.deleteMany()
db.products.find().pretty()
db.dropDatabase()
use companyData
db.companies.insertOne({...})
db.companies.findOne()
db.numbers.insertOne({})
db.numbers.findOne()
db.stats()
db.companies.drop()
show collections
db.numbers.drop()
db.numbers.insertOne({a: NumbertInt(1)})
db.stats()
typeof db.numbers.findOne().a
db.patients.insertOne({})
db.diseaseSummaries.insertOne({})
var dsid = db.patients.findOne().diseaseSummary
db.diseaseSummaries.findOne({_id: dsid})
db.patients.deleteMany({})
db.books.aggregate([{$lookup: {from: "authros", localField: "authors", foreginField: "_id", as: "creators"}}])
db.createCollection("posts", {<validator})
db.runCommand({collMod: "posts"}, <validator>)
---
mongod --fork --config /usr/local/etc/mongod.conf
ps aux | grep mongod
use admin
db.shutdownServer()
---
// On Windows
net start MongoDB
net start MongoDB
---
mongod --config /usr/local/etc/mongod.conf
mongod -f /usr/local/etc/mongod.conf
---
mongod --help | less
mongo --help | less
mongo --nodb
mongo --quiet
mongo
---
help
help admin
ls()
pwd()
hostname()
show dbs
use test
db.help()
show collections
db.posts.help()
db.stats()
db.posts.stats()
---
show dbs
user contactData
db.dropDatabase()
use test
db.dropDatabase()
show dbs
use contactData
db.persons.insertOne({
    name: "John",
    age: 30,
    hobbies: ["Sports", "Cooking"]
})
db.persons.find().pretty()
db.persons.findOne()
db.hobbies.insertMany([...], {ordered: true})
db.persons.insertOne({...}, {writeConcern: {w: 1, j: true, wtimeout: 200}})
---
mongoimport <path> -d <database> -c <collection> --jsonArray --drop
---
db.movies.find({runtime: 60}).pretty()
db.movies.find({runtime: {$eq: 60}}).pretty()
db.movies.find({runtime: {$ne: 60}}).pretty()
db.movies.find({runtime: {$le: 60}}).pretty()
db.movies.find({runtime: {$lte: 60}}).pretty()
db.movies.find({"rating.average": {$gt: 7}}).pretty()
db.movies.find({genres: "Drama"}).pretty()
db.movies.find({genres: ["Drama"]}).pretty()
db.movies.find({genres: ["Drama"]}).pretty().count()
db.movies.find({runtime: {$in: [30, 42]}}).pretty()
db.movies.find({runtime: {$nin: [30, 42]}}).pretty()
db.movies.find({$or: [{"rating.average": {$lt: 5}}, {"rating.average": {$gt: 9.3}}]}).pretty()
db.movies.find({$nor: [{"rating.average": {$lt: 5}}, {"rating.average": {$gt: 9.3}}]}).pretty()
db.movies.find({$and: [{"rating.average": {$gt: 9}}, {genres: "Drama"}]}).pretty()
db.movies.find({"rating.average": {$gt: 9}}, {genres: "Drama"}).pretty()
db.movies.find({genres: "Drama", genres: "Horror"}).count()
db.movies.find({$and: [{genres: "Drama", genres: "Horror"}]}).count()
db.movies.find({runtime: {$not: {$eq: 60}}}).count()
db.movies.find({runtime: {$ne: 60}}).count()
db.users.find({age: {$exists: true}})
db.users.find({age: {$exists: true, $ne: null}})
```
