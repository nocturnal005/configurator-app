# Frame Studio Configurator

Custom picture framing configurator with live preview, HD frame gradients, and Wessex pricing engine.

## Features

- **Live Frame Preview**: Real-time updates with HD colour gradients for gold, silver, wood, and painted finishes
- **Multi-Style Classification**: Frames tagged across Modern, Traditional, Rustic, and Ornate categories
- **Wessex Pricing**: Accurate frame + glass + mount pricing with VAT
- **Image Upload**: Auto-fit uploaded images to frame dimensions with object-fit:cover
- **Glass Effects**: Visible preview of glossy, matte, and UV-protective glass options
- **16 Mount Colours**: White, Cream, Ivory, Black, Charcoal, Grey, Warm Grey, Navy, Sage, Duck Egg, Burgundy, Forest, Taupe, Linen, Sand, Powder Blue

## Deployment

### Deploy to Vercel

1. Push this repository to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Click "Add New" → "Project"
4. Import your GitHub repository
5. Vercel will auto-detect Vite and deploy

### Local Development

```bash
npm install
npm run dev
```

Visit `http://localhost:5173`

## Project Structure

```
frame-configurator/
├── index.html          # Entry HTML
├── package.json        # Dependencies
├── vite.config.js      # Build config
└── src/
    ├── main.jsx        # React entry point
    └── App.jsx         # Configurator component
```

## Pricing Logic

Uses Wessex pricing formula:
- Frame: `(wholesale_per_metre × perimeter × 2.8 markup × 100) + 450p base + (1.5p × area)`
- Glass: `(250p base + 2.0p × area) × glass_multiplier`
- Mount: `300p base + 2.0p × area` (if enabled)
- VAT: 20% on total

## Product Data

100 mouldings from Simons 2023 catalogue embedded in App.jsx. Each product includes:
- `id`: Product code
- `d`: Description
- `w`: Width in mm
- `col`: Colour family (black, white, gold, silver, natural-wood, dark-wood, grey, cream)
- `sty`: Array of applicable styles (modern, traditional, rustic, ornate)
- `ppm`: Price per metre (wholesale)

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari 14+
