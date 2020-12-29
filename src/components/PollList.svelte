<script>
  import PollStore from '../stores/PollStore.js'
  import PollDetails from './PollDetails.svelte'
  
  export let polls = [];

  // Using the store, will update when the data get updated in the store
  PollStore.subscribe(data => {
    polls = data;
  });
</script>

<div class="poll-list">
  {#each polls as poll (poll.id)}
    <div>
      <PollDetails {poll} on:vote/>
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