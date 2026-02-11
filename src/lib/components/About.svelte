<section class="about" id="about">
	<div class="container">
		<div class="about-grid">
			<div class="about-content">
				<div class="section-label">Our Story</div>
				<h2 class="section-title">Excellence in Building Materials</h2>
				<div class="about-text serif">
					<p>
						Sun World Building Materials Trading LLC is one of the leading distributors and retailers
						of building materials in the UAE. Established in 2004, we have built a strong reputation
						for providing high-quality building materials including structural steel, marine and plywood timber,
						waterproofing systems, paints, cement, safety equipment and clothing.
					</p>
					<p>
						With our strategic location in Ras Al Khor Industrial Area and comprehensive inventory,
						we serve contractors, developers, and individual builders across the UAE with reliable
						supply and competitive pricing.
					</p>
				</div>
				<div class="about-features">
					<div class="feature">
						<div class="feature-icon">✦</div>
						<div class="feature-text">
							<div class="feature-title">Wide Range</div>
							<div class="feature-desc">Comprehensive selection of building materials</div>
						</div>
					</div>
					<div class="feature">
						<div class="feature-icon">✦</div>
						<div class="feature-text">
							<div class="feature-title">Quality Products</div>
							<div class="feature-desc">Trusted brands and materials</div>
						</div>
					</div>
					<div class="feature">
						<div class="feature-icon">✦</div>
						<div class="feature-text">
							<div class="feature-title">Reliable Service</div>
							<div class="feature-desc">Consistent supply and delivery</div>
						</div>
					</div>
				</div>
			</div>
			<div class="about-visual">
				<div class="visual-card card-1">
					<div class="card-inner">
						<div class="card-number">2004</div>
						<div class="card-label">Established</div>
					</div>
				</div>
				<div class="visual-card card-2">
					<div class="card-inner">
						<div class="card-number">Wide</div>
						<div class="card-label">Range</div>
					</div>
				</div>
				<div class="visual-card card-3">
					<div class="card-inner">
						<div class="card-number">UAE</div>
						<div class="card-label">Coverage</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<style>
	.about {
		padding: 8rem 0;
		background: var(--color-sand);
		position: relative;
	}
	
	.about::before {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		height: 1px;
		background: linear-gradient(90deg, transparent, var(--color-terracotta), transparent);
	}
	
	.container {
		max-width: 1400px;
		margin: 0 auto;
		padding: 0 2rem;
	}
	
	.about-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 6rem;
		align-items: center;
	}
	
	.section-label {
		font-size: 0.875rem;
		color: var(--color-terracotta);
		text-transform: uppercase;
		letter-spacing: 0.2em;
		font-weight: 600;
		margin-bottom: 1rem;
	}
	
	.section-title {
		font-size: clamp(2.5rem, 5vw, 4rem);
		color: var(--color-charcoal);
		margin-bottom: 2rem;
		line-height: 1;
	}
	
	.about-text {
		font-size: 1.125rem;
		line-height: 1.8;
		color: var(--color-slate);
		margin-bottom: 3rem;
	}
	
	.about-text p {
		margin-bottom: 1.5rem;
	}
	
	.about-features {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}
	
	.feature {
		display: flex;
		align-items: flex-start;
		gap: 1rem;
	}
	
	.feature-icon {
		font-size: 1.5rem;
		color: var(--color-gold);
		flex-shrink: 0;
	}
	
	.feature-title {
		font-family: var(--font-body);
		font-size: 1.125rem;
		font-weight: 600;
		color: var(--color-charcoal);
		margin-bottom: 0.25rem;
	}
	
	.feature-desc {
		font-size: 0.875rem;
		color: var(--color-slate);
	}
	
	.about-visual {
		position: relative;
		height: 600px;
	}
	
	.visual-card {
		position: absolute;
		width: 280px;
		height: 200px;
		background: var(--color-white);
		border-radius: 4px;
		box-shadow: var(--shadow-lg);
		transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
	}
	
	.visual-card:hover {
		transform: translateY(-10px) scale(1.02);
	}
	
	.card-1 {
		top: 0;
		left: 0;
		background: linear-gradient(135deg, var(--color-terracotta), var(--color-deep-terracotta));
	}
	
	.card-2 {
		top: 50%;
		right: 0;
		transform: translateY(-50%);
		background: linear-gradient(135deg, var(--color-gold), #B89860);
	}
	
	.card-3 {
		bottom: 0;
		left: 20%;
		background: linear-gradient(135deg, var(--color-charcoal), #1a1a1a);
	}
	
	.card-inner {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100%;
		padding: 2rem;
		color: var(--color-white);
	}
	
	.card-number {
		font-family: var(--font-display);
		font-size: 4rem;
		line-height: 1;
		margin-bottom: 0.5rem;
	}
	
	.card-label {
		font-size: 1rem;
		text-transform: uppercase;
		letter-spacing: 0.15em;
		opacity: 0.9;
	}
	
	@media (max-width: 1024px) {
		.about-grid {
			grid-template-columns: 1fr;
			gap: 4rem;
		}
		
		.about-visual {
			height: 400px;
			margin: 0 auto;
			max-width: 500px;
		}
		
		.visual-card {
			width: 200px;
			height: 150px;
		}
		
		.card-number {
			font-size: 3rem;
		}
	}
	
	@media (max-width: 768px) {
		.about {
			padding: 4rem 0;
		}
		
		.about-visual {
			display: none;
		}
	}
</style>
