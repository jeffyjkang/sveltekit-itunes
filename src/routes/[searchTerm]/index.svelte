<script lang='ts'>
  import {goto} from '$app/navigation';
  import {page} from '$app/stores';
  import {onMount} from 'svelte';
  let songResults = [];

  onMount(async () => {
    let searched = $page.params.searchTerm;
    const itunesSearched = await fetch(`https://itunes.apple.com/search?term=${searched}&entity=song`);
    let res = await itunesSearched.json();
    songResults = res.results;
  })
</script>

<div>
  {$page.params.searchTerm}
</div>
<div>
  {#each songResults as song}
    <button on:click={goto(`${$page.params.searchTerm}/${song.trackId}`)}>
      {song.trackName}
    </button>
  {/each}
</div>

