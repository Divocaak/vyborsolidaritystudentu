<script>
	import favicon from '#lib/assets/favicon.jpg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav>
	<!-- <div class="heading-row">
		<img src="/logo.jpg" alt="logo" /> -->
	<h1>VÝBOR SOLIDARITY STUDENTŮ</h1>
	<!-- </div> -->
	<div class="nav-row">
		<a href="/#protest">protest</a>
		<a href="/#co-se-deje">co se děje</a>
		<a href="/#aktualni-prohlaseni">aktuální prohlášení</a>
		<a href="/#kontakty">kontakty</a>
		<a
			href="https://docs.google.com/forms/d/e/1FAIpQLSfFS0qa8it1aV0O8JJEtRRJlWh7ipm4FwjK-NrxWuOu1HVmQQ/viewform"
			target="_blank"
		>
			kontaktní formulář
		</a>
	</div>
</nav>

{@render children()}

<footer>
	<p class="signature">
		Code & maintenance:
		<a href="https://divokyvojtech.cz/" target="_blank">Vojtěch Divoký</a>
	</p>
</footer>

<style>
	@font-face {
		font-family: 'TikTokSans';
		src: url('/TikTokSans-VariableFont_opsz,slnt,wdth,wght.ttf') format('truetype');
		font-style: normal;
		font-display: swap;
	}

	:global(:root) {
		--ui-scale: 1;

		--text-12: calc(clamp(0.6rem, 0.5rem + 0.2vw, 0.75rem) * var(--ui-scale));
		--text-16: calc(clamp(0.9rem, 0.8rem + 0.5vw, 1rem) * var(--ui-scale));
		--text-20: calc(clamp(1rem, 0.9rem + 0.6vw, 1.25rem) * var(--ui-scale));
		--text-24: calc(clamp(1.1rem, 1rem + 0.8vw, 1.5rem) * var(--ui-scale));
		--text-32: calc(clamp(1.3rem, 1.1rem + 1.2vw, 2rem) * var(--ui-scale));
		--text-36: calc(clamp(1.5rem, 1.2rem + 1.5vw, 2.25rem) * var(--ui-scale));
		--text-48: calc(clamp(1.8rem, 1.4rem + 2vw, 3rem) * var(--ui-scale));
		--text-64: calc(clamp(2.2rem, 1.8rem + 2.8vw, 4rem) * var(--ui-scale));
		--text-96: calc(clamp(3rem, 2.5rem + 4vw, 6rem) * var(--ui-scale));

		--gap: 5rem;

		--border-width: 5px;

		--color-primary: #f4e8db;
		--color-text: #f2e3d3;
		--color-accent: #383e55;
		--color-fx: #8d8a91;
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	:global(h1, h2, h3) {
		font-weight: 900;
	}
	:global(a),
	:global(.attention-text) {
		font-weight: 700;
	}

	:global(body) {
		background: linear-gradient(135deg, #33384f 0%, #1d233c 100%);
		color: var(--color-text);
		font-family: 'TikTokSans', sans-serif;
		font-weight: 400;
	}

	:global(h1) {
		font-size: var(--text-48);
	}

	:global(h2) {
		font-size: var(--text-36);
	}

	:global(p),
	:global(a) {
		font-size: var(--text-20);
		line-height: calc(var(--text-20) * 1.35);
	}

	:global(.attention-text) {
		background-color: var(--color-accent);
		font-weight: bold;
		padding: 5px 10px;
		border-radius: 5px;
	}

	footer,
	footer p,
	footer a {
		all: revert;
		color: var(--color-fx);
	}

	footer {
		margin-top: 400px;
	}

	footer p {
		text-align: end;
		font-size: xx-small;
	}

	:global(a) {
		text-decoration: none;
		text-transform: uppercase;
		font-weight: bold;
		color: var(--color-primary);

		display: inline-block;
		vertical-align: middle;
		position: relative;

		transform: perspective(1px) translateZ(0);
		transition:
			transform 0.3s ease,
			color 0.2s ease;
	}

	:global(a:hover),
	:global(a:focus),
	:global(a:active) {
		transform: scale(1.1);
	}

	nav {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 1rem;

		padding: 1rem var(--gap);
		border-bottom: var(--border-width) solid var(--color-primary);
	}

	nav .heading-row h1 {
		width: 100%;
		margin: 0;
		text-align: center;
		overflow-wrap: anywhere;
	}

	nav .nav-row {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;
		gap: 0.75rem 2rem;
		width: 100%;
	}

	/* nav .heading-row{
		display: flex;
		flex-direction: row;
	} */

	nav .heading-row img {
		height: 100px;
		width: auto;
	}

	nav a {
		text-align: center;
	}

	/* Tablets */
	@media (max-width: 1023px) {
		:global(:root) {
			--gap: 1.5rem;
		}
	}

	/* Mobile */
	@media (max-width: 599px) {
		:global(:root) {
			--gap: 1rem;
		}

		nav {
			padding: 1rem var(--gap);
			gap: 0.75rem;
		}

		nav h1 {
			font-size: var(--text-32);
			line-height: 1.15;
		}

		nav .nav-row {
			gap: 0.75rem 1rem;
		}

		nav a {
			max-width: 100%;
			font-size: var(--text-16);
			line-height: 1.4;
			overflow-wrap: anywhere;
		}
	}
</style>
