<script lang='ts'>
  import {page} from '$app/stores';
  import {onMount} from 'svelte';
  let songResults = [];

  onMount(async () => {
    let searched = $page.params.searchTerm;
    const itunesSearched = await fetch(`https://itunes.apple.com/search?term=${searched}&entity=song`);
    let res = await itunesSearched.json();
    songResults = res.results;
    console.log(songResults);
  })
</script>

<div>
  {$page.params.searchTerm}
</div>

