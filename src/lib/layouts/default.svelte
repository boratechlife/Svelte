<script>
  import { Router, Route, Link, useLocation } from "svelte-navigator";
    import PrivateRoute from "../Auth/PrivateRoute.svelte";
  import Header from '../Shared/Header.svelte'
  import About from '../Dashboard/About.svelte'
  import Profile from '../User/Profile.svelte'
let url;
	const location = useLocation();

	$: {
		url = $location.pathname;
	}

location.subscribe(r => console.log(r))
</script>

<Router>
<Header />
{url}
<Route path="/">
<h1>Home</h1>
</Route>

	<PrivateRoute path="about/*"  let:location>
		<About />
	</PrivateRoute>

  	<PrivateRoute path="profile/*"  let:location>
		<Profile />
	</PrivateRoute>
</Router>