# SunWorld Building Material LLC - Premium Website

A modern, high-performance website built with SvelteKit showcasing SunWorld's building materials business across the UAE.

## 🎨 Design Features

- **Premium Aesthetic**: Distinctive design with Bebas Neue display font, Cormorant serif, and Work Sans body font
- **Terracotta & Gold Color Scheme**: Sophisticated palette reflecting building materials industry
- **Smooth Animations**: Staggered reveals, scroll effects, and micro-interactions
- **Fully Responsive**: Optimized for desktop, tablet, and mobile devices
- **Performance Optimized**: Built with SvelteKit for blazing-fast load times

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ installed
- npm or pnpm package manager

### Installation

1. Install dependencies:
```bash
npm install
```

2. Run development server:
```bash
npm run dev
```

3. Open browser to `http://localhost:5173`

### Building for Production

```bash
npm run build
```

Preview production build:
```bash
npm run preview
```

## 📁 Project Structure

```
sunworld-website/
├── src/
│   ├── lib/
│   │   └── components/
│   │       ├── Navigation.svelte    # Sticky navigation bar
│   │       ├── Hero.svelte          # Hero section with stats
│   │       ├── About.svelte         # Company information
│   │       ├── Products.svelte      # Product categories
│   │       ├── Branches.svelte      # UAE locations
│   │       ├── Contact.svelte       # Contact form
│   │       └── Footer.svelte        # Footer with links
│   ├── routes/
│   │   ├── +layout.svelte          # Root layout
│   │   └── +page.svelte            # Homepage
│   ├── app.html                     # HTML template
│   └── app.css                      # Global styles
├── static/                          # Static assets
├── svelte.config.js                 # SvelteKit config
├── vite.config.js                   # Vite config
└── package.json
```

## 🎯 Key Sections

1. **Hero**: Dramatic full-screen introduction with company stats
2. **About**: Company history and core values
3. **Products**: 8 main product categories with 30,000+ items
4. **Branches**: 6 locations across UAE
5. **Contact**: Interactive form with business details
6. **Footer**: Quick links and company information

## 🛠 Customization

### Colors
Edit color variables in `src/app.css`:
```css
:root {
  --color-sand: #F4EDE3;
  --color-terracotta: #D4856A;
  --color-gold: #C9A870;
  --color-charcoal: #2B2B2B;
  /* ... */
}
```

### Fonts
Modify font imports in `src/app.html`:
- Display: Bebas Neue
- Serif: Cormorant
- Body: Work Sans

### Content
- Update product categories in `src/lib/components/Products.svelte`
- Modify branch locations in `src/lib/components/Branches.svelte`
- Edit company info in `src/lib/components/About.svelte`

## 📱 Contact Form

The contact form includes validation and a success state. To connect to a backend:

1. Update the `handleSubmit` function in `src/lib/components/Contact.svelte`
2. Add your API endpoint or email service integration
3. Configure CORS if needed

## 🌐 Deployment

### Vercel (Recommended)
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm install -g netlify-cli
netlify deploy --prod
```

### Static Export
For static hosting:
1. Install static adapter: `npm i -D @sveltejs/adapter-static`
2. Update `svelte.config.js` to use adapter-static
3. Build: `npm run build`
4. Deploy `build` folder

## 🎨 Design Philosophy

This website embodies:
- **Industrial Elegance**: Warm terracotta tones mixed with architectural precision
- **Material Authenticity**: Design language that reflects building materials
- **Professional Trust**: Clean, confident layouts that establish credibility
- **UAE Context**: Design choices that resonate with the regional market

## 📄 License

This website is proprietary to SunWorld Building Material LLC.

## 🤝 Support

For questions or support, contact SunWorld Building Material LLC:
- Email: info@sunworlduae.com
- Phone: +971 4 XXX XXXX
- Website: [Your domain]

---

Built with ❤️ using SvelteKit
