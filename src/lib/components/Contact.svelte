<script>
	let formData = {
		name: "",
		email: "",
		phone: "",
		company: "",
		message: "",
	};

	let submitted = false;

	function handleSubmit(e) {
		e.preventDefault();
		// In a real application, this would send data to a backend
		submitted = true;
		setTimeout(() => {
			submitted = false;
			formData = {
				name: "",
				email: "",
				phone: "",
				company: "",
				message: "",
			};
		}, 3000);
	}
</script>

<section class="contact" id="contact">
	<div class="container">
		<div class="contact-grid">
			<div class="contact-info">
				<div class="section-label">Get In Touch</div>
				<h2 class="section-title">Let's Build Together</h2>
				<p class="contact-text serif">
					Whether you're a contractor, developer, or individual
					builder, our team is ready to assist you with expert
					guidance and competitive quotes.
				</p>

				<div class="contact-details">
					<div class="contact-item">
						<div class="contact-icon">📧</div>
						<div class="contact-content">
							<div class="contact-label">Email</div>
							<a
								href="mailto:info@sunworldbmt.com"
								class="contact-value">info@sunworldbmt.com</a
							>
						</div>
					</div>

					<div class="contact-item">
						<div class="contact-icon">📞</div>
						<div class="contact-content">
							<div class="contact-label">Phone</div>
							<a href="tel:+97143536209" class="contact-value"
								>+971 4 353 6209</a
							>
						</div>
					</div>

					<div class="contact-item">
						<div class="contact-icon">📠</div>
						<div class="contact-content">
							<div class="contact-label">Fax</div>
							<a href="tel:+97143536309" class="contact-value"
								>+971 4 353 6309</a
							>
						</div>
					</div>

					<div class="contact-item">
						<div class="contact-icon">📍</div>
						<div class="contact-content">
							<div class="contact-label">Address</div>
							<div class="contact-value">
								PO Box: 51275, Ras Al Khor, Industrial Area No.2<br
								/>10-B Street, Warehouse #6 Dubai - UAE
							</div>
						</div>
					</div>
				</div>

				<div class="social-links">
					<a href="#" class="social-link" aria-label="LinkedIn">in</a>
					<a href="#" class="social-link" aria-label="Facebook">f</a>
					<a href="#" class="social-link" aria-label="Instagram">ig</a
					>
					<a
						href="https://wa.me/971558875696"
						target="_blank"
						rel="noopener noreferrer"
						class="social-link"
						aria-label="WhatsApp">wa</a
					>
				</div>
			</div>

			<div class="contact-form-wrapper">
				<form class="contact-form" on:submit={handleSubmit}>
					<div class="form-group">
						<label for="name">Full Name *</label>
						<input
							type="text"
							id="name"
							bind:value={formData.name}
							required
							placeholder="John Doe"
						/>
					</div>

					<div class="form-group">
						<label for="email">Email Address *</label>
						<input
							type="email"
							id="email"
							bind:value={formData.email}
							required
							placeholder="john@company.com"
						/>
					</div>

					<div class="form-group">
						<label for="phone">Phone Number *</label>
						<input
							type="tel"
							id="phone"
							bind:value={formData.phone}
							required
							placeholder="+971 XX XXX XXXX"
						/>
					</div>

					<div class="form-group">
						<label for="company">Company Name</label>
						<input
							type="text"
							id="company"
							bind:value={formData.company}
							placeholder="Your Company (Optional)"
						/>
					</div>

					<div class="form-group full-width">
						<label for="message">Message *</label>
						<textarea
							id="message"
							bind:value={formData.message}
							required
							rows="5"
							placeholder="Tell us about your project requirements..."
						></textarea>
					</div>

					<button
						type="submit"
						class="submit-btn"
						disabled={submitted}
					>
						{submitted ? "✓ Message Sent!" : "Send Message"}
					</button>
				</form>
			</div>
		</div>
	</div>
</section>

<style>
	.contact {
		padding: 8rem 0;
		background: var(--color-white);
		position: relative;
	}

	.contact::before {
		content: "";
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		height: 1px;
		background: linear-gradient(
			90deg,
			transparent,
			var(--color-gold),
			transparent
		);
	}

	.container {
		max-width: 1400px;
		margin: 0 auto;
		padding: 0 2rem;
	}

	.contact-grid {
		display: grid;
		grid-template-columns: 1fr 1.2fr;
		gap: 6rem;
		align-items: start;
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

	.contact-text {
		font-size: 1.125rem;
		line-height: 1.8;
		color: var(--color-slate);
		margin-bottom: 3rem;
	}

	.contact-details {
		display: flex;
		flex-direction: column;
		gap: 2rem;
		margin-bottom: 3rem;
	}

	.contact-item {
		display: flex;
		align-items: flex-start;
		gap: 1rem;
	}

	.contact-icon {
		font-size: 1.5rem;
		flex-shrink: 0;
	}

	.contact-label {
		font-size: 0.875rem;
		color: var(--color-slate);
		text-transform: uppercase;
		letter-spacing: 0.05em;
		margin-bottom: 0.25rem;
	}

	.contact-value {
		font-size: 1.125rem;
		color: var(--color-charcoal);
		font-weight: 500;
		text-decoration: none;
		transition: color 0.3s ease;
	}

	a.contact-value:hover {
		color: var(--color-terracotta);
	}

	.social-links {
		display: flex;
		gap: 1rem;
	}

	.social-link {
		width: 50px;
		height: 50px;
		display: flex;
		align-items: center;
		justify-content: center;
		background: var(--color-sand);
		color: var(--color-charcoal);
		text-decoration: none;
		font-weight: 700;
		border-radius: 50%;
		transition: all 0.3s ease;
		font-size: 0.875rem;
	}

	.social-link:hover {
		background: var(--color-terracotta);
		color: var(--color-white);
		transform: translateY(-4px);
	}

	.contact-form-wrapper {
		background: var(--color-sand);
		padding: 3rem;
		border-radius: 8px;
		box-shadow: var(--shadow-sm);
	}

	.contact-form {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 1.5rem;
	}

	.form-group {
		display: flex;
		flex-direction: column;
	}

	.form-group.full-width {
		grid-column: 1 / -1;
	}

	label {
		font-size: 0.875rem;
		font-weight: 600;
		color: var(--color-charcoal);
		margin-bottom: 0.5rem;
		text-transform: uppercase;
		letter-spacing: 0.05em;
	}

	input,
	textarea {
		padding: 1rem;
		font-family: var(--font-body);
		font-size: 1rem;
		color: var(--color-charcoal);
		background: var(--color-white);
		border: 2px solid transparent;
		border-radius: 4px;
		transition: all 0.3s ease;
		outline: none;
	}

	input:focus,
	textarea:focus {
		border-color: var(--color-terracotta);
		box-shadow: 0 0 0 3px rgba(212, 133, 106, 0.1);
	}

	textarea {
		resize: vertical;
		min-height: 120px;
	}

	.submit-btn {
		grid-column: 1 / -1;
		padding: 1.25rem 3rem;
		background: var(--color-terracotta);
		color: var(--color-white);
		border: 2px solid var(--color-terracotta);
		border-radius: 4px;
		font-family: var(--font-body);
		font-size: 1rem;
		font-weight: 600;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		cursor: pointer;
		transition: all 0.3s ease;
	}

	.submit-btn:hover:not(:disabled) {
		background: var(--color-deep-terracotta);
		transform: translateY(-2px);
		box-shadow: 0 8px 24px rgba(212, 133, 106, 0.3);
	}

	.submit-btn:disabled {
		background: var(--color-gold);
		border-color: var(--color-gold);
		cursor: not-allowed;
	}

	@media (max-width: 1024px) {
		.contact-grid {
			grid-template-columns: 1fr;
			gap: 4rem;
		}
	}

	@media (max-width: 768px) {
		.contact {
			padding: 4rem 0;
		}

		.contact-form-wrapper {
			padding: 2rem;
		}

		.contact-form {
			grid-template-columns: 1fr;
		}
	}
</style>
