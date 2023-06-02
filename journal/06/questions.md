# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > | ANSWER HERE |

02. What is the difference between a vue `component` and `page`?

  > | A view component is similar to a template in that its a chunk of code with a specific responsibility used inside a page. A page is the webpage the user can see and interact with. |

03. What is ***Component-Based Architecture***?

  > | CBA is designed to give single responsibilities to single components. Instead of a horizontal style framework like MVC, CBA handles most of its logic in its components. The potential problem with CBA is that many developers use it as an entire framework which can potentially degrade readability. |

04. What are the three tags that make up a Vue component?

  > | The template: html, script: javascript, style: css |

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > | They are used as listeners and constructors to execute functions and certain operations as they are called throughout the life of the application. |

06. Which component in Vue does the vue-router use to mount pages onto?

  > | the vue-router uses loadPage to find which page to use. |

07. What is the difference between the `AppState` and the state object within a component?

  > | The state object is what the objects state is currently. The AppState is what the object is when it was saved and pushed into the AppState. |

08. What is the responsibility of `Services` in our Vue projects?

  > | Services has the same responsibility in vue that it had in mvc. When there is logic that requests data from a server or manipulates data in the AppState, it goes to the service. |

09. What are ***props*** and how are they used? Provide an example

  > | Because we use components that needs access to data stored in the AppState, we need a way to import that data. Props are used to bring that data into our components.

  example: If i were to use a component as a template for my page, I would need to pull data from the AppState to the page and finally into the component. To do this, I would use a compute to give that data in the AppState both a listener and a name. Then i would bind that as a prop to the component. Once I get that prop in my component, I have access to the data in the AppState.

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > | v-model on something like an input is watchable. Computed can be used to observe the AppState for changes. |
