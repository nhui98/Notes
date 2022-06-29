# Profiler
<Profiler id="Navigation" onRender={callback}>
  function onRenderCallback(
    id, // the "id" prop of the Profiler tree that has just committed
    phase, // either "mount" (if the tree just mounted) or "update" (if it re-rendered)
    actualDuration, // time spent rendering the committed update
    baseDuration, // estimated time to render the entire subtree without memoization
    startTime, // when React began rendering this update
    commitTime, // when React committed this update
    interactions // the Set of interactions belonging to this update
  ) {
    // Aggregate or log render timings...
  }

- measuring how often a react component renders

# Error Boundaries
class ErrorBoundary extends React.Component {
  constructor(props) { 
    super(props); 
    this.state = { hasError: false };
  }

  *Update state so the next render will show the fallback UI*
  static getDerivedStateFromError(error) { 
    return { hasError: true };
  }

  *You can also log the error to an error reporting service*
  componentDidCatch(error, errorInfo) { 
    logErrorToMyService(error, errorInfo);
  }

  render() {
    *You can render any custom fallback UI*
    if (this.state.hasError) { 
      return <h1>Something went wrong.</h1>;
    }

    return this.props.children;
  }
}

Error boundaries do not catch errors for:
1. Event handlers (learn more)
2. Asynchronous code (e.g. setTimeout or requestAnimationFrame callbacks)
3. Server side rendering
4. Errors thrown in the error boundary itself (rather than its children)

# Turning svg into react component
npx @svgr/cli src/assets/icons --out-dir src/assets/iconComponents --icon --typescript