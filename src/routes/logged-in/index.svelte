<script>
  import { onMount } from 'svelte';
  // import qs from 'query-string';

  let props = {};
  let userName = "";

  onMount(async()=>{
    const urlSearchParams = new URLSearchParams(window.location.search);
    userName = urlSearchParams.get("userName");

    // const query = qs.parse(context.queryString);
    
  })
</script>

<h1>Welcome to 22ndtech {userName}</h1>