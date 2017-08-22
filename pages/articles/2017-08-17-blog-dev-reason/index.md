---
title: Gatsby Blog
date: "2017-08-17T22:40:32.169Z"
layout: post
path: "/blog-dev-reason/"
category: "FrontEnd"
description: "GatsbyJS is an incredibly fast static site generator for React and I personally had great experience messing around with Gatsby"
---

## GatsbyJS
I've developed this blog mainly using GatsbyJS, incredibly fast static site generator for React.

I have spent quite some time to decide which tool to use for my blog and finally decided to use Gatsby.

The main reasons are as follows:

<ul>
  <li>The site generation is super simple and Gatsby follows the rules of Progressive Web</li>
  <li>Gatsby allows me to further dive into React which I have been learning lately</li>
  <li>Deploying website was also easy using surge.sh</li>
</ul>

I initially thought of using Wordpress or Jekyll because those are the most popular site/blog generator out there.

Wordpress might have been a good choice because I am comfortable using PHP but I heard a lot of stories of how Wordpress is becoming outdated.

In addition, Jekyll had advantage of being able to directly use Github page which is super convenient but required some knowledge of Ruby.

As a result, thanks to [this article on Medium](https://medium.freecodecamp.org/a-study-plan-to-cure-javascript-fatigue-8ad3a54f2eb1), I found out about GatsbyJS which is a rising static generator for React.

As for the theme of this blog, I used Gatsby blog starter from [this repo](https://github.com/tea1528/gatsby-starter-lumen).

## Disqus (Updated on Aug, 22)
[Disqus](https://disqus.com/) is a great tool for implementing comment system into your website easily. If you log into Disqus, you will find that Disqus provides numerous platform for installation. Unfortunately, they don't seem to support Gatsby yet and [universal embed code](https://help.disqus.com/customer/portal/articles/472097-universal-embed-code) isn't relevant as it directly handles DOM element (not allowed in React).

As a result, I have looked into some of the react components for Disqus:
- [most famous one: react-disqus-thred](https://github.com/mzabriskie/react-disqus-thread)
- [similar version](https://www.npmjs.com/package/react-disqus-comments)
- [modified version](https://github.com/konsumer/gatsby-starter-drunkenblog/blob/master/components/Disqus.js)
- [one I used](https://github.com/kriasoft/react-starter-kit/blob/master/docs/recipes/how-to-integrate-disqus.md)

I made a new component using the link above and named the folder Comments.

<br/>

```javascript
import { config } from 'config';

const SHORTNAME = config.disqusShortname;
const WEBSITE_URL = config.blogUrl;
```
<br/>

I replaced shortName and website_url using by creating disqusShortname and blogUrl in the config.toml file.



## Deployment
I had two options for deployment, surge.sh and Netlify. I first tried using surge.sh and it was incredibly fast in deploying the website. However, it was quite inconvenient in that it didn't link with Github repository directly.

As a result, I decided to use Netlify which had [great documentation](https://www.netlify.com/blog/2016/02/24/a-step-by-step-guide-gatsby-on-netlify/) on deploy Gatsby-generated website. Most importantly, it allowed direct link with either Github or Bitbucket.

## Custom Domain/hosting
Although I have not added any custom domain for my blog yet, I intend to do so in the near future. I haven't decided which service provider to use. I will upload another blog post on hosting when I do so.
