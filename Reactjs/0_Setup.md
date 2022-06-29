# Setup
*Npm*
npm i react react-dom 

*Create React App*
npx create-react-app app-name

*CDN*
<script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
<!-- <script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script> -->
<!-- <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script> -->

# Entry Point
import React from "react"
import ReactDOM from "react-dom"

const App = () => {
  return (...)
}

ReactDOM.render(React.createElement(App), document.getElementById("root"))

# React.createElement
const App = props => {
  return React.createElement(
    "div",
    {prop1: value, prop2: value},
    [//children]  
  )
}