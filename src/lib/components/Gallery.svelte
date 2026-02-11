<script>
    let activeFilter = "all";

    // Sample product gallery data - replace with actual product images
    const products = [
        {
            id: 1,
            image: "/gallery/gulf.jpeg",
            title: "High-Grade Rebar",
            brand: "Qatar Steel",
            category: "rebar",
            description: "Premium reinforcement bars for structural integrity",
        },
        {
            id: 2,
            image: "/gallery/conares.jpeg",
            title: "Structural Steel Beams",
            brand: "Jindal Steel",
            category: "beams",
            description: "Industrial-grade I-beams and H-beams",
        },
        {
            id: 3,
            image: "/gallery/gulf.jpeg",
            title: "Wire Mesh Panels",
            brand: "Gulf Steel",
            category: "mesh",
            description: "Welded wire mesh for concrete reinforcement",
        },
        {
            id: 4,
            image: "/gallery/conares.jpeg",
            title: "Steel Coils",
            brand: "Tata Steel",
            category: "coils",
            description: "Hot-rolled and cold-rolled steel coils",
        },
        {
            id: 5,
            image: "/gallery/conares.jpeg",
            title: "Steel Sheets",
            brand: "ArcelorMittal",
            category: "sheets",
            description: "Galvanized and stainless steel sheets",
        },
        {
            id: 6,
            image: "/gallery/conares.jpeg",
            title: "Steel Pipes",
            brand: "CONARES",
            category: "pipes",
            description: "Seamless and welded steel pipes",
        },
        {
            id: 7,
            image: "/gallery/asas.jpeg",
            title: "Deformed Rebar",
            brand: "Asas Steel",
            category: "rebar",
            description: "High-strength deformed reinforcement bars",
        },
        {
            id: 8,
            image: "/gallery/conares.jpeg",
            title: "Steel Angles",
            brand: "JSW Steel",
            category: "profiles",
            description: "Equal and unequal angle sections",
        },
    ];

    const categories = [
        { id: "all", name: "All Products" },
        { id: "rebar", name: "Rebar" },
        { id: "beams", name: "Beams" },
        { id: "mesh", name: "Wire Mesh" },
        { id: "coils", name: "Coils" },
        { id: "sheets", name: "Sheets" },
        { id: "pipes", name: "Pipes" },
        { id: "profiles", name: "Profiles" },
    ];

    $: filteredProducts =
        activeFilter === "all"
            ? products
            : products.filter((p) => p.category === activeFilter);

    function setFilter(filter) {
        activeFilter = filter;
    }
</script>

<section class="gallery">
    <div class="container">
        <div class="section-header">
            <div class="section-label">Product Showcase</div>
            <h2 class="section-title">Premium Steel Products</h2>
            <p class="section-subtitle serif">
                Explore our extensive range of high-quality steel products from
                trusted global brands
            </p>
        </div>

        <!-- Filter Buttons -->
        <div class="filter-bar">
            {#each categories as category}
                <button
                    class="filter-btn"
                    class:active={activeFilter === category.id}
                    on:click={() => setFilter(category.id)}
                >
                    {category.name}
                </button>
            {/each}
        </div>

        <!-- Product Grid -->
        <div class="gallery-grid">
            {#each filteredProducts as product (product.id)}
                <div class="gallery-item">
                    <div class="item-image">
                        <img src={product.image} alt={product.title} />
                        <div class="image-overlay">
                            <div class="overlay-content">
                                <span class="view-icon">🔍</span>
                                <span class="view-text">View Details</span>
                            </div>
                        </div>
                    </div>
                    <div class="item-content">
                        <div class="item-brand">{product.brand}</div>
                        <h3 class="item-title">{product.title}</h3>
                        <p class="item-description">{product.description}</p>
                    </div>
                </div>
            {/each}
        </div>

        <div class="gallery-cta">
            <p class="cta-text">Can't find what you're looking for?</p>
            <a href="#contact" class="btn-gallery">Request Custom Product</a>
        </div>
    </div>
</section>

<style>
    .gallery {
        padding: 8rem 0;
        background: var(--color-sand);
        position: relative;
    }

    .gallery::before {
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

    .filter-bar {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 1rem;
        margin-bottom: 4rem;
        padding: 0 1rem;
    }

    .filter-btn {
        padding: 0.75rem 1.5rem;
        background: var(--color-white);
        color: var(--color-charcoal);
        border: 2px solid transparent;
        border-radius: 50px;
        font-family: var(--font-body);
        font-size: 0.95rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 0.05em;
        cursor: pointer;
        transition: all 0.3s ease;
    }

    .filter-btn:hover {
        border-color: var(--color-terracotta);
        transform: translateY(-2px);
    }

    .filter-btn.active {
        background: var(--color-terracotta);
        color: var(--color-white);
        border-color: var(--color-terracotta);
    }

    .gallery-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
        gap: 2.5rem;
        margin-bottom: 5rem;
    }

    .gallery-item {
        background: var(--color-white);
        border-radius: 8px;
        overflow: hidden;
        box-shadow: var(--shadow-sm);
        transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        animation: fadeInUp 0.6s ease-out;
    }

    .gallery-item:hover {
        transform: translateY(-12px);
        box-shadow: var(--shadow-lg);
    }

    .item-image {
        position: relative;
        width: 100%;
        height: 280px;
        overflow: hidden;
        background: var(--color-concrete);
    }

    .item-image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1);
    }

    .gallery-item:hover .item-image img {
        transform: scale(1.1);
    }

    .image-overlay {
        position: absolute;
        inset: 0;
        background: linear-gradient(
            135deg,
            rgba(212, 133, 106, 0.9),
            rgba(181, 103, 79, 0.9)
        );
        display: flex;
        align-items: center;
        justify-content: center;
        opacity: 0;
        transition: opacity 0.4s ease;
    }

    .gallery-item:hover .image-overlay {
        opacity: 1;
    }

    .overlay-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
        transform: translateY(20px);
        transition: transform 0.4s ease;
    }

    .gallery-item:hover .overlay-content {
        transform: translateY(0);
    }

    .view-icon {
        font-size: 2.5rem;
    }

    .view-text {
        color: var(--color-white);
        font-size: 1.125rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 0.1em;
    }

    .item-content {
        padding: 2rem;
    }

    .item-brand {
        font-size: 0.875rem;
        color: var(--color-terracotta);
        font-weight: 700;
        text-transform: uppercase;
        letter-spacing: 0.1em;
        margin-bottom: 0.75rem;
    }

    .item-title {
        font-family: var(--font-display);
        font-size: 1.75rem;
        color: var(--color-charcoal);
        margin-bottom: 0.75rem;
        line-height: 1.2;
    }

    .item-description {
        font-size: 0.95rem;
        color: var(--color-slate);
        line-height: 1.6;
    }

    .gallery-cta {
        text-align: center;
        padding: 4rem 2rem;
        background: linear-gradient(135deg, var(--color-charcoal), #1a1a1a);
        border-radius: 8px;
    }

    .cta-text {
        font-family: var(--font-serif);
        font-size: 1.75rem;
        font-style: italic;
        color: var(--color-concrete);
        margin-bottom: 2rem;
    }

    .btn-gallery {
        display: inline-block;
        padding: 1.25rem 3rem;
        background: var(--color-terracotta);
        color: var(--color-white);
        text-decoration: none;
        font-weight: 600;
        font-size: 1.125rem;
        text-transform: uppercase;
        letter-spacing: 0.1em;
        border-radius: 4px;
        transition: all 0.3s ease;
        border: 2px solid var(--color-terracotta);
    }

    .btn-gallery:hover {
        background: transparent;
        border-color: var(--color-gold);
        color: var(--color-gold);
        transform: translateY(-4px);
        box-shadow: 0 8px 24px rgba(201, 168, 112, 0.3);
    }

    @keyframes fadeInUp {
        from {
            opacity: 0;
            transform: translateY(30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @media (max-width: 768px) {
        .gallery {
            padding: 4rem 0;
        }

        .section-header {
            margin-bottom: 3rem;
        }

        .filter-bar {
            margin-bottom: 3rem;
            gap: 0.75rem;
        }

        .filter-btn {
            padding: 0.6rem 1.25rem;
            font-size: 0.875rem;
        }

        .gallery-grid {
            grid-template-columns: 1fr;
            gap: 2rem;
        }

        .item-image {
            height: 240px;
        }

        .gallery-cta {
            padding: 3rem 1.5rem;
        }

        .cta-text {
            font-size: 1.5rem;
        }
    }
</style>
