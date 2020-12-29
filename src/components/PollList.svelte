<script>
  // import { onMount, onDestroy } from 'svelte';
  import PollStore from '../stores/PollStore.js'
  import PollDetails from './PollDetails.svelte'
  
  // export let polls = [];

  // // Using the store, will update when the data get updated in the store
  // const unsub = PollStore.subscribe(data => {
  //   polls = data;
  // });

  // onMount(() => {
  //   console.log('Component is mounted');
  // });

  // onDestroy(() => {
  //   console.log('component destroyed');
  //   unsub();
  // });

  // Note: Instead of using export and destroy to remove sub, just use $PollStore
</script>

<div class="poll-list">
  {#each $PollStore as poll (poll.id)}
    <div>
      <PollDetails {poll} />
    </div>
  {/each}
</div>

<style>
  .poll-list{
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 20px;
  }
</style>