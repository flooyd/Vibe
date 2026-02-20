<script>
	let { children } = $props();
</script>

<svelte:head>
	<title>Vibe.</title>
</svelte:head>

<nav>
	<div class="nav-inner">
		<a href="/" class="nav-brand">Vibe.</a>
		<div class="nav-links">
			<a href="#tools">Tools</a>
			<a href="#github">GitHub</a>
			<a href="#project">Project</a>
			<a href="#commit">Commit</a>
		</div>
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
		justify-content: space-between;
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

	.nav-links {
		display: flex;
		gap: 2rem;
	}

	.nav-links a {
		font-family: 'DM Sans', sans-serif;
		font-size: 0.875rem;
		font-weight: 500;
		color: #a09880;
		text-decoration: none;
		letter-spacing: 0.05em;
		text-transform: uppercase;
		transition: color 0.2s;
	}

	.nav-links a:hover {
		color: #f0ece4;
	}

	@media (max-width: 600px) {
		.nav-links {
			gap: 1rem;
		}
		.nav-links a {
			font-size: 0.75rem;
		}
	}
</style>
