# The Witcher 3 Beastiary API 🐺
A RESTFul API that provides the name, type, susceptibility, and loot drops of each monster.
## Usage
This API uses [Express](https://expressjs.com/) for routing endpoints and [DynamoDB](https://aws.amazon.com/dynamodb/) to store and retrieve each monster.
The server returns a **JSON object** of each monster's information as a response.

### Getting Monsters

You can get all monsters, all monsters under a specific category (type), or a single monster. You can simply do all of these by specifying the endpoint. 

**Examples:**
* http://localhost:3000/monsters - returns all of the monsters.
* http://localhost:3000/monsters/Beasts - returns all of the monsters under the ***Beasts*** category.
* http://localhost:3000/monsters/Beasts/Bear - only returns the information for ***Bear***, which is under the ***Beasts*** category.

> For types and/or names with spaces, use underscores. For instance:<br>
> http://localhost:3000/monsters/Cursed_Ones/The_Toad_Prince


### Adding, Updating, and Deleting Monsters

For adding and updating, the server takes the request's body (a JSON object) and sends it to the database. For deleting, you just have to specify the monster's id in the URI.

**Examples:**
* http://localhost:3000/monsters/add - adds a new monster using a put request's body, takes a JSON object.
* http://localhost:3000/monsters/update/2 - updates the monster with an ***id*** of ***2*** using a put request's body, takes a JSON object.
* http://localhost:3000/monsters/delete/5 - deletes the monster with an ***id*** of ***5***.
