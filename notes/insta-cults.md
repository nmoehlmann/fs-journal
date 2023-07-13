created a dotnet-vue template
throw in connection string and auth0 credentials. env.js connection details
change the baseURL to use 7045 if using dotnet

we need cults and cult members
create cults table
create cult members table

quick creates:
create cults repo
create cults service
create cults controller

add scoped service and repo in startup so that files can recognize those files without having to import them.

create a cult model.
the created at and updated data types are DateTime.

Cult Controller post
create post request
create auth0 readonly

Cult Service post
create post request

Cult Repo post
start with sql as always. use @ for dapper.
we set the leader foreign object to the PROFILE of the account.

Cult Controller get cults
create get request
returning a list

Cult Service get cults
send straight to repo

Cult Repo get cults
as always, start with sql.
SELECT because its a get.

Cult Controller get by id
inside [HttpGet] we need the cultId being passed through from the front end
pass into service

Cult Service get by id
do a null check on the cult to see if it does not return anything from repo.

Cult Repo get by id
start sql
SELECT because its a get
JOIN the leader

# NEW search in c#

Cult Controller
create a search request that takes in the search value in url

Cult Service
getting back list. sending straight to repo

Cult Repo
LIKE is how sql deals with searches.
includes similar to.
WHERE cult.tags LIKE @search
search is the value inputted and is takes the where and compares everything associated with the value.
return search as an object and then ToList it.
search is the key and whatever is after that is the value.

# NEW getting views

create an alter table called popularity with integer data type
All we do to use this is add to the popularity every time the get by id function is executed.
it does not persist until its saved in the repository layer.

repo
going to make a new method because its an edit.
sql

Create cult members table
reference cult and account

create a cult member model
We want to use a separate account model so that we can keep the actual cultist id.

create cult members repo service and controller

# NOTE regarding sql c#

we cant simply populate the account inside the cult member model because the account is in an entirely separate table. The way sql database is stored is completely different from mongo db. its rows and columns and tables cannot interact with other tables without JOINING them.

# end

Cult Member create request

Cult Member get request
sql
We are passing through a cult member, we are passing through the account associated which is cult member id, and we are returning an account with the cult id association which is Cultist.

Cult Member delete request
we are passing in the cult member id, not the account id
need to get the cult member by id so that we can check if that member is authorized to delete.

string sql = @""

# FRONT END

Get cults function written on the home page.

# ez fix

router.js do beforeEnter: authSetteled. this will wait for the account to be authenticated before running the route.

# NOTE

create a cult member which is just a bunch of ids. we cannot populate the account on this with sql

now that we have the cult member, we want to display the account. BUT WE DONT HAVE AN ACCOUNT.

we create a new view (extended class of account) and put the cult member id on it.

NOW we have access to the cult member id AND the account details. we can delete this cult member because we have access to this through the extended account class called CULTIST

:()