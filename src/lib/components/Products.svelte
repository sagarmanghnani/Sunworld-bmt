<script>
	const categories = [
		{
			name: 'Cement & Concrete',
			description: 'Premium quality cement and ready-mix concrete solutions',
			icon: '🏗️',
			products: ['Portland Cement', 'Ready-Mix Concrete', 'Masonry Cement']
		},
		{
			name: 'Steel & Rebar',
			description: 'High-grade steel products for structural integrity',
			icon: '⚙️',
			products: ['Reinforcement Bars', 'Steel Beams', 'Wire Mesh']
		},
		{
			name: 'Bricks & Blocks',
			description: 'Diverse range of construction blocks and bricks',
			icon: '🧱',
			products: ['Concrete Blocks', 'Clay Bricks', 'Hollow Blocks']
		},
		{
			name: 'Tiles & Flooring',
			description: 'Elegant flooring solutions for every space',
			icon: '◼️',
			products: ['Ceramic Tiles', 'Porcelain', 'Natural Stone']
		},
		{
			name: 'Paints & Coatings',
			description: 'Professional-grade paints and protective coatings',
			icon: '🎨',
			products: ['Interior Paint', 'Exterior Paint', 'Waterproofing']
		},
		{
			name: 'Plumbing & Sanitary',
			description: 'Complete plumbing and sanitary solutions',
			icon: '🚰',
			products: ['Pipes & Fittings', 'Fixtures', 'Water Heaters']
		},
		{
			name: 'Electrical',
			description: 'Comprehensive electrical supplies and components',
			icon: '⚡',
			products: ['Cables', 'Switches', 'Lighting Fixtures']
		},
		{
			name: 'Insulation',
			description: 'Thermal and acoustic insulation materials',
			icon: '🛡️',
			products: ['Foam Boards', 'Mineral Wool', 'Reflective Insulation']
		}
	];
</script>

<section class="products" id="products">
	<div class="container">
		<div class="section-header">
			<div class="section-label">Our Range</div>
			<h2 class="section-title">30,000+ Premium Products</h2>
			<p class="section-subtitle serif">
				From foundation to finish, we provide everything you need for your building project
			</p>
		</div>
		
		<div class="products-grid">
			{#each categories as category, i}
				<div class="product-card" style="animation-delay: {i * 0.1}s">
					<div class="card-icon">{category.icon}</div>
					<h3 class="card-title">{category.name}</h3>
					<p class="card-description">{category.description}</p>
					<div class="card-products">
						{#each category.products as product}
							<span class="product-tag">{product}</span>
						{/each}
					</div>
					<div class="card-arrow">→</div>
				</div>
			{/each}
		</div>
		
		<div class="products-cta">
			<p class="cta-text">Looking for something specific?</p>
			<a href="#contact" class="btn-contact">Request a Quote</a>
		</div>
	</div>
</section>

<style>
	.products {
		padding: 8rem 0;
		background: var(--color-white);
		position: relative;
	}
	
	.products::before {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		height: 1px;
		background: linear-gradient(90deg, transparent, var(--color-gold), transparent);
	}
	
	.container {
		max-width: 1400px;
		margin: 0 auto;
		padding: 0 2rem;
	}
	
	.section-header {
		text-align: center;
		max-width: 800px;
		margin: 0 auto 5rem;
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
		margin-bottom: 1.5rem;
		line-height: 1;
	}
	
	.section-subtitle {
		font-size: 1.25rem;
		color: var(--color-slate);
		font-weight: 300;
		font-style: italic;
	}
	
	.products-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 2rem;
		margin-bottom: 5rem;
	}
	
	.product-card {
		background: var(--color-sand);
		padding: 2.5rem;
		border-radius: 4px;
		position: relative;
		transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
		border: 1px solid transparent;
		opacity: 0;
		animation: fadeInUp 0.8s ease-out forwards;
	}
	
	.product-card:hover {
		transform: translateY(-8px);
		box-shadow: var(--shadow-lg);
		border-color: var(--color-terracotta);
		background: var(--color-white);
	}
	
	.card-icon {
		font-size: 3rem;
		margin-bottom: 1.5rem;
		display: inline-block;
		transform: scale(1);
		transition: transform 0.3s ease;
	}
	
	.product-card:hover .card-icon {
		transform: scale(1.1);
	}
	
	.card-title {
		font-size: 1.75rem;
		color: var(--color-charcoal);
		margin-bottom: 0.75rem;
	}
	
	.card-description {
		font-size: 0.95rem;
		color: var(--color-slate);
		line-height: 1.6;
		margin-bottom: 1.5rem;
	}
	
	.card-products {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
		margin-bottom: 1rem;
	}
	
	.product-tag {
		font-size: 0.75rem;
		padding: 0.4rem 0.8rem;
		background: rgba(212, 133, 106, 0.1);
		color: var(--color-deep-terracotta);
		border-radius: 20px;
		font-weight: 500;
	}
	
	.card-arrow {
		position: absolute;
		bottom: 2rem;
		right: 2rem;
		font-size: 1.5rem;
		color: var(--color-terracotta);
		opacity: 0;
		transform: translateX(-10px);
		transition: all 0.3s ease;
	}
	
	.product-card:hover .card-arrow {
		opacity: 1;
		transform: translateX(0);
	}
	
	.products-cta {
		text-align: center;
		padding: 4rem 2rem;
		background: linear-gradient(135deg, var(--color-charcoal), #1a1a1a);
		border-radius: 8px;
		color: var(--color-white);
	}
	
	.cta-text {
		font-family: var(--font-serif);
		font-size: 1.5rem;
		font-style: italic;
		margin-bottom: 2rem;
		color: var(--color-concrete);
	}
	
	.btn-contact {
		display: inline-block;
		padding: 1rem 3rem;
		background: var(--color-terracotta);
		color: var(--color-white);
		text-decoration: none;
		font-weight: 600;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		border-radius: 2px;
		transition: all 0.3s ease;
		border: 2px solid var(--color-terracotta);
	}
	
	.btn-contact:hover {
		background: transparent;
		border-color: var(--color-gold);
		color: var(--color-gold);
		transform: translateY(-2px);
	}
	
	@media (max-width: 768px) {
		.products {
			padding: 4rem 0;
		}
		
		.section-header {
			margin-bottom: 3rem;
		}
		
		.products-grid {
			grid-template-columns: 1fr;
			gap: 1.5rem;
		}
		
		.products-cta {
			padding: 3rem 1.5rem;
		}
	}
</style>
