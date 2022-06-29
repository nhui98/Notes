# Setup
npm i react-router-dom

import BrowserRouter and wrap around app


# Components
*Routes*
<Routes>
  <Route path="/" element={}>
    //nested route, use <Outlet context? /> to render child in parent component
    <Route index element={} />          
    <Route path="id" element={} />
  </Route>
  <Route path="/:urlParam" element={} />
  <Route path="*" element={} /> 
</Routes>

*Links*
<Link to="/"></Link>
<NavLink to="" className={({ isActive }) => ...}>

*Navigate*
<Navigate to replace?>


# Hooks
*useParams*
const params = useParams()  //url Params are always strings

*useSearchParams*
const [searchParams, setSearchParams] = useSearchParams()

*useLocation*
const location = useLocation()
const {
  pathname, //url after the origin
  search,   //search params
  hash,     //scroll position of the current page
  state,    //additional state which can be passed by navigate("", {state: ...}) and <Link to state>
  key       //each location gets a unique key
} = location

*useNavigate*
const navigate = useNavigate()
navigate("", {replace: true})