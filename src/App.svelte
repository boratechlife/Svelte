<script lang="ts">
  import { Router, Route, Link } from "svelte-navigator";
  import Login from "./lib/Auth/Login.svelte";
  import PrivateRoute from "./lib/Auth/PrivateRoute.svelte";
  import DefaultLayout from './lib/layouts/default.svelte'

  import { user } from "./lib/stores";


</script>

<Router>
ENV = {import.meta.env.VITE_ENV}
<Route path="login">
  <Login />
</Route>



<PrivateRoute path="/*" let:location>
<DefaultLayout />

</PrivateRoute>


</Router>