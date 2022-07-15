# next/image
<Image src alt width height placeholder="blur"(optional) priority />
- need to provide width and height for remote images (images not in public folder)
- optional blurDataURL can also be provided
- priority property should be added to image that will be the largest Contentful Paint for each page

*optimizes by*
1. serving correctly sized img for each device
2. only loading img when they enter the viewport
3. on-demand image re-sizing
*avoid Cumulative Layout Shift*
1. using a static import
2. explicitly include height and width property
3. implicitly with layout='fill' 

# next/router
const router = useRouter()
- window.location is better for external URLs

# next/script

# next/head
