<script>
	import Header from './components/Header.svelte'
	import Footer from './components/Footer.svelte'
	import Tabs from './common/Tabs.svelte'

// tabs
let items = ['Current polls', 'Add New Poll']
let activeItem = 'Current polls'

const tabChange = (e) => {
	activeItem = e.detail;
}
</script>

<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange}/>
	{#if activeItem === 'Current polls'}
		<p>Poll list components goes here</p>
	{:else if activeItem === 'Add New Poll'}	
		<p>New poll from component goes here</p>
	{/if}
</main>
<Footer />

<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
</style>