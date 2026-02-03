<script>
	const branches = [
		{
			city: 'Dubai',
			area: 'Al Quoz',
			type: 'Main Showroom & Warehouse',
			phone: '+971 4 XXX XXXX',
			hours: 'Sat-Thu: 8:00 AM - 8:00 PM'
		},
		{
			city: 'Abu Dhabi',
			area: 'Mussafah',
			type: 'Showroom & Warehouse',
			phone: '+971 2 XXX XXXX',
			hours: 'Sat-Thu: 8:00 AM - 7:00 PM'
		},
		{
			city: 'Sharjah',
			area: 'Industrial Area',
			type: 'Distribution Center',
			phone: '+971 6 XXX XXXX',
			hours: 'Sat-Thu: 8:00 AM - 7:00 PM'
		},
		{
			city: 'Ajman',
			area: 'New Industrial',
			type: 'Warehouse',
			phone: '+971 6 XXX XXXX',
			hours: 'Sat-Thu: 8:00 AM - 6:00 PM'
		},
		{
			city: 'Ras Al Khaimah',
			area: 'Industrial Zone',
			type: 'Showroom',
			phone: '+971 7 XXX XXXX',
			hours: 'Sat-Thu: 8:00 AM - 6:00 PM'
		},
		{
			city: 'Fujairah',
			area: 'Sakamkam',
			type: 'Distribution Point',
			phone: '+971 9 XXX XXXX',
			hours: 'Sat-Thu: 8:00 AM - 6:00 PM'
		}
	];
</script>

<section class="branches" id="branches">
	<div class="container">
		<div class="section-header">
			<div class="section-label">Nationwide Presence</div>
			<h2 class="section-title">Visit Our Locations</h2>
			<p class="section-subtitle serif">
				Strategically located across the UAE for your convenience
			</p>
		</div>
		
		<div class="branches-grid">
			{#each branches as branch, i}
				<div class="branch-card" style="animation-delay: {i * 0.08}s">
					<div class="branch-header">
						<h3 class="branch-city">{branch.city}</h3>
						<span class="branch-type">{branch.type}</span>
					</div>
					<div class="branch-details">
						<div class="detail-item">
							<span class="detail-icon">📍</span>
							<span class="detail-text">{branch.area}</span>
						</div>
						<div class="detail-item">
							<span class="detail-icon">📞</span>
							<span class="detail-text">{branch.phone}</span>
						</div>
						<div class="detail-item">
							<span class="detail-icon">🕒</span>
							<span class="detail-text">{branch.hours}</span>
						</div>
					</div>
					<div class="branch-action">
						<a href="#contact" class="branch-link">Get Directions →</a>
					</div>
				</div>
			{/each}
		</div>
		
		<div class="map-placeholder">
			<div class="map-content">
				<div class="map-icon">🗺️</div>
				<h3 class="map-title">UAE Coverage Map</h3>
				<p class="map-text">Serving all seven emirates with dedication and excellence</p>
			</div>
		</div>
	</div>
</section>

<style>
	.branches {
		padding: 8rem 0;
		background: var(--color-sand);
		position: relative;
	}
	
	.branches::before {
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
	
	.branches-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
		gap: 2rem;
		margin-bottom: 4rem;
	}
	
	.branch-card {
		background: var(--color-white);
		padding: 2rem;
		border-radius: 4px;
		border-left: 4px solid var(--color-terracotta);
		transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
		opacity: 0;
		animation: fadeInUp 0.8s ease-out forwards;
	}
	
	.branch-card:hover {
		transform: translateX(8px);
		box-shadow: var(--shadow-md);
		border-left-color: var(--color-gold);
	}
	
	.branch-header {
		margin-bottom: 1.5rem;
		padding-bottom: 1rem;
		border-bottom: 1px solid var(--color-concrete);
	}
	
	.branch-city {
		font-size: 2rem;
		color: var(--color-charcoal);
		margin-bottom: 0.5rem;
	}
	
	.branch-type {
		display: inline-block;
		font-size: 0.75rem;
		padding: 0.3rem 0.8rem;
		background: rgba(212, 133, 106, 0.1);
		color: var(--color-terracotta);
		border-radius: 20px;
		text-transform: uppercase;
		letter-spacing: 0.05em;
		font-weight: 600;
	}
	
	.branch-details {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		margin-bottom: 1.5rem;
	}
	
	.detail-item {
		display: flex;
		align-items: center;
		gap: 0.75rem;
	}
	
	.detail-icon {
		font-size: 1.25rem;
		flex-shrink: 0;
	}
	
	.detail-text {
		font-size: 0.95rem;
		color: var(--color-slate);
	}
	
	.branch-action {
		padding-top: 1rem;
		border-top: 1px solid var(--color-concrete);
	}
	
	.branch-link {
		color: var(--color-terracotta);
		text-decoration: none;
		font-weight: 600;
		font-size: 0.95rem;
		transition: all 0.3s ease;
		display: inline-block;
	}
	
	.branch-link:hover {
		color: var(--color-gold);
		transform: translateX(4px);
	}
	
	.map-placeholder {
		background: linear-gradient(135deg, var(--color-charcoal), #1a1a1a);
		border-radius: 8px;
		padding: 5rem 2rem;
		text-align: center;
		position: relative;
		overflow: hidden;
	}
	
	.map-placeholder::before {
		content: '';
		position: absolute;
		inset: 0;
		background: radial-gradient(circle at 50% 50%, rgba(201, 168, 112, 0.1) 0%, transparent 70%);
	}
	
	.map-content {
		position: relative;
		z-index: 2;
	}
	
	.map-icon {
		font-size: 4rem;
		margin-bottom: 1.5rem;
	}
	
	.map-title {
		font-size: 2.5rem;
		color: var(--color-white);
		margin-bottom: 1rem;
	}
	
	.map-text {
		font-family: var(--font-serif);
		font-size: 1.25rem;
		color: var(--color-concrete);
		font-style: italic;
	}
	
	@media (max-width: 768px) {
		.branches {
			padding: 4rem 0;
		}
		
		.branches-grid {
			grid-template-columns: 1fr;
			gap: 1.5rem;
		}
		
		.map-placeholder {
			padding: 3rem 1.5rem;
		}
	}
</style>
