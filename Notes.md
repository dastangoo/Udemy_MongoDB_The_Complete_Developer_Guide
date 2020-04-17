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
```

