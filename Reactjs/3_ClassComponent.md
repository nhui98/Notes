# Class Components
class ClassComponent extends React.Component {
  constructor(props){
    super(props)
    this.state = {}
  }

  this.setState({...})
  this.setState((state,props) => ({...}))
  this.props

  componentDidMount() {}
  shouldComponentUpdate(nextProps, nextState) {}
  componentDidUpdate() {}
  componentWillUmount() {}

  render() {
    return
  }
}

# Context API
const MyContext = React.createContext(defaultValue) 
<MyContext.Provider value={ someValue }></MyContext.Provider>

<MyContext.Consumer>
  {
    value => 
    //render something based on the context value
  }
</MyContext.Consumer>

<!-- context for class components -->
MyClass.contextType = MyContext 
this.context

# React 18 concurrent feature
- React.startTransition 

function handleTabSelect(someState) {
  startTransition(() => {
    setTab(someState); //this someState is not an urgent update but a transition, so keep old UI in place and update only when new state is ready.
  });
}

- React.useTransition
