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
```
