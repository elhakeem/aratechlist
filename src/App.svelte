<script>
	import Header from './components/header.svelte';
	import About from './components/about.svelte';
	import Grid from './components/grid.svelte';
	import Blog from './components/blog.svelte';
	import Filter from './components/filter.svelte';
	import Footer from './components/footer.svelte';
	import data from './data.json';

	let filterVal = "";

	const collectedBlogInfo = blog => `${blog.name} ${blog.blog} ${blog.emoji} ${blog.description} ${blog.keywords.join(" ")}`;
	
</script>

<main>
	<Header />
	<Filter on:change={e => filterVal = e.detail.value}/>
	<Grid>
		{#each data as blog}
			{#if collectedBlogInfo(blog).includes(filterVal)}
				<Blog blog={blog}/>
			{/if}
		{/each}
	</Grid>
	<About />
	<Footer />
</main>

<style>
	main {
		max-width: 1200px;
		padding: 15px;
		margin: auto;
	}
</style>