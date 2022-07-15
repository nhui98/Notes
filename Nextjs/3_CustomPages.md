# Error Page
- pages/404.js
export default function Custom404() {}  //can use getStaticProps
- pages/500.js
export default function Custom500() {}  //can use getStaticProps

# Layout
- pages/_app.js       //each page/component is passed and rendered through app.js

*Single Shared Layout*
- layout component can wrap the returned component in _app.js
*Per-Page Layout*
- add a property for a page, Page.getLayout
- in _app.js check if this property exists, Component.getLayout

# Document
- pages/_document.js
import Document, { Html, Head, Main, NextScript } from 'next/document'
class MyDocument extends Document {
  render() {
    return (
      <Html>
        <Head>
          *Font optimisation*
          <link href="https://fonts.googleapis.com/css2?family=Inter&display=optional" rel="stylesheet" />
        </Head>
        <body>
          <Main />
          <NextScript />
        </body>
      </Html>
    )
  }
}

export default MyDocument
