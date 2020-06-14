<script>
	import Maps from './component/maps.svelte';
	import Contact from './component/contact.svelte';
	import Portfolio from './component/portfolio.svelte';
	import Todolist from './component/todolist.svelte';
	import Home from './component/home.svelte';
	import Footer from './footer.svelte';
	import Header from './header.svelte';
	// export let name;
</script>

<style>
	:global(.container) {
		max-width: 1100px;
	}
	:global(main) {
	}

	:global(h3) {
		margin-bottom: 1em;
		color: #ff3e00;
		text-transform: uppercase;
		text-align: center;
		font-size: 4em;
	}

</style>

<Header/>
<Home/>
<Portfolio/>
<Contact/>
<Maps/>
<Todolist/>
<Footer/>

<!-- <main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main> -->