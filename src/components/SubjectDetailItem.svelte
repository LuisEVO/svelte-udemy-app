<script>
export let title;
export let section;
export let classes = [];
</script>

<div class="card">
  <div class="card-body">
    <h5>{ title }</h5>
    <h6>{ section }</h6>
    {#each classes as text}
      <div>{ text }</div>
    {/each}
  </div>
</div>

<style>
  .card {
    margin: 10px 0;
  }
</style>