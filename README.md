# Mongodb_Commands

Here's how to create a basic database, a collection (equivalent to a table in relational databases), and insert data into MongoDB.

1. Start the MongoDB Shell
   ```
    mongosh
   ```
2. Create a Database /  Switch to the Database
    ```
    use my_database
   ```
3. Create a Collection
    ```
    db.createCollection("users")
   ```
4. List Collections
     ```
    show collections
   ```
5. Access the Collection
     ```
    db.users
   ```
6. Insert Data
    ```
    // Insert One
    db.users.insertOne({
    username: "john_doe",
    email: "john.doe@example.com",
    password: "securepassword123"
    })

    // Insert Many
    db.users.insertMany([
    { username: "alice", email: "alice@example.com", password: "password1" },
    { username: "bob", email: "bob@example.com", password: "password2" },
    { username: "charlie", email: "charlie@example.com", password: "password3" }
     ])
    ```
7. Query the Data
     ```
    db.users.find()
     
   // Find all users with the username alice:
    db.users.find({ username: "alice" })
     
    // Count the Documents:
     db.users.countDocuments()

    // Display Results in a Readable Format:
     db.users.find().pretty()

   ```
8. Update Data
     ```
    db.users.updateOne(
   { username: "alice" }, // Filter
   { $set: { email: "alice.new@example.com" } } // Update
   )
   ``
9. Delete Data
     ```
     // To delete a specific user:
       db.users.deleteOne({ username: "bob" })
     //To delete all users:
       db.users.deleteMany({})

   ```
Example Workflow
```
use my_database

db.createCollection("users")

db.users.insertMany([
  { username: "alice", email: "alice@example.com", password: "password1" },
  { username: "bob", email: "bob@example.com", password: "password2" },
  { username: "charlie", email: "charlie@example.com", password: "password3" }
])

print("All Users:")
db.users.find().forEach(user => printjson(user))

```
