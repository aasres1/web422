---
title: Angular routing introduction
layout: default
---

## Angular routing, introduction

> This document is being edited.  
> This notice will be removed when the edits are complete.

<br> 

Recall the ["Routing" in React](react-routing) notes from a few weeks ago. (Please review them before continuing.)

To summarize, you learned some new ideas:
* Routing matches URLs to components in an app
* In an app, we must add the router code module
* You must design and configure he route URLs
* It is possible to define URL parameters
* It is possible to define a "not found" route

~ ~ ~ ~ ~ 

Official docs... two sources:  

**TUTORIAL > Routing**
* Tour of Heroes example
* Adds the app routing module manually
* Route definitions distributed at first, then refactored into the routing module
* Incrementally adds default and not found routes*

**FUNDAMENTALS > Routing & Navigation**  
* Same Tour of Heroes data set
* Evolutionary detailed approach, too much detail
* Also too many advanced topics (router state, router events, guard, child, lazy load, etc.)

Other things to note:
* Routed components don't need a selector (check this out)
*

<br>

Return to the tutorial  
Pick and choose the highlights  
Done - not much new was learned there  

Then go to the FUNDAMENTALS > Routing & Navigation  
Work our way through that  
Again, focus on the engineering aspects  

Router features include (from the docs):
* can interpret a URL as an instruction to navigate to a view
* can pass optional parameters along to the view component 
* can bind the router to links on a page
* can navigate imperatively when the user clicks a button, selects from a drop box, or in response to some other stimulus from any source
* and the router logs activity in the browser's history feature so the back and forward buttons work as well

Routes (URL paths) must be defined. In the base config, there's no "by convention" route templates. This contrasts with ASP.NET MVC apps, which have a default route template. (Follow the convention, and there's no route code to write.)

Order of the defined routes matters. 

Route array id of type Routes. A few notes to get started:
* path is a string; it's assumed (configured) that the string is added to the "base" href in index.html
* empty path is often used todo a default redirect
* path ** is a wildcard, to match any non-configured route; often used for 404 not found component (or redirect)
* component names the component with the view to be displayed
* data is optional, can pass an object to the component/view

Router outlet (router-outlet) element is a placeholder, often in app-component.html. 

An `<a>` element must include a routerLink attribute, and NOT an href attribute. 

Often, a `<nav>` element encloses a set of links. Add a `routerLinkActive` attribute to the `<nav>` element so that it will add the CSS "active" class to the active/clicked link. A nice visual help cue/hint for the browser user. 

The first part of the document's [summary](https://angular.io/guide/router#summary) is good and useful.  
(ooh - I'm having a *deja vu* moment when writing this, from a long time ago!)

The [sample app in action](https://angular.io/guide/router#the-sample-application-in-action) has all the working pieces. 

After looking at several examples, including how-to's (tutorials) and guides, I think that it's best to extract the "how to" rules to a checklist, then dive right in to code the app you're working on. The above "sample app in action" part of the document will likely provide us with all we need to make the checklist. 

One item that should be on the checklist is for the programmer to list (write out!) all the URL paths that are likely to be needed in the app. 

The docs FUNDAMENTALS > Routing & Navigation coverage is just too much for our purposes.

<br>

### Adding routing to an app (our guidance)

> Editing is in progress...  
> Will have to carefully go through this

To get started, 

When creating a new project, can add the `--routing` option to create an `app-routing.module.ts` file

So... can:
1. add to existing project, or
2. generate a new project with routing

Generate a module that will be dedicated to routing.

```
ng g module app-routing
```

In `app.module.ts`, import the router module.

```javascript
import { Router } from "@angular/router";
```

<br>

Helpful note (in addition to the official docs):  
[SO - add routing module](https://stackoverflow.com/questions/44990030/how-to-add-a-routing-module-to-an-existing-module-in-angular-cli-version-1-1-1)

Another take:  
[Config routing](https://shermandigital.com/blog/configure-routing-in-an-angular-cli-project/)

<br>

**Suggestion**  
Leave route parameters until the next week, when we learn services  
Doing that will give context and deeper meaning to the topic

( more to come )

<br>

**Future**

Can add static assets to a project  
Google search words: angular router ignore segment static assets  
[SO - default path](https://stackoverflow.com/questions/40424907/whats-the-default-path-for-static-files-in-angular2)  

Deployment - Angular app *and* web API in same host at the server?  
"angular proxy server" will open up this topic  
[SO - proxy API requests](https://stackoverflow.com/questions/37172928/angular-cli-server-how-to-proxy-api-requests-to-another-server)  
<br>