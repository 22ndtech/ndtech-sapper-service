<script>
  import { onMount } from "svelte";
  import axios from "axios";

  let urlSearchParams = new URLSearchParams(window.location.search);
  let code = urlSearchParams.get("code");

  let loggedIn = false;
  let githubUserData = {};

  onMount(() => {
    axios.post("http://localhost:3000/logged-in", {
      code: code,
      headers: {
        'Content-Type': 'application/json;charset=UTF-8',
        'Access-Control-Allow-Origin': '*',
        'Access-Control-Allow-Methods' : 'GET,PUT,POST,DELETE,PATCH,OPTIONS',
      }
    })
    .then((response => {
      loggedIn = true;
      const {githubUserData: data} = response.data;
    }))
    .catch((err) => {
      console.log("err = " + err);
      throw err;
    });
  });
</script>

<h1>loggedIn = {loggedIn}</h1>
<h1>githubUserData = {JSON.stringify(githubUserData)}</h1>