<script>
	import { onMount } from "svelte";

	let scrolled = false;
	let mobileMenuOpen = false;

	onMount(() => {
		const handleScroll = () => {
			scrolled = window.scrollY > 50;
		};

		window.addEventListener("scroll", handleScroll);
		return () => window.removeEventListener("scroll", handleScroll);
	});

	function toggleMobileMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}

	function closeMobileMenu() {
		mobileMenuOpen = false;
	}
</script>

<nav class="navbar" class:scrolled>
	<div class="container">
		<div class="nav-content">
			<a href="/" class="logo">
				<img
					src="/images/logo2.png"
					alt="SunWorld Building Materials Logo"
					class="logo-img"
				/>
			</a>

			<div class="nav-links" class:open={mobileMenuOpen}>
				<a href="#about" on:click={closeMobileMenu}>About</a>
				<a href="#products" on:click={closeMobileMenu}>Products</a>
				<a href="#branches" on:click={closeMobileMenu}>Locations</a>
				<a href="#contact" class="nav-cta" on:click={closeMobileMenu}
					>Contact Us</a
				>
			</div>

			<button
				class="mobile-toggle"
				on:click={toggleMobileMenu}
				aria-label="Toggle menu"
			>
				<span class="burger-line" class:open={mobileMenuOpen}></span>
				<span class="burger-line" class:open={mobileMenuOpen}></span>
				<span class="burger-line" class:open={mobileMenuOpen}></span>
			</button>
		</div>
	</div>
</nav>

<style>
	.navbar {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		z-index: 1000;
		background: transparent;
		transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
		padding: 1.5rem 0;
	}

	/* Ensure navbar stays above other content */
	.navbar {
		z-index: 10000 !important;
	}

	.navbar.scrolled {
		background: rgba(43, 43, 43, 0.95);
		backdrop-filter: blur(10px);
		padding: 0.75rem 0; /* Slightly reduced padding when scrolled on mobile */
		box-shadow: 0 4px 24px rgba(0, 0, 0, 0.1);
	}

	@media (max-width: 768px) {
		.navbar.scrolled {
			padding: 0.75rem 0; /* Consistent padding when scrolled on mobile */
		}
	}

	.container {
		max-width: 1400px;
		margin: 0 auto;
		padding: 0 2rem;
	}

	.nav-content {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	@media (max-width: 768px) {
		.nav-content {
			justify-content: space-between; /* Ensure logo and menu button stay apart */
		}
	}

	.logo {
		display: flex;
		flex-direction: column;
		text-decoration: none;
		transition: transform 0.3s ease;
		align-items: center; /* Center the logo */
		justify-content: center;
	}

	.logo:hover {
		transform: translateY(-2px);
	}

	.logo-img {
		height: 40px;
		width: auto;
		object-fit: contain;
	}

	.nav-links {
		display: flex;
		align-items: center;
		gap: 3rem;
	}

	@media (max-width: 768px) {
		.logo-img {
			height: 60px; /* Adjusted size for actual logo on mobile */
			width: auto;
		}

		.navbar {
			padding: 1rem 0; /* Adjust padding on mobile to prevent overlap */
		}
	}

	.nav-links a {
		color: var(--color-concrete);
		text-decoration: none;
		font-weight: 500;
		font-size: 0.95rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		position: relative;
		transition: color 0.3s ease;
	}

	.nav-links a:not(.nav-cta)::after {
		content: "";
		position: absolute;
		bottom: -4px;
		left: 0;
		width: 0;
		height: 2px;
		background: var(--color-terracotta);
		transition: width 0.3s ease;
	}

	.nav-links a:not(.nav-cta):hover::after {
		width: 100%;
	}

	.nav-links a:hover {
		color: var(--color-white);
	}

	.nav-cta {
		padding: 0.75rem 1.5rem;
		background: var(--color-terracotta);
		color: var(--color-white) !important;
		border-radius: 2px;
		transition: all 0.3s ease;
	}

	.nav-cta:hover {
		background: var(--color-deep-terracotta);
		transform: translateY(-2px);
		box-shadow: 0 4px 16px rgba(212, 133, 106, 0.4);
	}

	.mobile-toggle {
		display: none;
		flex-direction: column;
		gap: 5px;
		background: none;
		border: none;
		cursor: pointer;
		padding: 0.5rem;
	}

	.burger-line {
		width: 28px;
		height: 3px;
		background: var(--color-white);
		border-radius: 2px;
		transition: all 0.3s ease;
	}

	.burger-line.open:nth-child(1) {
		transform: rotate(45deg) translateY(8px);
	}

	.burger-line.open:nth-child(2) {
		opacity: 0;
	}

	.burger-line.open:nth-child(3) {
		transform: rotate(-45deg) translateY(-8px);
	}

	@media (max-width: 768px) {
		.mobile-toggle {
			display: flex;
		}

		.nav-links {
			position: fixed;
			top: 0;
			right: -100%;
			width: 80%;
			max-width: 300px;
			height: 100vh;
			background: var(--color-charcoal);
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 2rem;
			transition: right 0.4s cubic-bezier(0.16, 1, 0.3, 1);
			box-shadow: -4px 0 24px rgba(0, 0, 0, 0.3);
		}

		.nav-links.open {
			right: 0;
		}

		.nav-links a {
			font-size: 1.25rem;
		}
	}
</style>
