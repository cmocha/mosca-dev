---
title: Choosing Eleventy for my blog. How I got there and my first impressions.
description: I was looking for learning something new and I found Eleventy. Hot take, I'm enjoying it.
tags:
  - post
  - eleventy
  - hot-take
  - jamstack
layout: layouts/post.njk
templateClass: tmpl-post
date: 2020-03-05
---

This journey started with wanting to build a new site for myself. Well I really wanted an excuse to work on something totally new and green. You know, pick whatever tech stack I wanted and no looking back. So time has come, build a simple site that I could document stuff I was working on, learning about and interested in.

Okay so where to begin? The part that I would imagine most developers consider is their favorite part of any project. What is that? Getting to pick what tech to build with of course! Well for me at least this is the most fun and also sometimes the most difficult.

With all of the talk about Jamstack lately I had to take a dive and see what this "JAM" stack was all about. I think it was perhaps a podcast where I first heard those words. I must admit my first thought was mixed feelings but still somewhat taken by the sound of it all. So I took off running and in a frenzy looking online to what I could find out about this stack the Jamstack.

I think it was the [jamstack guitar amplifier site](https://jamstack.io) that I found first and thought, well that's kinda cool but not what I'm looking for right now. Umm let's bookmark that for later. ;) Okay, maybe the next or so result was it. The [Jamstack.org](https://jamstack.org) website was the one and where I learned a bit more about what makes a website a Jamstack website. I was sold pretty quickly and wanted to experiment and use this stack on my next project. It had brought back an excitement in developing and designing websites that I was missing for some time. It was refreshing. I mean doesn't a webstack promising performance, scaling, security and a better developer experience just sound sweet?

The growing popularity and buzz around Jamstack seemed to make exploring it an obvious choice. There appeared to be plenty that I could learn along the way and build my skill set. I thought to myself this is a win win. I had never worked with automated builds and atomic deploys so with these two practices labled as "best practices", I knew I would be getting some lessons and learning about this as I put it to practice. The concept of everything in Git also sounded very appealing and I liked the idea of possibly no database in that case. Some others, like modern build tools, use of a CDN and instant cache validation to go along. Instant cache validation? I don't even know what that is, hopefully I'll learn about it.

All in all this seems like super smart guidlines that should be fun to learn and implement. Next I began to look at some examples. Reading about some of the [sites featured on Jamstack.org](https://jamstack.org/examples/) were really inspriring. I liked how they listed what type of tech was leveraged to build each site. This gave some context and maybe a glimpse as to what is most popular. I started looking at the sites and ones I liked, quickly noted what they were built with. This seemed to point me to investigate [Gatsby](https://www.gatsbyjs.org), [Netlify](https://www.netlify.com), and [Vue.js](https://vuejs.org) to name a few.

## Looking for that perfect tech.

I spent some time looking at Gatsby and setup a local dev environment tinkering with the Gatsby [default starter](https://www.gatsbyjs.org/starters/gatsbyjs/gatsby-starter-default/) This was my first look at Gatsby and it was enjoyable and seemed like if I wanted to stop here and run with it I could. It appeared to me that Gatsby as a project could really fit most needs and probably mine. But I didn't have any experience with React so this ecosystem was new to me. This wasn't a problem but it did make me question if I was sure I wanted to use this for my "simple" blog project. This question made me want to give a look at some others before sticking on Gatsby and React. I do like Gatsby a lot but after going through some of the step by step tutorials I still wanted to check some other options.

So I decided next I wanted to try something using Vue. Since I tried a React based site generator, it only seemed like the obvious choice. Well I took a look at Vue.js and quickly started going through some of the docs and tutorials. I found myself next "hello worlding" [Gridsome](https://gridsome.org/), the Vue.js powered static site generator. This is when I realized that I was questioning my decisions based on an underlying framework. I thought do I really need to use a framework for just a "simple" blog site? That's when about the time I recalled some static site generator I heard of that was supposed to be a "simpler" static site generator. Thats how I decided that I wanted to try [Eleventy](https://www.11ty.dev/) next.

I headed on over to the 11ty.dev site. The simplicity of it all is what felt right. I liked how the template engine was decoupled from your content allowing for easy migration to somthing else if needed. The flexibility of many supported template engines was also nice. There really wasn't much setup at all involved to get running with it. Probably the quickest experience ever. This plethora of templating choices and 0 to 100 setup time made working with Eleventy so enjoyable.

I was off running eleventy --serve and then modified a couple posts. Just a couple markdown files that lived in a posts folder. I also messed around with the eleventy.js file and experimented with filtering my posts like a WordPress style excerpt.

```js
// Get an intro or in WordPress land an excerpt.
eleventyConfig.addFilter("intro", (string, n) => {
  if (n < 0) {
    return string.slice(n);
  }

  return string.slice(0, n);
});
```

Next I thought about what if I wanted to somehow use an alternate content source, like content from a headless cms. Maybe this is not what 11ty is really intended for or maybe it has no real preference, but I was able to successfully fetch some content from a [Strapi](https://www.strapi.io/) setup. So my thought afterwards is Eleventy is not opinionated on how you provide it content. It is a tool in your web dev tool box that simply allows you to generate some static markup using practically any templating style you want from any data/content available.

In the end I realized this was really all I needed at this time for a simple blog site... Okay so no framework, and probably not a real Jamstack project... Just Eleventy. Oh but I see a Jamstack project on the horizon. Actually it is only a matter of time before I use some service or API on this site. Somebody say comments?

### Summary

Not sure what is proper Eleventy or 11ty... But to me this simplicity and flexibility is great and what I really like about Eleventy. What do you think of Eleventy? Are you using any static site generators on your projects? What is your favorite? Send me a message. Now I gotta setup some comment system to go right here...
