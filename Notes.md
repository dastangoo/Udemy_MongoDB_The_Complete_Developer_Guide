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
db.users.find({phone: {$type: "number"}}).pretty()
db.users.find({phone: {$type: "double"}}).pretty()
db.users.find({phone: {$type: ["double", "string"]}}).pretty()
db.movies.findOne()
db.movies.find({summary: {$regex: /musical/}}).pretty()
db.sales.find({$expr: {$gt: ["$volume", "$target"]}}).pretty()
db.sales.find({$expr: {$gt: [{$cond: {if: {$gte: ["$volume", 190]}, then: {$subtract:["$volume", 10]}, else: "$volume"}}, "$target"]}}).pretty()
db.users.find({hobbies: {title: "Sports", frequency: 2}}).pretty()
db.users.find({"hobbies.title": "Sports"}).pretty()
db.users.find({hobbies: {$size: 3}}).pretty()
db.moviestarts.find({genre: ["action", "thriller"]}).pretty()
db.moviestarts.find({genre: {$all: ["action", "thriller"]}}).pretty()
db.users.find({$and: [{"hobbies.title"}, {"hobbiles.frequency": 2}]}).pretty()
db.users.find({$and: [{"hobbies.title"}, {"hobbiles.frequency": {$gt: 2}}]}).pretty()
db.users.find({hobbies: {$elemMatch: {title: "Sports", frequency: {$gte: 3}}}}).pretty()
db.movies.find().count()
db.movies.find().pretty()
db.movies.find().next()
const dataCursor = db.movies.find()
dataCursor.next()
dataCursor
dataCursor.forEach(document => {printjson(document)})
dataCursor.next()
dataCursor.hasNext()
C
db.movies.find().sort({"rating.average": -1}).pretty()
db.movies.find().sort({"rating.average": 1}).pretty()
db.movies.find().sort({"rating.average": 1, runtime: -1}).pretty()
db.movies.find().sort({"rating.average": 1, runtime: -1}).skip(10).pretty()
db.movies.find().sort({"rating.average": 1, runtime: -1}).skip(10).limit(10).pretty()
db.movies.find({name: 1, genres: 1, runtime: 1, rating: 1, _id: 0}).pretty()
db.movies.find({name: 1, genres: 1, runtime: 1, "rating.average": 1, _id: 0}).pretty()
db.movies.find({genres: "Drama"}, {"genres.$": 1}).pretty()
db.movies.find({genres: "Drama"}, {genres: {$elemMatch: {$eq: "Horror"}}}}).prety()
db.movies.find({"rating.average": {$gt: 9}}, {genres: {$slice: 2}, name: 1}).pretty()
db.movies.find({"rating.average": {$gt: 9}}, {genres: {$slice: [1,2]}, name: 1}).pretty()
db.users.updateOne({_id: <object_id>},{$se: {hobbies: [title: "Sports", frequency: 5], {title: "Cooking", frequency: 3}, {title: "Hiking", frequency: 1}}})
db.users.updateMany({"hobbies.title": "Sports"}, {$set: {isSporty: true}})
db.users.updateOne({name: "Jake"}, {$inc: {age: 1}})
db.users.updateOne({name: "Jake"}, {$inc: {age: 1}, $set: {isSporty: false}})
db.users.updateOne({name: "Jake"}, {$min: {age: 35}})
db.users.updateOne({name: "Jake"}, {$max: {age: 35}})
db.users.updateOne({name: "Jake"}, {$mul: {age: 1.1}})
db.users.updateMany({isSporty: true}, {$set: {phone: null}})
db.users.updateMany({isSporty: true}, {$unset: {phone: null}})
db.users.updateMany({}, {$rename: {age: "totalAge"}})
db.users.updateOne({name: "Jerome"}, {$set: {age: 23}}, {upsert: true})
db.suers.find({$and: [{"hobbies.title": "Sports"}, {"hobbies.frequency": {$gt: 3}}]}).pretty()
db.users.find({hobbies: {$elemMatch: {title: "Sports", frequency: {$get: 3}}}}).pretty()
db.users.updateMany({hobbies: {$elemMatch: {title: "Sports", frequency: {$gte: 3}}}}, {$set: {"hobbies.$.highFrequency": true}})
db.users.find({"hobbies.frequency": {$gt: 2}}).pretty()
db.users.find({"hobbies.frequency": {$gt: 2}}).count()
db.users.updateMany({"hobbies.frequency": {$gt: 2}}, {$set: {"hobbies.$.goodFrequency": true}})
db.users.find({totalAge: {$gt: 20}}).pretty
db.users.updateMany({totalAge: {$gt: 30}}, {$inc: {"hobbies.$[].frequency": -1}})
db.users.find({"hobbies.frequency": {$gt: 2}}).pretty()
db.users.updateMany({"hobbies.frequency": {$gt: 2}}, {$set: {"hobbies.$[el].goodFrequency": true}}, {arrayFilters: [{"el.frequency": {$gt: 2}}]})
db.users.updateOne({name: "Jake"},{$push: {hobbies: {title: "Sports", frequency:2}}})
db.users.updateOne({name: "Jake"}, {$push: {hobbies: {$each: [{title: "Sports", frequency: 2}, {title: "Hiking", frequency: 2}], $sort: {frequency: -1}, $slice: 1}}})
db.users.find({name: "Jane"}).pretty()
db.users.updateOne({name: "Jane"}, {$pull: {hobbies: {title: "Cars"}}})
db.users.updateOne({name: "Jeffrey"}, {$pop: {hobbies: 1}})
db.users.updateOne({name: "Jake"}, {$push: {title: "Hiking", frequency: 2}})
db.users.deleteOne({name: "Jake"})
db.users.deleteMany({age: {$gt: 30}, isSporty: false})
db.users.deleteMany({age: {$exists: false}, isSporty: false})
db.users.deleteMany({})
db.users.drop()
db.dropDatabase()
mongoimport 125\ persons.json -d contactData -c contacts --jsonArray
db.contacts.findOne()
db.contacts.find({"dob.age": {$gt: 60}}).pretty()
db.contacts.find({"dob.age": {$gt: 60}}).count()
db.contacts.explain().find({"dob.age": {$gt: 60}})
db.contacts.explain("executionStats").find({"dob.age": {$gt: 60}})
db.contacts.createIndex({"dob.age": 1})
db.contacts.dropIndex({"dob.age": 1})
db.contacts.createIndex({gender: 1})
db.contacts.explain("executionStats").find({gender: "male"})
db.contacts.dropIndex({gender: 1})
db.contacts.createIndex({"dob.age": 1, gender: 1})
db.explain().find({"dob.age": 35, gender: "male"})
db.explain().find({gender: "male"})
db.explain().find({"dob.age": 35}).sort({gender: "male"})
```
