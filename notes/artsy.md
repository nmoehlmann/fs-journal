# router
beforeEnter: authGuard sees if the user is authenticated and prompts them to login.

# hook
basically something that checks when something is loaded to the page. listener.

# style
If you use a certain height and then use aspect-ratio: 1/1; the width will always be proportionate to the height.

# v-if
Shows whatever its attached to if the condition is met.

# pages and components
good rule of thumb is not having more than 150 lines of code.

# editable 
when making an editable, the ref needs to start out with something. for example. const editable = ref(AppState.account)
when creating a form, you can use v-model in the inputs to edit the editable.

# watchEffect 
An observer that changes things based on other things.

# modals
you can put modal xl on modal to make it bigger. By modal dialogue.
 
# router-link
example: 
:to="name: 'Profile', params: {id: project.creatorId}" 

