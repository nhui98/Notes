# Setup
npx create-next-app app-name | npm i next react react-dom

# Linking
import Link from 'next/link'
<Link href={} | href={{ pathname: '/blog/[slug]', query: { slug: post.slug }, }} >
  <a></a>
</Link>

# Routing
*index routes*
/blog/index.js              /blog
*nested routes*
/blog/first-post.js         /blog/first-post
*dynamic routes*
/blog/[slug].js             /blog/:slug 
/[username]/settings.js     /:username/settings 
/post/[...all].js           /post/*
/post/[[...all]].js         /post/* | /post  
