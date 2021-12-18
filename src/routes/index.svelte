<script lang='ts'>
  import {goto} from '$app/navigation';
  let searchTerm = '';
  const submitSearch = () => {
    goto(`${searchTerm}`)
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

