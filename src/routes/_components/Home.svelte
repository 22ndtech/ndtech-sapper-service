<script>
  import Stories from './Stories/index.svelte'

  export let currentPage = 1
</script>

<svelte:head>
  <title>22nd Tech App</title>
</svelte:head>

<div class="homepage page">
  <Stories {currentPage}/>
</div>
