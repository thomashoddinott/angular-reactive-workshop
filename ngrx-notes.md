<u>add to master branch when done</u>

# My Notes

Navigate through each step via its respective branch :arrow_right:

```
master (completed project)
start
01-ngrx-feature
02-reducers
03-actions
04-entity
05-basic-selectors
06-01-async-events-with-effects
06-async-events-with-effects
07-computed-data-with-selectors
08-facades
```

## Intro

Ngrx borrows from Redux and adds the ***special sauce*** of ... :drum: ... Observables (verify)

We already know that shared mutable state is terrible, but having multiple (not shared) states is also pretty bad 

If something changes in place A, how do you update state in place B? You need to share messages about updated state, or duplicate your state in another place, etc. ==> It's not simple 

One of the core principles or Redux is that **your state is in a single place** ==> All your state goes into a single state tree. This is a lot easier to work with :thumbsup:

#### holy trinity

Remember holy trinity of programming? 

- Handling of state
- Flow of control
- Code volume

Good handling of state ==> simplifies flow of control and reduces code volume

## Redux & NgRx Overview

**Redux**

1. Entire state is in a single state tree
2. State flows down from tree into application
3. Events are captured and **dispatched** via **action** objects into a **reducer**

A reducer is the only place you can mutate application state

This is all built on top of Observables which automatically update their subscribers when they themselves are updated 

==> All data flows down into child components and services very easily

Asynchronous operations all go via **effects** ==> a library for handling any "side effects" in your application. It's where business logic goes.

## Combine Reducers

Feature-level reducers are combined into a top-level reducer

## @ngrx/entity

Entity State adapter for managing record collections. @ngrx/entity provides an API to manipulate and query entity collections.

1. Reduces boilerplate for creating reducers that manage a collection of models
2. Provides performant CRUD operations for managing entity collections
3. Extensible type-safe adapters for selecting entity information.

https://duncanhunter.gitbook.io/angular-and-ngrx/22.-use-entity-adapter

---

**Effects** are **middleware** sitting between your application and the reducer

==> we use it for async operations

### Computed Data with Selectors

What if you need to connect *related* models together, or if you need to perform some kind of data manipulation before your selected data is *consumed*? 

How we can take selectors, perform some combinatory logic, and get the data out?

### Facades

Use the when you want to hide the details of the NgRx implementation. Useful for legacy code.

### Summary

Stores, Actions, Reducers, Selectors, *Entity*, Computed selectors, Facades

Your data is in one place and it is changed in one place. Simplifies your entire communication flow

In Angular, NgRx is how you can greatly reduce complexity

- All state in a single state tree; Single source of truth
- Read-only ==> reduce shared-mutable state
- Small specific methods in reducers ==> pure functions ==> easy to test

==> Helps keep our [holy trinity](#holy trinity) strong 

And... Observables are very handy

---

Todos:

- [continue making PRs between branches](https://github.com/thomashoddinott/angular-reactive-workshop/pulls) - the diffs might be helpful [ ]
- Go over code at the end of the course [ ]

https://github.com/onehungrymind/angular-reactive-workshop/wiki/Reactive-Workshop-Steps
