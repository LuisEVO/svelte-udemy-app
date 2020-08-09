
<script >
  import { createEventDispatcher } from "svelte";
  
  export let id;
  export let title;
  export let img;
  export let instructor;
  export let progress;
  export let qualification;
  
  const dispatch = createEventDispatcher();
  const goDetail = () => dispatch('goDetail', id);
</script>

<div class="card" on:click={goDetail}>
  <img src="{img}" class="cardimg-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">{ title }</h5>
    <p class="card-text">{ instructor }</p>
    <p class="card-text">{ progress } % completo</p>
  </div>
</div>

<style>
  .card {
    width: calc( 100% - 20px);
    max-width: 15rem;
    margin: auto;
    margin-top: 10px;
    margin-bottom: 10px;
    transition: opacity .3s;
  }

  .card-title:hover {
    cursor: pointer;
    text-decoration: underline;
  }

  .card-title:active {
    opacity: 0.8;
  }

</style>  