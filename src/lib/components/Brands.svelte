<script>
    // Sample brand data - replace with actual logo images
    const brands = [
        { name: "CONARES", logo: "/brands/conares.png" },
        { name: "Qatar Steel", logo: "/brands/qatar-steel.png" },
        { name: "Asas Steel", logo: "/brands/asas-steel.png" },
        { name: "Gulf Steel", logo: "/brands/gulf-steel.png" },
        { name: "Jindal Steel & Power", logo: "/brands/jindal.png" },
        // { name: "Tata Steel", logo: "/brands/tata-steel.png" },
        // { name: "JSW Steel", logo: "/brands/jsw-steel.png" },
        // { name: "ArcelorMittal", logo: "/brands/arcelormittal.png" },
        // { name: "POSCO", logo: "/brands/posco.png" },
        // { name: "Nippon Steel", logo: "/brands/nippon.png" },
        // { name: "Baosteel", logo: "/brands/baosteel.png" },
        // { name: "ThyssenKrupp", logo: "/brands/thyssenkrupp.png" },
    ];

    // Duplicate brands for seamless infinite scroll
    const duplicatedBrands = [...brands, ...brands];
</script>

<section class="brands">
    <div class="container">
        <div class="section-header">
            <div class="section-label">Trusted Partners</div>
            <h2 class="section-title">Premium Brands We Carry</h2>
            <p class="section-subtitle serif">
                Partnering with the world's leading manufacturers to bring you
                quality materials
            </p>
        </div>

        <div class="carousel-wrapper">
            <div class="carousel-track">
                {#each duplicatedBrands as brand}
                    <div class="brand-card">
                        <div class="brand-logo">
                            <img src={brand.logo} alt={brand.name} />
                        </div>
                    </div>
                {/each}
            </div>
        </div>

        <div class="brands-footer">
            <p class="brands-text">+ Many more trusted manufacturers</p>
        </div>
    </div>
</section>

<style>
    .brands {
        padding: 6rem 0;
        background: var(--color-white);
        position: relative;
        overflow: hidden;
    }

    .brands::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        height: 1px;
        background: linear-gradient(
            90deg,
            transparent,
            var(--color-terracotta),
            transparent
        );
    }

    .container {
        max-width: 1400px;
        margin: 0 auto;
        padding: 0 2rem;
    }

    .section-header {
        text-align: center;
        max-width: 800px;
        margin: 0 auto 4rem;
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

    .carousel-wrapper {
        position: relative;
        overflow: hidden;
        padding: 2rem 0;
        margin: 0 -2rem;
    }

    .carousel-wrapper::before,
    .carousel-wrapper::after {
        content: "";
        position: absolute;
        top: 0;
        bottom: 0;
        width: 150px;
        z-index: 2;
        pointer-events: none;
    }

    .carousel-wrapper::before {
        left: 0;
        background: linear-gradient(90deg, var(--color-white), transparent);
    }

    .carousel-wrapper::after {
        right: 0;
        background: linear-gradient(-90deg, var(--color-white), transparent);
    }

    .carousel-track {
        display: flex;
        gap: 4rem;
        animation: scroll 40s linear infinite;
        width: fit-content;
    }

    .carousel-track:hover {
        animation-play-state: paused;
    }

    .brand-card {
        flex-shrink: 0;
        width: 200px;
        height: 100px;
        display: flex;
        align-items: center;
        justify-content: center;
        background: var(--color-sand);
        border-radius: 8px;
        padding: 1.5rem;
        transition: all 0.3s ease;
        box-shadow: var(--shadow-sm);
    }

    .brand-card:hover {
        transform: translateY(-4px);
        box-shadow: var(--shadow-md);
        background: var(--color-white);
    }

    .brand-logo {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .brand-logo img {
        max-width: 100%;
        max-height: 100%;
        object-fit: contain;
        filter: grayscale(100%);
        opacity: 0.7;
        transition: all 0.3s ease;
    }

    .brand-card:hover .brand-logo img {
        filter: grayscale(0%);
        opacity: 1;
    }

    .brands-footer {
        text-align: center;
        margin-top: 3rem;
    }

    .brands-text {
        font-size: 1rem;
        color: var(--color-slate);
        font-style: italic;
    }

    @keyframes scroll {
        0% {
            transform: translateX(0);
        }
        100% {
            transform: translateX(-50%);
        }
    }

    @media (max-width: 768px) {
        .brands {
            padding: 4rem 0;
        }

        .section-header {
            margin-bottom: 3rem;
        }

        .carousel-track {
            gap: 2rem;
            animation-duration: 30s;
        }

        .brand-card {
            width: 150px;
            height: 80px;
        }

        .carousel-wrapper::before,
        .carousel-wrapper::after {
            width: 50px;
        }
    }
</style>
