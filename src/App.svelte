<script>
  import { Router, Link, Route } from "svelte-routing";
  import Subjects from "./pages/Subjects.svelte";
  import SubjectsDetail from "./pages/SubjectsDetail.svelte";
</script> 

<Router>
  <div>
    <Route path="subjet-detail/:id" component="{SubjectsDetail}" />
    <Route path="/"><Subjects /></Route>
  </div>
</Router>

