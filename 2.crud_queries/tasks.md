1. Create a database named `blog`.

use blog

2. Create a collection called 'articles'.

db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields

db.articles.insert({_id : 1, title : "article1", author : "Sanjib Roy", tags : ["art1Tag1","alt1Tag2"], details : "abcd")
db.articles.insert({_id : 2, title : "article2", author : "Aritra Roy", tags : ["art2Tag1","altT2ag2"], details : "mnop"})
db.articles.insert({_id : 3, title : "article3", author : "Reettik", tags : ["art3Tag1","alt3Tag2"], details : "wxyz"})

4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find()

5. Find a document using _id field.

db.articles.find({_id : 1})

6. Find documents using title and author's name field.

db.articles.find({title : "article2", author : "Aritra Roy"})

7. Find document using a specific tag.

db.articles.find({tags : "art1Tag1"})

8. Update title of a document using its _id field.

db.articles.update({_id : 1},{$set : {title : "first"}})

9. Update a author's name using article's title.

db.articles.update({title : "art1"}{$set : {author : "Sanjib"}})

10. rename details field to description from articles collection. 

db.articles.update({_id : 1},{$rename : {details : "description"}})

11. Add additional tag in a specific document.

db.articles.update({_id : 2}{$push : {tags : "newTag"}})

12. Update an article's tags using $set and without $set.
  - Write the differences here ?

13. Increment an auhtor's age by 5.  

db.articles.update({_id : 1}{$inc : {age : 5}})

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

db.articles.remove({_id : 1})

Use sample.js data for below queries.

1. Find all males who play cricket.

db.users.find({gender : "male"} && {sports : "cricket"})

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

db.users.update({name : "Steve Ortega" },{$push : {sports : "golf"}})

3. Find all users who play either 'football' or 'cricket'.

db.users.find({sports : "football" || "cricket"})

4. Find all users whose name includes 'ri' in their name.

db.users.find({name : /\w*ri\w*/ig})