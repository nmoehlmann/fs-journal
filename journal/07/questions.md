# Managing the Fullstack Application

1. Describe the two ways to bind Data in Vue?

  > | one way data binding: taking a property from js and using it with double curlies to express it in HTML. |
  > | class binding: you can use : before something to indicate that the value is referencing another object. |

2. The `SPA` acronym stands for what?

  > | Single Page Application |

3. What are some of the advantages/uses of a `SPA` over a traditional one?

  > | Because SPA only uses a single HTML file, it doesnt have to request new HTML files on every request for a new page. Instead it sends JSON which is usually faster.
  Instead of content rewriting on pageload, it will rewrite content on the current page. this is better for development and the user experience. |

4. What does the `onMounted` method in Vue do?

  > | It runs a function when the page loads. |

5. What is the `v-model` attribute in Vue for, and when might you use it?

  > | v-model creates a two way data binding. It usually binds between an input value and a property in js. |

6. What is the package.json file used for?

  > | It handles dependencies that the project needs. |

7. Which Vue attributes(directives) could you use to conditionally render elements on a page?

  > | v-if: can use a truthy falsey statement that only renders something if its true.
      v-else: if v-if is false, can run something else. |

8. What is the purpose of the `key` attribute when using `v-for` on an element?

  > | The key helps vue keep track of each element it renders on the page. It is usually supplied with an id |

9. What is the `<slot>` element and what is it used for?

  > | slot is a placeholder that can be used to render separate components and elements to a page given the proper tag. |
