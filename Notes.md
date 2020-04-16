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
```
