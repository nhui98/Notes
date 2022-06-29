# React API
React.Component/PureComponent
React.createElement()
React.cloneElement()
React.isValidElement()
React.Children
.forEach() .count .only .toArray
React.Fragment | <></>


# Dynamic Import / Lazy Loading
1. import(...).then(...)
2. React.lazy + React.Suspense

const OtherComponent = React.lazy(() => import('./OtherComponent'))
<Suspense fallback={}>
  <OtherComponent />
</Suspense>

# Refs
React.createRef
React.forwardRef

*Forwarding Refs*
const FancyButton = React.forwardRef((props, ref) => (
  <button ref={ref} className="FancyButton">
    {props.children}
  </button>
))

const ref = React.createRef();
<FancyButton ref={ref}>Click me!</FancyButton>

# React.memo
const MyComponent = React.memo(function MyComponent(props) {
  //render using props
});

- only checks for prop changes
- useState, useReducer, useContext will still cause rerender
- only shallowly compare complex objects - can pass a second function to memo for a custom comparison

* Pass a second fn to React.memo for manual prop checking
function areEqual(prevProps, nextProps) {
  - return true if passing nextProps to render would return the same result as passing prevProps to render
  - otherwise return false
}
React.memo(MyComponent, areEqual);


# Portals
ReactDOM.createPortal(child, container)
- portal still exists in the React tree regarless of position in the DOM tree so behaves normally including event bubbling