<script>
import { onMount } from "svelte";
import SubjectDetailItem from "../components/SubjectDetailItem.svelte";

export let id;
let details = [];

const loadSubjectDetails = () => {
  fetch(`https://ionicapp-7a398.firebaseio.com/galaxydemy/subject/${id}.json`)
  .then(res => res.json())
  .then(res => details = res)
  .catch(err => console.log(err))
}

onMount(() => {
  loadSubjectDetails();
});

</script>

<main>
  <div class="container">
    {#each details as detail}
      <SubjectDetailItem {...detail} />
    {/each}
  </div>
</main>