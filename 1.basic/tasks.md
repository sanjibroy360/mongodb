#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..

use sports

2. list all databases present in local mongod server.
// Answer here..

show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.

db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

db.cricket.insert({name : "Sanjib Roy", age : 22, email : "sanjibroy0098@gmail.com"})
db.cricket.insert({name : "Aritra Roy", age : 22, email : "aritra@gmail.com"})
db.cricket.insert({name : "Reettik Goswami", age : 22, email : "reettik@gmail.com"})

db.football.insert({name : "Pratap Panda", age : 22, email : "pratap@gmail.com"})
db.football.insert({name : "Subham Das", age : 22, email : "subham@gmail.com"})
db.football.insert({name : "Mayank Agnihotri", age : 19, email : "mayank@gmail.com"})

db.TT.insert({name : "Rittik Karmakar", age : 22,  email : "rittik@gmail.com"})
db.TT.insert({name : "Shivsagar", age : 25,  email : "sagar@gmail.com"})
db.TT.insert({name : "Ashish Sharma", age : 24,  email : "ashish@gmail.com"})

5. list all collections in sports database.

show collections

6. rename `TT` collection to `tennis`.

db.TT.renameCollection('tennis',true)

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

db.createCollection('khokho',{capped : true, size : 1000000, max : 3})

8. check whether a collection is capped or not?

db.collection.isCapped('khokho')

9. remove all documents from `football` collection.

db.football.remove({})

10. delete cricket collection completely.

db.cricket.drop()

11. rename database sports to games

db.copyDatabase('sports','games','localhost')

12. delete sports database. 

use sports
db.dropDatabase()
