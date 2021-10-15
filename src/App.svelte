<script>
  import { Router, Route, NotFound, redirect, activeRoute } from "./pager";

  import AppBar from "./components/AppBar.svelte";

  import Home from "./pages/Home.svelte";
  import Student from "./pages/Student.svelte";
  import Instructor from "./pages/Instructor.svelte";

  const guard = (ctx, next) => {
    if (true) {
      redirect("/");
    } else {
      next();
    }
  };
</script>

<main>
  {#if $activeRoute.path != "/"}
    <AppBar />
  {/if}
  <Router>
    <Route path="/" component={Home} />
    <Route path="/student" component={Student} middleware={[guard]} />
    <Route path="/instructor" component={Instructor} />
    <NotFound component={Home} />
  </Router>
</main>
