# Async

Does something but doesnt stay at that function when the task isnt complete. Doesnt have to finish for other code to run at the same time. tis the meaning of async.

## await
> put before code to tell it is async

appState.characters = response.data.map(c => new Character(c))