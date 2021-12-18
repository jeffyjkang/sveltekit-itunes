<script lang='ts'>
  import {page} from '$app/stores';
  import {onMount} from 'svelte';
  let songResult: any = '';
  onMount(async () => {
    let songId = $page.params.songId;
    const itunesSearched = await fetch(`https://itunes.apple.com/search?term=${songId}&entity=song`);
    let res = await itunesSearched.json();
    songResult = res.results[0];
  })
</script>

<div>
  {$page.params.searchTerm}
</div>
<div>
  <div>{songResult.trackName}</div>
</div>

