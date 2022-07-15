# API Handlers
async handler(req: {cookies, query, body}, res) {}

Response Helpers
1. res.status(code)
2. res.json(body)
3. res.send(body)
4. res.redirect([status,] path)
4. res.unstable_revalidate(urlPath)

Every API route can export a config object to change the default configs: 
export const config = {
  api: {
    bodyParser: false, //set to false if want to stream the body
    bodyParser: {
      sizeLimit: '1mb', //"1000kb"
    },
    responseLimit: '4mb' (default)
  },
}

* You can use any Connect/Express middleware.

# Middleware
/pages/_middleware.ts

import { NextResponse } from 'next/server'

export function middleware(req, ev) {
  const {cookies, nextUrl, ip, ua, geo} = req

  response =  NextResponse.redirect() - Returns a NextResponse with a redirect set
              NextResponse.rewrite() - Returns a NextResponse with a rewrite set
              NextResponse.next() - Returns a NextResponse that will continue the middleware chain
              NextResponse.json() - A convenience method to create a response that encodes the provided JSON data

  response.cookies -  An object with the cookies in the Response
  response.cookie() - Set a cookie in the Response
  response.clearCookie() - Accepts a cookie and clears it
}
