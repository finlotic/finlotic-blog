# A Brief Overview of the Tech Stack

## Language
We have two choices for type checked JavaScript

* TypeScript 
* Flow 

Community support for TypeScript is much better compared to Flow. Many projects are written in typescript or typings are provided by the community in DefinitelyTyped.

[Comparison post](https://blog.logrocket.com/typescript-vs-flow/)

> TypeScript is the language choice. 

---

## UI Framework 

### Requirements 
* It's server / statically rendered. 
* It's a static site, so a Static Site Generator (SSG) or SSG like support is necessary.
* Good build times (SSG builds tend to be really slow as they get big!)
* Must work well with a CMS

### Choices
#### **React Based** 

##### **Next.js**

It's a server side framework with both Server Rendering and Static Rendering support, by changing the function used to fetch the data. 

`getStaticProps / getStaticPaths` -> Statically Rendered
`getServerSideProps` -> Server Rendered

It has good CMS support with example projects for most CMS systems out there. 

Build times are not great for really large sites, but is mostly okay. 

It has good integration with Vercel, a way to deploy our website. It has features like `Incremental Static Re-Generation` which allows you to change the static content after the site is built with `getStaticPaths`. Which means we can add new posts without rebuilding and replacing the entire site. [Explanation here](https://nextjs.org/blog/next-9-5#stable-incremental-static-regeneration).

It forces a file-system based routing system, but data fetching can be made over any transport or protocol. 

##### **Gatsby.js**

Gatsby is a SSG framework, which excels in community support. It has a bunch of community built "recipes", plugins and themes. It should be super quick to build an MVP and get a site up and running. 

The plugin support is pretty good. For example, it has a plugin to integrate with Sharp image processing library that converts an image to the best format required for the browser it is rendering on. 

It has very good CMS support as well. 

Build times are really bad large sites, but better incremental build support is being worked on and should not be a problem. 

Gatsby forces upon you a GraphQL API. Even for things like file system based file fetching.

It has good integration with Gatsby Cloud.

##### **Gatsby vs Next**
*  [Post 1](https://dev.to/jameesy/gatsby-vs-next-js-what-why-and-when-4al5)

* [Post 2](https://jaredpalmer.com/gatsby-vs-nextjs)

* [Post 3](https://medium.com/frontend-digest/which-to-choose-in-2020-nextjs-vs-gatsby-1aa7ca279d8a)

#### **Vue Based** 

##### **Nuxt.js**

Nuxt is the Next.js equivalent in the Vue.js world. Has the same advantages of Next.js.

Has good CMS support as well. 

It is currently based of Vue 2, and Vue 3 (Which seems to have many breaking changes) support is not there yet. May not be the best time to pick this up. 

##### **Elevnty**

We can use Elevnty, which is a Jeykll replacement with, Vue as a template. [Explanation blog post by creator of Eleventy](https://www.netlify.com/blog/2020/09/18/eleventy-and-vue-a-match-made-to-power-netlify.com/)


#### **Svelte based**

##### **Sapper**

Again it's the next.js of the Svelte world. [Introductory blog post](https://svelte.dev/blog/sapper-towards-the-ideal-web-app-framework)

This seems to be the best in terms of performance. Really small bundle size with compiled code approach. But it may be lacking in CMS / Cloud support. 

#### **Other SSG frameworks**  
* [Elevnty](https://www.11ty.dev/) with Pug / Handlebars templates 

* [Hugo](https://gohugo.io/)

* [Jekyll](https://jekyllrb.com/)

> Going with React and Next.js

---

## CMS Provider 

We can go through this [post](https://bejamas.io/blog/headless-cms/#introduction) and make a decision. Seems like there is no real wrong choice, and for us as we are starting out really need posts features I would think.

---

## Things left to decide:- 

* Cloud / CDN provider (decided by framework of choice)
* Styling solution (completely custom or design system based? CSS in JS or CSS Modules? Would also be based on UI framework)


 

