# sockets

set useSockets to true.

sockets are a way to communicate to a server without using http

up arrow is client sending message to server / down arrow is server sending message back to client

WS on the networking tab shows websockets

.on("s:creating:channel"), this.creatingChannel

create a function called creatingChannel

null check payload

pops a toast on channel creation, but we dont want the creator to be notified

conditional to prevent creator from getting pop toast.

doesnt get message back because he is sending to roomId that he isnt in.

watchEffect

router.beforeEach((to, from) => {
  logger.log('[TO]', to, '[FROM]' from)  
  if
})

require auth for socket supers so that it loads the auth before loading other things that require that.

