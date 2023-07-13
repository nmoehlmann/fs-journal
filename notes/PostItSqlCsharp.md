configure env and startup.

Create a table for albums one is already set up for accounts.

when putting in the creatorId that references another id in another table, they need to have the same datatype.

if tables are going to talk to eachother the table set needs to be the same. default charset utf8 COMMENT as example

create FOREIGN KEY that references the id of the other table

This is creating a CONSTRAINT which is different from a virtual.

# note: primary key tells sql that its special row in which the row identifies itself as.

# note: you cannot delete a row that references other data to prevent you from creating orphan data.

add a hook to foreign key constraint. ON DELETE CASCADE. this will delete everything that references this data.

If you select data from multiple different tables and join the data it will give back all that data.

Create the album model. your allowed to put in Account which references your account model

create album repo.
create album service.
create album controller.

# album controller

start with creating a post request in the controller.

[Authorize] on top will not allow you to access this route until you are logged in.

the post request must be async because its making a request to a third party api auth0

Account userInfo = await

because we are bringing in auth0provider service we must create another readonly for that service.

HttpContext is the req that we are sending to the server.

for the async post request, you must return Task<ActionResult<>Album>. This is NECESSARY for async requests. Its like a promise, which means it will keep the command alive until the promise returns something.

# album service

creating string sql for the sql command to post

the way we select the one we created is by using LAST_INSERT_ID() to grab the one that we created last.

# note: we dont async our own database because we have a direct connection. we dont have that connection to external apis. we are just making requests to them.

To populate the creator, we must add a select and join account that created it to the table.

dapper is trying to take all the data it gets back from both tables and push them into the album model.

when we Query, we need to make sure its not just using Album. It is Album, Account. Dapper knows that the tables coming back are separated by the id.

We must also declare a return type. looks like this: <Album, Account, Album>.

The order in which the album and account models come in MATTERS!

# get all albums

create a get all albums in the controller
get all albums in service
get all albums in repo

When your trying to return a list, you must .ToList().

 # get album by id

 create album by id in the controller
 service
 repo

We give dapper the albumId by giving it in the form of a function so that it can use it.

We make that an object so that it gives it a key value pair so dapper knows what it is. albumId by itself is just a number new {albumId} is albumId = number.

# delete album

conroller
service
repo

service stuff
first grab album by id
flip archived bool

repo stuff
when we set the values in the album we Execute.
execute returns an int of how many rows were affected / changed / updated

# PICTURES

create the pictures table
Foreign keys need to be wrapped in parantheses

create picture model
In c# you usually start in uppercase. This is industry standard.


We simply name it _repo because a service will only ever talk to its own repo. This means if you are doing something in another service, you arent going to go into a different repo, you are going to go into the service that the repo is associated with before you go into that repo. SERVICES NEVER TALK TO ANY REPO THAT ISNT ITS OWN.

the _picturesService = picturesService is basically making the readonly useable in the rest of the file. Its a constructor that makes it useable.

repo
service
controller

Create post method in the controller
We will need to access auth0 provider service, so we create readonly and then add the extra logic into our create picture method.

create post method in service
can make it short by returning it directly. return _repo.CreatePicture(pictureData) // this is shorter but can be hard to debug.

create post method in repo
start with string sql = @""

JOIN accounts a ON a.id = pic.creatorId: basically joining single account where the account id is = to the creator id.

You can alias the shit out of everything in C# kinda wacky

After inserting and selecting through the sql, we use a Query.
sql, (picture, creator) these are aliased out from the models passed through the initial Query.

GO ADD SCOPED SERVICES AND REPOS IN THE STARTUP OR POSTMAN WILL NOT WORK.

# get pictures

we create the super in the http on top of the actual method
The brackets for ids are similar to the colon which is the key of the actual value being passed through.

We add the pictures service to the albums controller. This is because we are requesting pictures by albumId which we get from the albums controller.

create get pictures in the pictures service nothing crazy
create get in repo

start with sql =@""
join the account who is the creator
select picture albumId that is equal the the one we are passing through

now we Query the db and return a List.
When we pass through the albumId we need to provide it as an object so that it is given a KEY VALUE pair. otherwise it will just be a number and dapper does not know what to do with that.

# delete picture

create delete method in controller
make sure to put authorize under post and delete. Anything that would require an account

create delete method in service
this will be an internal void because its destructive.

We want to get the picture by id so we create another method for getting by id.
we null check for validity.
we create the get by id method in the repo
NOW we can finish the delete method. and we have get by id method to call to if we implement that into our app

create delete method in repo now.
start with sql=@""
we put a limit 1 at the end of the delete for safety. it will never delete more than 1 thing.
because we are deleting we use an execute and then return rows because execute returns a number of rows that are affected.

# collaborators

Create collaborator table.
has a foreign key for the account attached and the album collaborated with.
join account and join album
when we join it basically joins all those tables separated by their ids.

create collaborator model
we have the collab id
account id associated
and album id the collaborator is collaborating with

we need to create a view model. this is what we use to map data from our table to the data that we see and use on the front end.

we create classes that extend the base classes of account and album.

CollaboratorAccount and CollaboratorAlbum which extend from their base models.
Its nothing new just a way to set up virtuals for the front end.

# NOTE: Its best practice for the extension models to be placed in the model its extending from.

repo
service
controller

create post in controller. make sure its authorized.
get userInfo from auth0 service. make sure the accountId in the collabData is equal to the userInfo id returned from Auth0

# collab repo stuff
start with sql=@""
we are going to use ExecuteScalar instead of execute or query.
ExecuteScalar returns the LAST_INSERT_ID.

# many to many, joining and how we see views.

We arent going through different objects and digging into it to see objects associated with it.

# get request for albums by collaborator

getting back a list of albums because 1 collaborator can have many albums.

a collaborator has its own id. the account has ITS own id. these are two separate things except that the collaborator id is extended from the account model.

when we query we are using collaborator and collaboratorAccount. We are returning a collaboratorAccount.

remember that when you pass an id that is referenced by dapper we need to pass it as an object: KEY VALUE pair so that it recognized what it is and what value to use. If its passed as a number, it doesn't know what to do with it.

Ultimately, the collaborator id is there so that we have access to it. We can find it by id, we can delete it.

# get all my albums that I collaborated on

We need to use the Auth0 provider for access to our userInfo. Remember that HTTPcontext is basically the req that gets sent to the server.

We are going to try and get a collaborator and then populate the albums its a little wacky wild.
It actually makes sense because all we are doing is getting OUR collaborator and then populating all the albums associated with its id. Thats big brain.

We need to populate the creator as well. this means we need to add the logic to our sql so that we are joining the act who's id matches the creatorId of the album.

# delete collaborator

controller
use auth0 to verify if you are authorized to delete.

service
Write out get by id function so its accessible.
auth check