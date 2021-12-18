<script lang='ts'>
  import {goto} from '$app/navigation';
  let searchTerm = '';
  const submitSearch = () => {
    console.log('submitHit');
    goto(`${searchTerm}/search-result`)
  }
</script>

<div>
  <div>Search an Artist</div>
    <form on:submit|preventDefault={submitSearch}>
      <input type='text' bind:value={searchTerm} />
      <button type='submit'>Search</button>
    <form />
  <p>{searchTerm}</p>
</div>
