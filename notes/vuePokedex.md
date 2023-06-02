# homepage.vue
> create an async function to get pokemon. push into pokemon service
> onMount the getPokemon function after the page loads.
> make a v-for="p in pokemon". then {{p.name}}.. this will show all the pokemon names on the page.
> put buttons that take us to the previous and next 20 pokemon: the url for the next and prev 20 exist in the get pokemon response
> @click="changePage"

return: compute the prev and next pageUrl


# poke service
> get the data from api
> save next and prev pageUrl to the appState
> we are going to use api in axios and set it to the pokedex api url

> changePage(url){
  const res = await api.get(url);
  save AppState prev next pokemon stuff
}

# app.vue
>

# AppState
>we need to set nextPageUrl and prevPageUrl in our AppState.

# misc
:disabled="!nextPageUrl" this will bind disabled to the html if nextPageUrl is null i think... on button...

 
