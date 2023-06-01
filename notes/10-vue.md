# Vue

Template: Vue Starter

Home Page: template, script, style.

Components: stores html templates like navbar and footer.

App.vue: the most top level of the application. hardcode things in DOM regardless of page.

# vueFlix

put movie Api inside of axios
settings parameters inside of axios instance:
{
>api_key: 'da key',
>includes_adult: false,
>certification_country: 'US'
>etc...
}
these params will be included in every request to the api.
we put params in axios because otherwise, we need to put in the params in the service every time we make a request.

> we put in an ONMOUNTED to make a request to the api as soon as the page loads:
> make an async function that gets movies from api
> make movie model when we know what the api model looks like.
> map the res.data into a new instance of the model so it isn't a pojo.
HOLDUP, make sure the thing your mapping is an array or it wont work.

> Add computed to page. It will be a listener to the AppState to bring in the get request to draw to the page.
> We will start by hardcoding what we want our page to look like.

> Make a movie card as a component.
Instead of abstracting our templates to our models, we are abstracting it to its own component
> We set up the props inside the component under the "export default".
> We bind the prop to the movieCard so that the prop data can be passed down to the component. 
HOLDUP, often times when rendering the props, it will try to render before knowing what it is. Put ELVIS OPERATORS in prop requests.

> We wrap the card in a router link that takes us to a different page.
> We need to put the movies route in the router, or it has nothing to load.
> In the router link, we need to put in the movie id in the params. This way we are navigating to a unique page for each movie.

> we put in a useRoute in the setup.
> underneath we use a getMoviesById function.
HOLDUP, there is a chance that your endpoint is not correct and you will get 404.
> After getting that moveById, push it to the AppState as active movie.
> Again, we are using computed as a listener to the AppState for active movie.

## background image in vue
> bind style to container; :style="{backgroundImage: 'url(${movie.backgroundImg})' }"

## search bar
> We make an input in a form with an @submit to searchMovie.
HOLDUP, @submit.prevent is the same thing as "window.event.preventDefault()"
> Inside the input, we put in v-model="searchTerm"
> In setup we setup search terms.
> const searchTerm = search.value
> For searching an API: use the word 'query' and assign the value of whatever the search is.
> We are changing the AppState to be whatever response we get from the search request.
HOLDUP, how the query finds matching objects in the database is all handled on the backend.
> It should automatically redraw as soon as the AppState changes. vue is neat.

# pages current, next, prev
> In getMovies, we are saving the current page and total pages to the AppState.
> Add listener "computed" to home page for current and total pages. 2 computed
> We also have two buttons one for prev another for next in the dom.
both have an @click that call for the changePage function.
> async changePage function:
@click="changePage('next')"
@click="changePage('previous')"
rest of code in github lol





