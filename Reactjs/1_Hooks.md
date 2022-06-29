# useState
const [state, setState] = useState(initialState)
setState(newState) | setState(prevState => newState)

# useEffect
useEffect(() => {
  ...
  return () => {
    //unmount cleanup
  }
}, [//dependencies]) 

# useContext + Context API
const MyContext = React.createContext({
  theme: themes.dark,
  toggleTheme: () => {},
})  

- MyContext.displayName = "custom name to display in dev tools"
- dynamic context - only specify shape of context, and populate the context using state from the component where the context is provided

<MyContext.Provider value={ defaultValue }></MyContext.Provider>
const value = useContext(MyContext)

# useReducer
const [state, dispatch] = useReducer(reducer, initialState)

# useCallback + useMemo
const memoizedFunction = useCallback(() => {}, [])
- referential equality between renders for functions
- returns its function uncalled
const memoizedValue = useMemo(() => {}, [])
- referential equality between renders for values
- calls its function and returns the result

# useRef
const refContainer = useRef(initialValue);
- handy for keeping mutable value around
- gives same ref object on every render

# useLayoutEffect
- same as useEffect but fires synchronously before being painted on screen
- use for layout calculations

# useTransition
const [isPending, startTransition] = useTransition();

startTransition(() => {
  //low priority setState
})

# useDeferredValue
const deferredValue = useDeferredValue(value);
- low priority update

# useImperativeHandle
useImperativeHandle(ref, createHandle, [deps])
- customizes the instance value that is exposed to parent components when using ref
- use with forwarRef

# useDebugValue
useDebugValue(value)
- used to display a label for custom hooks in React DevTools

# useId
const id = useId();

