# Step by Step kinda:

## Server

bcw-create express vue

enter the workspace

setup env.js and .env for client and server

verify everything is connected via the network in dev tools

starts with the model Album.js he is making a schema

creatorId is tied to Account with an objectId in the model

we create a virtual for album that shows the creator of the model

go to DbContext and make albums

makes a album service and controller

because we cant test things without content inside the database, naturally we have to POSt and PUT things before we GET things.

adds a post with a .use as middleware to prevent unauthorized users from making post requests.

we want the creatorId to equal the userId we do that in the post function

make sure to populate the album with creator, which we made a virtual for in the model.

now that we can POST we want a GET to find all albums, and albums by id

create an archiveAlbum function that flips a bool when a album is "deleted".

we are changing album.archived in the database, so we do album.save(). telling the database that we changed it i think


Now we make a picture model

put picture model in dbcontext to connect it to database

make picture service and controller

like the albums, the first thing we need to do in order to test things is create a POST request for GET.

equal creatorId to userInfoId in controller

create function inside service using pictureDate

cannot read properties of undefined (reading id) this means that the thing giving the error isnt id, its whatever is before it!

create a virtual for it and then populate it

now we create find albumsByPictures. where albumId: param = albumId: albumId in each picture

populate creator on here too

server done i guess


## Client

when you fork code and clone it, you need to setup the env stuff every time.

 creates Album model. creates Account model extends Profile.

 makes picture model, does all this because we know what we are getting back from the server we created.

 new Profile(data.creator) in model this will give more intelisence.

 creates services for everything

 getAlbums function. onMounted so it does things on page load.

 writes getAlbums on service. map res.data to albums in AppState.

 make a computed for albums in the AppState. this accesses data in AppState.

 Starts making template on HomePage. abstracts album template to AlbumCard component

 put AlbumCard in HomePage and then v-for it. bind AlbumCard to a prop.

when passing in :album="a" im passing in each album it goes through when it does the v-for. If I had a single instance i could simply pass through the whole thing from the AppState.
ex: :profile="profile" "profile" is = to the activeProfile and can be passed through in its entirety because its on its own.

Set background image on App.vue because its going to be used on every page.

create router path for album by id.

create a routerview for each album on the homepage. to="the 'NAME' inside the router path". params: {id: albumId}

create AlbumDetailsPage for that router path.

getPicturesByAlbumId, getAlbumById. onMounted to run functions when page loads.

create a userRoute so that we are getting the route url and equalling it to a variable.

albums service and getAlbumById. we are passing in albumId with the useRoute method in the page i think.

create pictures service so we can run the get getPicturesByAlbumId function.

now that we are getting pictures we put it in the Appstate. we dont do activePictures because we are only ever getting pictures when we are in an album by Id.

we already made a picture model so when we map pictures into the AppState we use the instance of the model Picture. 

the style of having images stacked and staggered is called masonry

we make a reusable modal. we put in a slot to handle injecting content into the modal.

we put the modal in App.vue under the footer

we pass id="createAlbum" into the modal in App.vue

we make a createAlbum component which holds the modal form that shows up on page after clicking a button.

the modal exists on the App.vue. we have reusable modal in a component that has a slot. this slot can be used to pass through data on the page which displays specific forms.

inside the createAlbumForm component, we make the form inputs inside of the modals guts.

in the createAlbum function, we dont just use editable: we use editable.value.

createAlbum in service. pass in formData which is equal to editable.value.

we put a v-if on the create button so that it doesnt show up if you are not logged on.

we put a select into the form for categories. we put options into select with values.

reset form and editable.

inside the createAlbum function we write a router.push that takes us to the details page we posted.

router.push({name: 'AlbumDetials', params: {id: newAlbum.id}})

instead of putting elvis operators on everything, you can put a v-if="album" and null check the album


Now we make a create picture form component. we use the same modal slot with different guts.

make createPicture function.

inject PictureForm in the App.vue modal. need something to take up that slot in the modal template.

createPicture in picture service. make sure to pass through editable.value

we are missing albumId in the editable. so we assign albumId to the album we are currently on. we do this using route.

push the pictures into the AppState.


## back on the server

making a collaborator Schema

creating album virtual and account virtual for collaborator model
foreignField:
localField:
ref:
justOne:

make a collaborator service and controller

before you can post you need .use auth

make createCollaboration post

we dont trust the user to tell the server what they are: req.body.accountId = req.userInfo.id

handle post in service and make connection of collaborator in the database through dbContext

we also want to populate the virtuals we made in the service.

get findAlbumCollaborators: push into service

dbContext.Collaborators.find(albumId: albumId): we need to find all collaborators by albumId

we then need to populate it with the profile. We should never see someone elses account, only their profile

make getAccountCollaborations the many to many between your account and other collaborators. we are comparing your accountId with the collaborators accountid: .find{accountId: accountId}

then populate it with album

make the delete collaborator function. pass in req.params.collabId and req.userInfo.id

nullcheck if the collab is even their with if(!collab) throw new BadRequest yada yada

check if collab accountId is not = to userId which checks if the account is logged in.

populate album and profile when it finds collab

once it finds and checks then we use the remove function.

make a virtual tieing the member count. ref collaborator from database and foreign id albumId.


## back to the client

make a filter by = ref

all the filters which all have an @click on the homepage

albums is being computed using the filter.

filters by the albums category and pushes it into the AppState i think

we make a get function that gets MyCollabs the accounts collabs

make myCollabs in the AppState.

make a getCollabsByAlbumId

computed to grap collabs from AppState

because we dont know if profile or album are going to be populated, we need to make then || null in the model

make a new class called AlbumMember that is an extension ob the Collab.

then we make another class called CollabedAlbum that is also an extension from Collab.

basically creating two models that extend from Collab.

linking collab button to create collab: takes in albumId and posts.

the server is responsible for associating the account and the collaboration with the album.

Now we need to make a bool that checks if you are a collab so that the button can check and uncheck THIS IS COOL I THINK

we have a computed called isCollaborator: AppState.collabs.find(AppState.user.id)

isCollaborator will return true if it finds you, and false if not.

we use a v-if on the button to become a collaborator if that computed is false. then we make another button for when its true. epic.

make archive button work











