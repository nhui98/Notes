# Static Site Generation
- generated at build time - recommended, better performance, can be cached by CDN

*getStaticPaths*
async getStaticPaths() 
  return {
    paths: [{ params: {paramName: value} }], 
    fallback: 
    false     //paths not returned by getStaticPaths will result in 404 page
    true      //only statically generate the returned paths, 
              //paths not specified will return a fallback version and in the background will statically generate the page,
              //swaps the fallback with the pre-rendered page once complete and adds(caches) it to the list of pre generated pages.
    blocking  //same as true but no fallback placeholder is returned, page is ssr on first request then cached
  }

- fallback page: check router.isFallback (next/router) and return fallback/loading state

*getStaticProps*
async getStaticProps(context: {params, preview, ...others}) 
  return {
    props: {},
    revalidate: false(default)   
                seconds             //time which a page re-generation occurs (Incremental Static Regeneration)
    notFound,                       //not needed if fallback is false, 
    redirect: {
      destination,
      permanent/statusCode
    }
  }

- if reading from file system use process.cwd() and not __dirname to get the directory where nextjs is being executed

# Server Side Rendering
- generated on each request

*getServerSideProps*
getServerSideProps(context: {params, req, res, query, ...others})
  return {
    props: {}
    notFound,                       //if true will return 404
    redirect: {
      destination,
      permanent/statusCode
    }
  }