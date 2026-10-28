# EVOQUE
An innovative AR based web application focused on delivering a modern, intuitive, and user-friendly digital experience.

EVOQUE is a futuristic fashion storefront concept that combines an editorial shopping experience with browser-based virtual try-on demos. It features a minimal black-and-white visual identity, technical streetwear product collections, product discovery, a shopping bag, and two camera-based try-on experiences.
Project status: Front-end prototype / work in progress. Shopping and try-on flows are demos; there is currently no production checkout, order-management backend, or persistent user account system.

Highlights
- Fashion storefront: Responsive landing page with editorial sections for collections, product innovation, and a fashion journal.
- Product catalogue: Browse technical outerwear, garments, and accessories with product details, tags, colors, and prices.
- Shop experience: Product browsing, category filtering/search controls, product quick views, and product-specific try-on entry points.
- Live AR-style try-on demo: Requests camera access and overlays selected garment/accessory artwork on a mirrored live camera feed. The current tracking implementation is a lightweight custom heuristic tracker, not a dedicated trained pose-estimation model.
- Photo-based try-on demo: Capture a webcam photo or upload an image, choose a garment, preview a composited garment overlay, compare the preview with the original, and download the result.
- Shopping bag: Add items, adjust/remove items, and view the current in-memory cart. Checkout is simulated and does not process payments or create real orders.
- Editorial content: Fashion journal articles and a technology/lab section describing material and garment concepts.
- Responsive interface and motion: Tailwind CSS, custom styling, icons, and motion effects.
  
Try-on implementation notes
The project includes two distinct experiences:
1. Live AR-style overlay — Uses the browser camera and canvas-based garment drawing, positioned using a custom real-time tracking/heuristic layer.
2. Photo try-on preview — Uses a captured or uploaded image and composites a product image onto a canvas to create a downloadable preview.

Product examples
The catalogue includes concept products such as:
- Cyber-Tex Overcoat
- Geo-Mesh Tech Hoodie
- Modular All-Weather Vest
- Orbital Tapered Trousers
- Zero-Form Minimalist Tee
- Cyber-Spec HUD Visor
- Neo-Carbon Bucket Cap
- Quantum Titanium Watch
The try-on catalogue also includes items such as the Neo Cyber Bomber, Minimalist Tech Hoodie, Vanguard Utility Vest, and eyewear.

Technology stack
- React 19 — UI components
- TypeScript — typed application code
- Vite — development server and production build
- Tailwind CSS 4 — utility-first styling
- Lucide React — interface icons
- Motion — UI animations
- HTML Canvas and browser MediaDevices API — camera-based overlays and image compositing
- Google GenAI SDK — included as a dependency, but not currently used for live API calls in the existing try-on implementation
Getting started
Prerequisites
- Node.js (use a current version compatible with the installed Vite version)
- npm
- A modern browser
- Camera access for live try-on features

Installation
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
npm install
npm run dev
Vite is configured to start on port 3000. Open the local URL printed in the terminal (typically http://localhost:3000).

Camera access generally requires localhost during development or a secure HTTPS deployment. Grant browser camera permission when prompted.
Available scripts
Command	Purpose
npm run dev	Start the Vite development server on port 3000
npm run build	Build the production bundle
npm run preview	Preview the production build locally
npm run lint	Run the TypeScript compiler in no-emit mode


Project structure

.
├── index.html
├── package.json
├── vite.config.ts
├── src/
│   ├── main.tsx                 # React entry point
│   ├── App.tsx                  # Main app, navigation, cart and modal state
│   ├── index.css                # Global styles and Tailwind import
│   ├── types.ts                 # Shared TypeScript interfaces
│   ├── data/
│   │   ├── products.ts          # Main catalogue, collections and editorial data
│   │   ├── arProducts.ts        # Live AR-style try-on products
│   │   └── aiTryOnProducts.ts   # Photo try-on products
│   ├── ar/
│   │   ├── CameraManager.ts     # Camera lifecycle and permissions
│   │   ├── RealTimeTracker.ts   # Lightweight tracking heuristics
│   │   └── GarmentDrawers.ts    # Canvas garment overlay drawing
│   └── components/
│       ├── home/                # Atelier, collections, lab, journal and footer
│       ├── shop/                # Product catalogue and shopping UI
│       └── ar/                  # Live and photo try-on modals

Roadmap ideas
- Integrate a real pose/face/hand landmark model for more stable tracking.
- Replace the photo overlay simulation with a properly integrated image-editing/generative try-on service.
- Add garment assets designed specifically for accurate body alignment.
- Add a backend for product inventory, accounts, cart persistence, and order management.
- Add automated tests, accessibility checks, and deployment documentation.
  
Contributing Suggestions and improvements are welcome. For substantial changes, open an issue first to discuss the proposed update.

License
No license has been specified yet. Unless a license is added to this repository, the default copyright rules apply and reuse is not automatically permitted.
