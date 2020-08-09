<script>
import { navigate } from "svelte-routing";
import SubjectItem from "../components/SubjectItem.svelte";
import { onMount } from "svelte";
import Link from "svelte-routing/src/Link.svelte";
let subjects = [];

const goSubjectDetail = ({ detail }) => {
  navigate(`/subjet-detail/${detail}`)
}

const loadSubjects = () => {
  fetch('https://ionicapp-7a398.firebaseio.com/galaxydemy/subjects.json')
  .then(res => res.json())
  .then(res => subjects = res)
  .catch(err => console.log(err))
}

onMount(() => {
  loadSubjects();
});
</script>

<main>
  <div class="container" >
    <h1 class="mb-3">Cursos</h1>
    <div class="row">
      {#each subjects as subject}
        <div class="col-12 col-sm-6 col-md-4 col-xl-3 p-0">
          <SubjectItem on:goDetail={goSubjectDetail} {...subject} ></SubjectItem>
        </div>
      {/each} 
    </div>
  </div>
</main>

