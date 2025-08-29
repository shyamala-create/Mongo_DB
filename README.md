# Mongo_DB
Queries for databse

# Mongo_DB
Queries for database

## to create a db
- use Zenclass

## to insert one, many data inside the user collection
- db.users.insertOne({name: "shyamala"})
- db.users.insertMany({name: "sangavi"}, {name: "Banu"}, {"selvaraj"})

## to find all the datas inside the user collection
- db.users.find();

## querying in database
## limit
- db.users.find().limit(2);
## filter 
## sorting 1 => ascending, -1 => descending
- db.users.find().sort({name: 1}).limit(2)
## skip
- db.users.find().skip(1).limit(2)

## query to find the particular datas inside particular document
- db.users.find({name: "Gokul"}, {name: 1, age, 1})

## if i don't want to the data inside the document to give 0 to the data 
- db.users.find({name: "Gokul"}, {_id: 0, name: 1})

## complex queries
## $eq => equalTo
- db.users.find({name: {$eq: "shya"}})
## $ne => not equal to
- db.users.find({name: {$ne: "shya"}})
## $gt => greater than
- db.users.find({age: {$gt: 25}})
## $gte => greater than or equal to
- db.users.find({age: {$gte: 25}})
## $lte => less than or equal to
- db.users.find({age: {$lte: 25}})
## $in => if we need to find the data's we use $in: []
- db.users.find({name: {$in: ["shya", "bans"]}})
## $nin => not in
- db.users.find({name: {$in: ["shya", "bans"]}})

## $exists true or false
- db.users.find({age: {$exists: true}})

## $exists two in one query
- db.users.find({age: {$gt: 20, $lt:60}, name: "shya})

## operations in db
## AND - $and
- db.users.find({$and: [{age: 54, name: bans} ]})
## OR - $or
- db.users.find({$or: [{age: 20, name: ""bans}]})
 ## not - $not
db.users.find({age: {$not: {$lt: 30}}})

## comparing two fields $expr
- db.users.find({$expr: {$gt: ["$debt", "$balance"]}})
 ## getting access to the data inside the data
- db.users.find({"address.street": "bagavanNagar"})


## find one, get the 1st element from the result
-db.users.findOne({age: {$gt: 10}})

## to get number of documents matching the exact query
- db.users.countDocuments({age: {$gt: 20}})


## Updating the data inside the document
- $set - it is an atomic operator to update the particular document
- eg: db.users.updateOne({age: 54}, {$set{age: 34}})
- $inc - increment the property
- $rename - renaming the key inside the document 
- $push - add the element in the array
- $pull - to remove the element in the array
- $unset - to delete the particular property inside the array

## updateMany
## replaceOne - replace the entire thing with the new value

## delete 
## deleteOne
## deleteMany
