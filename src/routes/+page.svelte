<script>
	let framework = $state('');

	const sveltekitPrompt = `You are an expert SvelteKit developer. Help me build a web app using SvelteKit and Vite.

I want to create a [describe your app idea here, e.g. "personal task manager where users can add, complete, and delete tasks"].

Please:
1. Scaffold the project structure with SvelteKit (using the minimal template).
2. Create the main page in src/routes/+page.svelte with a clean UI.
3. Use Svelte's $state() rune for reactive state management.
4. Add basic CSS styles inline or in a <style> block — no external UI libraries.
5. Make it functional and ready to run with \`npm run dev\`.

Start by showing me the files I need to create or modify.`;

	const reactPrompt = `You are an expert React developer. Help me build a web app using React and Vite.

I want to create a [describe your app idea here, e.g. "personal task manager where users can add, complete, and delete tasks"].

Please:
1. Scaffold the project with \`npm create vite@latest my-app -- --template react\`.
2. Create the main component in src/App.jsx.
3. Use React's useState hook for state management.
4. Add basic CSS styles in src/App.css — no external UI libraries.
5. Make it functional and ready to run with \`npm run dev\`.

Start by showing me the files I need to create or modify.`;
</script>

<main>
	<!-- Hero -->
	<section class="hero">
		<h1>How to Vibe</h1>
		<p class="subtitle">A practical guide to building your first web app with AI as your co-pilot</p>
	</section>

	<!-- Step 1: Tools -->
	<section id="tools" class="step">
		<div class="step-number">01</div>
		<h2>Download Your Tools</h2>
		<p>
			Before writing a single line of code, you need three things on your machine: a code editor, a
			JavaScript runtime, and a version-control client. Here's what to grab.
		</p>

		<div class="tool-grid">
			<div class="tool-card">
				<div class="tool-icon">🖊️</div>
				<h3>VS Code</h3>
				<p>The most popular code editor. Free, fast, and has great extensions for Svelte and React.</p>
				<a
					href="https://code.visualstudio.com/download"
					target="_blank"
					rel="noopener noreferrer"
					class="tool-link"
				>
					Download VS Code →
				</a>
				<div class="install-note">
					Also install the <strong>Svelte for VS Code</strong> extension from the Extensions panel
					(Ctrl+Shift+X / ⌘+Shift+X).
				</div>
			</div>

			<div class="tool-card">
				<div class="tool-icon">⬢</div>
				<h3>Node.js</h3>
				<p>
					The JavaScript runtime that powers your dev server and build tools. Download the LTS
					version.
				</p>
				<a
					href="https://nodejs.org/en/download"
					target="_blank"
					rel="noopener noreferrer"
					class="tool-link"
				>
					Download Node.js →
				</a>
				<div class="install-note">
					After installing, verify in your terminal:
					<pre><code>node --version
npm --version</code></pre>
				</div>
			</div>

			<div class="tool-card">
				<div class="tool-icon">🐙</div>
				<h3>Git</h3>
				<p>The version-control system you'll use to track changes and push code to GitHub.</p>
				<a
					href="https://git-scm.com/downloads"
					target="_blank"
					rel="noopener noreferrer"
					class="tool-link"
				>
					Download Git →
				</a>
				<div class="install-note">
					After installing, configure your identity:
					<pre><code>git config --global user.name "Your Name"
git config --global user.email "you@example.com"</code></pre>
				</div>
			</div>
		</div>
	</section>

	<!-- Step 2: GitHub -->
	<section id="github" class="step">
		<div class="step-number">02</div>
		<h2>Create a GitHub Repository</h2>
		<p>
			GitHub is where your code lives in the cloud. Every project starts with a repository (repo for
			short).
		</p>

		<ol class="instructions">
			<li>
				Go to <a href="https://github.com" target="_blank" rel="noopener noreferrer">github.com</a>
				and sign up for a free account (or log in).
			</li>
			<li>
				Click the <strong>+</strong> icon in the top-right corner and choose
				<strong>New repository</strong>.
			</li>
			<li>
				Give your repo a name (e.g. <code>my-vibe-app</code>), set it to <strong>Public</strong>,
				check <strong>Add a README file</strong>, then click <strong>Create repository</strong>.
			</li>
			<li>
				Once created, click the green <strong>Code</strong> button and copy the HTTPS URL. Then clone
				it locally:
				<pre><code>git clone https://github.com/your-username/my-vibe-app.git
cd my-vibe-app</code></pre>
			</li>
		</ol>

		<div class="tip">
			💡 <strong>Tip:</strong> You can also use the
			<a href="https://desktop.github.com" target="_blank" rel="noopener noreferrer"
				>GitHub Desktop app</a
			> if you prefer a GUI over the command line.
		</div>
	</section>

	<!-- Step 3: Framework -->
	<section id="project" class="step">
		<div class="step-number">03</div>
		<h2>Create Your Project</h2>
		<p>
			Choose a framework to scaffold your app. Both options use Vite under the hood for blazing-fast
			development.
		</p>

		<div class="framework-picker">
			<button
				class="framework-btn"
				class:active={framework === 'svelte'}
				onclick={() => (framework = framework === 'svelte' ? '' : 'svelte')}
			>
				<span class="fw-icon">⚡</span>
				<span class="fw-name">SvelteKit</span>
				<span class="fw-tag">Recommended</span>
			</button>
			<button
				class="framework-btn"
				class:active={framework === 'react'}
				onclick={() => (framework = framework === 'react' ? '' : 'react')}
			>
				<span class="fw-icon">⚛️</span>
				<span class="fw-name">React</span>
				<span class="fw-tag">Popular</span>
			</button>
		</div>

		{#if framework === 'svelte'}
			<div class="framework-detail">
				<h3>Scaffold a SvelteKit project</h3>
				<p>Run this command inside your cloned repo folder:</p>
				<pre><code>npx sv create . --template minimal --no-types --install npm</code></pre>
				<p>Then start the development server:</p>
				<pre><code>npm run dev</code></pre>
				<p>Open <a href="http://localhost:5173" target="_blank">http://localhost:5173</a> in your browser. 🎉</p>
			</div>
		{:else if framework === 'react'}
			<div class="framework-detail">
				<h3>Scaffold a React + Vite project</h3>
				<p>Run this command inside your cloned repo folder:</p>
				<pre><code>npm create vite@latest . -- --template react</code></pre>
				<p>Install dependencies, then start the development server:</p>
				<pre><code>npm install
npm run dev</code></pre>
				<p>Open <a href="http://localhost:5173" target="_blank">http://localhost:5173</a> in your browser. 🎉</p>
			</div>
		{:else}
			<p class="picker-hint">👆 Select a framework above to see setup instructions.</p>
		{/if}
	</section>

	<!-- Step 4: AI Prompt -->
	<section class="step">
		<div class="step-number">04</div>
		<h2>Prompt Your AI Co-pilot</h2>
		<p>
			This is the vibe-coding magic. Open <a
				href="https://cursor.sh"
				target="_blank"
				rel="noopener noreferrer">Cursor</a
			>,
			<a href="https://github.com/features/copilot" target="_blank" rel="noopener noreferrer"
				>GitHub Copilot</a
			>, or any AI chat tool (ChatGPT, Claude, Gemini) and paste the prompt below. Customise the
			bracketed section to describe <em>your</em> idea.
		</p>

		{#if framework === 'svelte' || framework === 'react'}
			<div class="prompt-box">
				<div class="prompt-header">
					{framework === 'svelte' ? '⚡ SvelteKit Prompt' : '⚛️ React Prompt'}
					<button
						class="copy-btn"
						onclick={() => {
							navigator.clipboard.writeText(framework === 'svelte' ? sveltekitPrompt : reactPrompt);
						}}
					>
						Copy
					</button>
				</div>
				<pre class="prompt-text">{framework === 'svelte' ? sveltekitPrompt : reactPrompt}</pre>
			</div>
		{:else}
			<div class="prompt-placeholder">
				<p>← Go back to <strong>Step 3</strong> and pick a framework to see your tailored prompt.</p>
			</div>
		{/if}

		<div class="tip">
			💡 <strong>Pro tip:</strong> The more specific your description, the better the AI's output.
			Include the features you want, the visual style, and any data you'll need to store.
		</div>
	</section>

	<!-- Step 5: Commit & Push -->
	<section id="commit" class="step">
		<div class="step-number">05</div>
		<h2>Commit &amp; Push to GitHub</h2>
		<p>
			Once you've built something worth saving, push it to GitHub so it lives in the cloud and you
			can share it with the world.
		</p>

		<ol class="instructions">
			<li>
				<strong>Stage your changes</strong> — tell Git which files to include in the commit:
				<pre><code>git add .</code></pre>
			</li>
			<li>
				<strong>Commit</strong> — snapshot your changes with a short description:
				<pre><code>git commit -m "Initial vibe: add home page"</code></pre>
			</li>
			<li>
				<strong>Push</strong> — upload your commit to GitHub:
				<pre><code>git push origin main</code></pre>
			</li>
			<li>
				Visit your GitHub repo in the browser — your files are now live! Share the URL with anyone.
			</li>
		</ol>

		<div class="tip">
			💡 <strong>Repeat the cycle:</strong> Build → <code>git add .</code> →
			<code>git commit -m "..."</code> → <code>git push</code>. That's the vibe-coding loop.
		</div>
	</section>

	<footer>
		<p>Made with ✨ vibe energy. Go build something.</p>
	</footer>
</main>

<style>
	main {
		max-width: 900px;
		margin: 0 auto;
		padding: 0 2rem 4rem;
	}

	/* ---- Hero ---- */
	.hero {
		padding: 5rem 0 3rem;
		text-align: center;
	}

	h1 {
		font-family: 'Playfair Display', serif;
		font-size: clamp(3rem, 8vw, 6rem);
		font-weight: 700;
		color: #c9a96e;
		letter-spacing: -0.03em;
		line-height: 1;
		margin-bottom: 1rem;
	}

	.subtitle {
		font-size: 1.125rem;
		color: #a09880;
		max-width: 520px;
		margin: 0 auto;
		line-height: 1.6;
	}

	/* ---- Steps ---- */
	.step {
		margin-top: 5rem;
		padding-top: 1rem;
		border-top: 1px solid rgba(255, 255, 255, 0.07);
	}

	.step-number {
		font-family: 'Playfair Display', serif;
		font-size: 0.75rem;
		font-weight: 700;
		letter-spacing: 0.15em;
		color: #c9a96e;
		text-transform: uppercase;
		margin-bottom: 0.5rem;
	}

	h2 {
		font-family: 'Playfair Display', serif;
		font-size: clamp(1.6rem, 4vw, 2.25rem);
		font-weight: 700;
		color: #f0ece4;
		letter-spacing: -0.02em;
		margin-bottom: 1rem;
	}

	h3 {
		font-family: 'Playfair Display', serif;
		font-size: 1.2rem;
		color: #f0ece4;
		margin-bottom: 0.75rem;
	}

	p {
		color: #c0b89e;
		line-height: 1.75;
		margin-bottom: 1.25rem;
	}

	a {
		color: #c9a96e;
		text-decoration: underline;
		text-underline-offset: 3px;
	}

	a:hover {
		color: #f0ece4;
	}

	code {
		font-family: 'Courier New', monospace;
		font-size: 0.875em;
		background: rgba(201, 169, 110, 0.12);
		color: #c9a96e;
		padding: 0.15em 0.4em;
		border-radius: 4px;
	}

	pre {
		background: #161616;
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: 8px;
		padding: 1rem 1.25rem;
		overflow-x: auto;
		margin: 0.75rem 0;
	}

	pre code {
		background: none;
		padding: 0;
		color: #d4c5a0;
		font-size: 0.9rem;
		line-height: 1.6;
	}

	/* ---- Tool grid ---- */
	.tool-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
		gap: 1.25rem;
		margin-top: 1.5rem;
	}

	.tool-card {
		background: #161616;
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: 12px;
		padding: 1.5rem;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.tool-icon {
		font-size: 1.75rem;
	}

	.tool-card h3 {
		font-family: 'Playfair Display', serif;
		font-size: 1.1rem;
		color: #f0ece4;
		margin: 0;
	}

	.tool-card p {
		font-size: 0.9rem;
		color: #a09880;
		margin: 0;
	}

	.tool-link {
		display: inline-block;
		margin-top: 0.25rem;
		font-size: 0.875rem;
		font-weight: 500;
		color: #c9a96e;
		text-decoration: none;
	}

	.tool-link:hover {
		text-decoration: underline;
	}

	.install-note {
		margin-top: 0.5rem;
		font-size: 0.82rem;
		color: #7a7260;
		line-height: 1.5;
	}

	.install-note pre {
		margin-top: 0.4rem;
		padding: 0.6rem 0.85rem;
	}

	/* ---- Ordered list ---- */
	.instructions {
		padding-left: 1.5rem;
		display: flex;
		flex-direction: column;
		gap: 1rem;
		margin-top: 1rem;
	}

	.instructions li {
		color: #c0b89e;
		line-height: 1.75;
	}

	/* ---- Tip ---- */
	.tip {
		margin-top: 1.5rem;
		padding: 1rem 1.25rem;
		background: rgba(201, 169, 110, 0.07);
		border-left: 3px solid #c9a96e;
		border-radius: 0 8px 8px 0;
		font-size: 0.9rem;
		color: #a09880;
		line-height: 1.6;
	}

	/* ---- Framework picker ---- */
	.framework-picker {
		display: flex;
		gap: 1rem;
		margin: 1.5rem 0;
		flex-wrap: wrap;
	}

	.framework-btn {
		display: flex;
		align-items: center;
		gap: 0.6rem;
		padding: 0.85rem 1.5rem;
		background: #161616;
		border: 1px solid rgba(255, 255, 255, 0.1);
		border-radius: 10px;
		color: #a09880;
		cursor: pointer;
		font-family: 'DM Sans', sans-serif;
		font-size: 0.95rem;
		transition:
			border-color 0.2s,
			color 0.2s,
			background 0.2s;
	}

	.framework-btn:hover,
	.framework-btn.active {
		border-color: #c9a96e;
		color: #f0ece4;
		background: rgba(201, 169, 110, 0.1);
	}

	.fw-icon {
		font-size: 1.2rem;
	}

	.fw-name {
		font-weight: 500;
	}

	.fw-tag {
		font-size: 0.7rem;
		background: rgba(201, 169, 110, 0.15);
		color: #c9a96e;
		padding: 0.15em 0.5em;
		border-radius: 4px;
		font-weight: 500;
		letter-spacing: 0.05em;
	}

	.framework-detail {
		margin-top: 1rem;
		padding: 1.5rem;
		background: #161616;
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: 12px;
	}

	.picker-hint {
		color: #7a7260;
		font-style: italic;
		margin-top: 0.5rem;
	}

	/* ---- Prompt box ---- */
	.prompt-box {
		margin: 1.5rem 0;
		background: #161616;
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: 12px;
		overflow: hidden;
	}

	.prompt-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0.75rem 1.25rem;
		background: rgba(255, 255, 255, 0.04);
		border-bottom: 1px solid rgba(255, 255, 255, 0.06);
		font-size: 0.85rem;
		font-weight: 500;
		color: #a09880;
	}

	.copy-btn {
		font-family: 'DM Sans', sans-serif;
		font-size: 0.78rem;
		padding: 0.3em 0.8em;
		background: rgba(201, 169, 110, 0.12);
		border: 1px solid rgba(201, 169, 110, 0.3);
		border-radius: 5px;
		color: #c9a96e;
		cursor: pointer;
		transition: background 0.2s;
	}

	.copy-btn:hover {
		background: rgba(201, 169, 110, 0.22);
	}

	.prompt-text {
		padding: 1.25rem;
		font-size: 0.85rem;
		white-space: pre-wrap;
		line-height: 1.65;
		color: #c0b89e;
		background: none;
		border: none;
		border-radius: 0;
		margin: 0;
		font-family: 'Courier New', monospace;
	}

	.prompt-placeholder {
		margin: 1.5rem 0;
		padding: 1.5rem;
		background: #161616;
		border: 1px dashed rgba(255, 255, 255, 0.1);
		border-radius: 12px;
		text-align: center;
	}

	.prompt-placeholder p {
		color: #7a7260;
		margin: 0;
	}

	/* ---- Footer ---- */
	footer {
		margin-top: 5rem;
		padding-top: 2rem;
		border-top: 1px solid rgba(255, 255, 255, 0.07);
		text-align: center;
	}

	footer p {
		color: #7a7260;
		font-size: 0.875rem;
	}
</style>
