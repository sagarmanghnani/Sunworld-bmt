<script>
	import { onMount } from 'svelte';
	
	let loaded = false;
	
	onMount(() => {
		setTimeout(() => loaded = true, 100);
	});
</script>

<section class="hero">
	<div class="hero-overlay"></div>
	<div class="hero-pattern"></div>
	
	<div class="hero-content" class:loaded>
		<div class="hero-badge">
			<span>Established 2004</span>
		</div>
		
		<h1 class="hero-title">
			<span class="line">Sun World</span>
			<span class="line delay-1">Building Materials</span>
			<span class="line delay-2">Trading LLC</span>
		</h1>

		<p class="hero-subtitle serif">
			Leading distributor and retailer of premium building materials across the UAE since 2004
		</p>

		<div class="hero-stats">
			<div class="stat">
				<div class="stat-number">17+</div>
				<div class="stat-label">Years Experience</div>
			</div>
			<div class="stat-divider"></div>
			<div class="stat">
				<div class="stat-number">Wide</div>
				<div class="stat-label">Range</div>
			</div>
			<div class="stat-divider"></div>
			<div class="stat">
				<div class="stat-number">UAE</div>
				<div class="stat-label">Nationwide</div>
			</div>
		</div>
		
		<div class="hero-cta">
			<a href="#products" class="btn-primary">Explore Products</a>
			<a href="#contact" class="btn-secondary">Get in Touch</a>
		</div>
	</div>
	
	<div class="scroll-indicator">
		<span>Scroll</span>
		<div class="scroll-line"></div>
	</div>
</section>

<style>
	.hero {
		position: relative;
		min-height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		background: linear-gradient(135deg, var(--color-charcoal) 0%, #1a1a1a 100%);
		overflow: hidden;
	}
	
	.hero-overlay {
		position: absolute;
		inset: 0;
		background: radial-gradient(circle at 30% 20%, rgba(212, 133, 106, 0.15) 0%, transparent 50%),
		            radial-gradient(circle at 70% 80%, rgba(201, 168, 112, 0.1) 0%, transparent 50%);
		pointer-events: none;
	}
	
	.hero-pattern {
		position: absolute;
		inset: 0;
		background-image: 
			repeating-linear-gradient(90deg, rgba(255,255,255,0.02) 0px, transparent 1px, transparent 40px, rgba(255,255,255,0.02) 41px),
			repeating-linear-gradient(0deg, rgba(255,255,255,0.02) 0px, transparent 1px, transparent 40px, rgba(255,255,255,0.02) 41px);
		opacity: 0.5;
	}
	
	.hero-content {
		position: relative;
		z-index: 10;
		text-align: center;
		max-width: 1200px;
		padding: 2rem;
		padding-top: 6rem; /* Add extra top padding to prevent overlap with navbar */
		opacity: 0;
		transform: translateY(30px);
		transition: all 1s cubic-bezier(0.16, 1, 0.3, 1);
	}
	
	@media (max-width: 768px) {
		.hero-content {
			padding-top: 8rem; /* More padding on mobile to account for navbar */
		}
	}
	
	.hero-content.loaded {
		opacity: 1;
		transform: translateY(0);
	}
	
	.hero-badge {
		display: inline-block;
		padding: 0.5rem 1.5rem;
		background: rgba(212, 133, 106, 0.2);
		border: 1px solid var(--color-terracotta);
		border-radius: 50px;
		color: var(--color-light-gold);
		font-size: 0.875rem;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		margin-bottom: 2rem;
		font-weight: 500;
		position: relative;
		top: 0;
	}
	
	@media (max-width: 768px) {
		.hero-badge {
			margin-top: 1rem; /* Add margin on mobile to ensure spacing */
		}
	}
	
	.hero-title {
		font-size: clamp(3rem, 12vw, 8rem);
		color: var(--color-white);
		margin-bottom: 1.5rem;
		line-height: 0.9;
	}
	
	.hero-title .line {
		display: block;
		opacity: 0;
		transform: translateY(40px);
		animation: slideInLeft 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
	}
	
	.line.delay-1 {
		animation-delay: 0.15s;
	}
	
	.line.delay-2 {
		animation-delay: 0.3s;
		color: var(--color-terracotta);
	}
	
	.hero-subtitle {
		font-size: clamp(1.25rem, 3vw, 2rem);
		color: var(--color-concrete);
		max-width: 700px;
		margin: 0 auto 3rem;
		font-weight: 300;
		font-style: italic;
	}
	
	.hero-stats {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 2rem;
		margin-bottom: 3rem;
		flex-wrap: wrap;
	}
	
	.stat {
		text-align: center;
	}
	
	.stat-number {
		font-family: var(--font-display);
		font-size: clamp(2rem, 4vw, 3.5rem);
		color: var(--color-gold);
		line-height: 1;
		margin-bottom: 0.5rem;
	}
	
	.stat-label {
		font-size: 0.875rem;
		color: var(--color-concrete);
		text-transform: uppercase;
		letter-spacing: 0.15em;
	}
	
	.stat-divider {
		width: 1px;
		height: 50px;
		background: linear-gradient(to bottom, transparent, var(--color-slate), transparent);
	}
	
	.hero-cta {
		display: flex;
		gap: 1.5rem;
		justify-content: center;
		flex-wrap: wrap;
	}
	
	.btn-primary,
	.btn-secondary {
		padding: 1rem 2.5rem;
		font-family: var(--font-body);
		font-size: 1rem;
		font-weight: 500;
		text-decoration: none;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		border-radius: 2px;
		transition: all 0.3s ease;
		display: inline-block;
	}
	
	.btn-primary {
		background: var(--color-terracotta);
		color: var(--color-white);
		border: 2px solid var(--color-terracotta);
	}
	
	.btn-primary:hover {
		background: var(--color-deep-terracotta);
		border-color: var(--color-deep-terracotta);
		transform: translateY(-2px);
		box-shadow: 0 8px 24px rgba(212, 133, 106, 0.3);
	}
	
	.btn-secondary {
		background: transparent;
		color: var(--color-white);
		border: 2px solid var(--color-gold);
	}
	
	.btn-secondary:hover {
		background: var(--color-gold);
		color: var(--color-charcoal);
		transform: translateY(-2px);
	}
	
	.scroll-indicator {
		position: absolute;
		bottom: 3rem;
		left: 50%;
		transform: translateX(-50%);
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
		color: var(--color-concrete);
		font-size: 0.75rem;
		letter-spacing: 0.2em;
		text-transform: uppercase;
	}
	
	.scroll-line {
		width: 1px;
		height: 60px;
		background: linear-gradient(to bottom, var(--color-gold), transparent);
		animation: scrollPulse 2s infinite;
	}
	
	@keyframes scrollPulse {
		0%, 100% {
			opacity: 0.3;
			transform: scaleY(1);
		}
		50% {
			opacity: 1;
			transform: scaleY(1.2);
		}
	}
	
	@media (max-width: 768px) {
		.hero-stats {
			gap: 1rem;
		}
		
		.stat-divider {
			display: none;
		}
		
		.hero-cta {
			flex-direction: column;
			align-items: stretch;
			padding: 0 1rem;
		}
	}
</style>
