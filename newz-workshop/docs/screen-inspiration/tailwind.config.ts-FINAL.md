# CODE SNIPPET

> FILE: tailwind.config.ts

In the attachment I enclosed the modified Tailwind config with the updates needed to accurately reflect the visual theme of the Dimension UI as presented in the desired screenshots. 

Which now includes:

### Dark Mode support (class)

**Color Palette**

- Backgrounds: #0e0c17, #1a1727
- Gradients: From lavender → pink → yellow

**Accents**

- Purple, soft pink, soft blue, golden yellow

**Typography**

- Inter font stack

**Shadows and Backgrounds**

- Subtle glows and gradients for a luminous, elegant dark UI

**NEXT STEPS**

- You may need to take this into account and brake it into your design tokens or convert to CSS variables.

---

### Code

```
import { type Config } from 'tailwindcss';

const config: Config = {
  darkMode: 'class',
  theme: {
    extend: {
      fontFamily: {
        sans: ['Inter', 'ui-sans-serif', 'system-ui'],
      },
      colors: {
        background: '#0e0c17', // deep navy background
        surface: '#1a1727', // secondary surfaces
        primary: '#fcae67', // warm highlight
        secondary: '#c084fc', // purple accent
        accent: '#e879f9',
        highlight: '#facc15', // yellow
        neutral: {
          100: '#f8fafc',
          200: '#e2e8f0',
          300: '#cbd5e1',
          400: '#94a3b8',
          500: '#64748b',
          600: '#475569',
          700: '#334155',
          800: '#1e293b',
          900: '#0f172a',
        },
        lavender: '#b794f4',
        grape: '#7c3aed',
        softpink: '#f9a8d4',
        softblue: '#93c5fd',
      },
      gradientColorStops: theme => ({
        ...theme('colors'),
        sunsetStart: '#a78bfa', // purple
        sunsetMid: '#f472b6', // pink
        sunsetEnd: '#facc15', // yellow
      }),
      backgroundImage: {
        'radial-fade': 'radial-gradient(ellipse at center, rgba(255,255,255,0.1), transparent)',
        'hero-glow': 'linear-gradient(to right, #c084fc, #fcae67, #facc15)',
      },
      boxShadow: {
        'glow': '0 0 20px rgba(250, 204, 21, 0.6)',
      },
    },
  },
  plugins: [],
};

export default config;
```
