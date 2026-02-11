<script>
	const currentYear = new Date().getFullYear();
</script>

<footer class="footer">
	<div class="container">
		<div class="footer-top">
			<div class="footer-brand">
				<h3 class="brand-name">Sun World</h3>
				<p class="brand-tagline serif">Building Materials Trading LLC</p>
				<p class="brand-desc">
					Your trusted partner for premium building materials across the UAE since 2004.
				</p>
			</div>

			<div class="footer-links">
				<div class="footer-column">
					<h4 class="column-title">Quick Links</h4>
					<ul>
						<li><a href="#about">About Us</a></li>
						<li><a href="#products">Products</a></li>
						<li><a href="#branches">Locations</a></li>
						<li><a href="#contact">Contact</a></li>
					</ul>
				</div>

				<div class="footer-column">
					<h4 class="column-title">Products</h4>
					<ul>
						<li><a href="#products">Structural Steel</a></li>
						<li><a href="#products">Timber & Plywood</a></li>
						<li><a href="#products">Safety Equipment</a></li>
						<li><a href="#products">Waterproofing</a></li>
					</ul>
				</div>

				<div class="footer-column">
					<h4 class="column-title">Support</h4>
					<ul>
						<li><a href="#contact">Get a Quote</a></li>
						<li><a href="#contact">Customer Service</a></li>
						<li><a href="#branches">Find a Store</a></li>
						<li><a href="#contact">Technical Support</a></li>
					</ul>
				</div>

				<div class="footer-column">
					<h4 class="column-title">Connect</h4>
					<ul>
						<li><a href="tel:+97143536209">+971 4 353 6209</a></li>
						<li><a href="mailto:info@sunworldbmt.com">info@sunworldbmt.com</a></li>
						<li><a href="tel:+97143536309">+971 4 353 6309 (Fax)</a></li>
						<li>Ras Al Khor, Dubai, UAE</li>
					</ul>
				</div>
			</div>
		</div>

		<div class="footer-bottom">
			<div class="copyright">
				<p>&copy; {currentYear} Sun World Building Materials Trading LLC. All rights reserved.</p>
			</div>
			<div class="footer-meta">
				<a href="#privacy">Privacy Policy</a>
				<span class="divider">|</span>
				<a href="#terms">Terms of Service</a>
			</div>
		</div>
	</div>
</footer>

<style>
	.footer {
		background: var(--color-charcoal);
		color: var(--color-concrete);
		padding: 5rem 0 2rem;
	}
	
	.container {
		max-width: 1400px;
		margin: 0 auto;
		padding: 0 2rem;
	}
	
	.footer-top {
		display: grid;
		grid-template-columns: 1.5fr 2fr;
		gap: 4rem;
		padding-bottom: 4rem;
		border-bottom: 1px solid rgba(255, 255, 255, 0.1);
	}
	
	.brand-name {
		font-size: 3rem;
		color: var(--color-white);
		margin-bottom: 0.25rem;
	}
	
	.brand-tagline {
		font-size: 1.125rem;
		color: var(--color-gold);
		font-style: italic;
		margin-bottom: 1.5rem;
	}
	
	.brand-desc {
		font-size: 0.95rem;
		line-height: 1.7;
		color: var(--color-concrete);
		max-width: 400px;
	}
	
	.footer-links {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 2rem;
	}
	
	.column-title {
		font-family: var(--font-body);
		font-size: 1rem;
		font-weight: 600;
		color: var(--color-white);
		text-transform: uppercase;
		letter-spacing: 0.1em;
		margin-bottom: 1.5rem;
	}
	
	.footer-column ul {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 0.75rem;
	}
	
	.footer-column a {
		color: var(--color-concrete);
		text-decoration: none;
		font-size: 0.95rem;
		transition: color 0.3s ease;
		display: inline-block;
	}
	
	.footer-column a:hover {
		color: var(--color-terracotta);
		transform: translateX(4px);
	}
	
	.footer-column li {
		font-size: 0.95rem;
		color: var(--color-concrete);
	}
	
	.footer-bottom {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-top: 2rem;
		flex-wrap: wrap;
		gap: 1rem;
	}
	
	.copyright p {
		font-size: 0.875rem;
		color: var(--color-slate);
	}
	
	.footer-meta {
		display: flex;
		align-items: center;
		gap: 1rem;
	}
	
	.footer-meta a {
		color: var(--color-slate);
		text-decoration: none;
		font-size: 0.875rem;
		transition: color 0.3s ease;
	}
	
	.footer-meta a:hover {
		color: var(--color-gold);
	}
	
	.divider {
		color: var(--color-slate);
	}
	
	@media (max-width: 1024px) {
		.footer-top {
			grid-template-columns: 1fr;
			gap: 3rem;
		}
		
		.footer-links {
			grid-template-columns: repeat(2, 1fr);
		}
	}
	
	@media (max-width: 640px) {
		.footer {
			padding: 3rem 0 2rem;
		}
		
		.footer-links {
			grid-template-columns: 1fr;
		}
		
		.footer-bottom {
			flex-direction: column;
			text-align: center;
		}
	}
</style>
