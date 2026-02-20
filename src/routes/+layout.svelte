<script>
	let { children } = $props();
</script>

<svelte:head>
	<title>Vibe</title>
</svelte:head>

<nav>
	<div class="nav-inner">
		<a href="/" class="nav-brand">Vibe</a>
	</div>
</nav>

{@render children()}

<style>
	:global(*, *::before, *::after) {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	:global(body) {
		font-family: 'DM Sans', sans-serif;
		background: #0d0d0d;
		color: #f0ece4;
		min-height: 100vh;
	}

	nav {
		position: sticky;
		top: 0;
		z-index: 100;
		background: rgba(13, 13, 13, 0.85);
		backdrop-filter: blur(12px);
		border-bottom: 1px solid rgba(255, 255, 255, 0.08);
	}

	.nav-inner {
		max-width: 900px;
		margin: 0 auto;
		padding: 1rem 2rem;
		display: flex;
		align-items: center;
	}

	.nav-brand {
		font-family: 'Playfair Display', serif;
		font-size: 1.6rem;
		font-weight: 700;
		color: #c9a96e;
		text-decoration: none;
		letter-spacing: -0.02em;
	}
</style>
