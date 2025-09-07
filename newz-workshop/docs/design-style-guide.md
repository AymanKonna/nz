# General Style Guide

## Introduction

This document outlines the design principles, visual language, and implementation details for the **General Style Guide** application. The goal is to ensure a consistent, modern, and user-friendly interface that aligns with the project's aesthetic vision.

## 1. Core Design Principles

The design of the **General Style Guide** is built upon the following core principles:

*   **Dark Mode First**: The application is designed with a dark theme as the default, providing a sleek and focused user experience.
*   **Glass Morphism**: UI elements leverage transparent, blurred backgrounds to create a sense of depth and modern elegance.
*   **Gradient Accents**: Strategic use of multi-color gradients for text and interactive elements to add visual interest and highlight key actions.
*   **Readability & Usability**: Clear typography, sufficient contrast, and intuitive layouts are prioritized for optimal user interaction.
*   **Responsiveness**: The design adapts seamlessly across various screen sizes, from mobile devices to large desktop monitors.

## 2. Color Palette

The application's color palette is defined using CSS variables in `src/app/globals.css` and extended in `tailwind.config.js`.

### Primary Colors

These are the foundational colors for the application's UI.

| CSS Variable          | Hex Value   | Tailwind Name      | Description                               |
| :-------------------- | :---------- | :----------------- | :---------------------------------------- |
| `--background`        | `#0e0c17`   | `background`       | Main background color                     |
| `--foreground`        | `hsl(210, 10%, 97%)` | `foreground`       | Primary text color                        |
| `--surface`           | `#1a1727`   | -                  | General surface/panel color               |
| `--card`              | `rgba(26, 23, 39, 0.6)` | `card`             | Background for cards and panels           |
| `--card-foreground`   | `hsl(210, 10%, 97%)` | `card-foreground`  | Text color on cards                       |
| `--popover`           | `#1a1727`   | `popover`          | Popover background                        |
| `--popover-foreground`| `hsl(210, 10%, 97%)` | `popover-foreground` | Text color on popovers                    |
| `--primary`           | `#fcae67`   | `primary`          | Main accent color (orange)                |
| `--primary-foreground`| `#0e0c17`   | `primary-foreground` | Text color on primary elements            |
| `--secondary`         | `#252241`   | `secondary`        | Secondary background/interactive color    |
| `--secondary-foreground`| `hsl(210, 10%, 97%)` | `secondary-foreground` | Text color on secondary elements          |
| `--muted`             | `#1a1727`   | `muted`            | Muted background color                    |
| `--muted-foreground`  | `hsl(215, 15%, 75%)` | `muted-foreground` | Muted text color                          |
| `--accent`            | `#e879f9`   | `accent`           | Accent color (pink/purple)                |
| `--accent-foreground` | `#0e0c17`   | `accent-foreground` | Text color on accent elements             |
| `--highlight`         | `#facc15`   | `highlight`        | Highlight color (yellow)                  |
| `--destructive`       | `hsl(0, 63%, 31%)` | `destructive`      | Destructive action color (red)            |
| `--destructive-foreground`| `hsl(210, 10%, 97%)` | `destructive-foreground` | Text color on destructive elements        |
| `--border`            | `rgba(255, 255, 255, 0.15)` | `border`           | Border color for UI elements              |
| `--input`             | `#252241`   | `input`            | Input field background                    |
| `--ring`              | `#c084fc`   | `ring`             | Focus ring color                          |

### Neutral Colors

A grayscale palette for various shades of neutral elements.

| CSS Variable    | Hex Value | Tailwind Name |
| :-------------- | :-------- | :------------ |
| `--neutral-100` | `#f8fafc` | `neutral-100` |
| `--neutral-200` | `#e2e8f0` | `neutral-200` |
| `--neutral-300` | `#cbd5e1` | `neutral-300` |
| `--neutral-400` | `#94a3b8` | `neutral-400` |
| `--neutral-500` | `#64748b` | `neutral-500` |
| `--neutral-600` | `#475569` | `neutral-600` |
| `--neutral-700` | `#334155` | `neutral-700` |
| `--neutral-800` | `#1e293b` | `neutral-800` |
| `--neutral-900` | `#0f172a` | `neutral-900` |

### Custom Colors

Specific colors used for various purposes, such as categories or special elements., such as content-types and tags.

| CSS Variable  | Hex Value | Description                 |
| :------------ | :-------- | :-------------------------- |
| `--lavender`  | `#b794f4` | Used for purple accents     |
| `--grape`     | `#7c3aed` | Deeper purple               |
| `--softpink`  | `#f9a8d4` | Soft pink for accents       |
| `--softblue`  | `#93c5fd` | Soft blue for accents       |

## 3. Typography

The application uses the **Inter** font family for all text, ensuring modern aesthetics and excellent readability.

*   **Font Family**: `--font-sans: 'Inter', system-ui, sans-serif;`
*   **Base Size**: `16px` (inherited from browser defaults, scaled by Tailwind)
*   **Weights**: `300`, `400`, `500`, `600`, `700` are available.
*   **Headings**: `h1` uses `text-4xl font-bold` with a gradient effect.
*   **Body Text**: Generally `text-base` or `text-sm` with `text-neutral-300` or `text-white`.
*   **Small Text**: `text-xs` for labels and metadata.

## 4. UI Components (shadcn/ui)

The **General Style Guide** exclusively uses [shadcn/ui](https://ui.shadcn.com/) components for all standard UI elements. These components are styled to seamlessly integrate with the custom theme.

### Used Components:

*   **Button**: For all clickable actions (e.g., "Add", "Update", "Delete", also in form submissions, icon buttons).
*   **Card**: Used as small containers enable users to scan content quickly without overwhelming with long blocks of text.
*   **Dialog**: For modal pop-ups, such as the "Add New " and "Edit" forms.
*   **Input**: For text input fields (e.g., search,  other user typing kind of input).
*   **Select**: For dropdown selections (e.g., date, priority, category, filters).
*   **Switch**: For toggle functionalities, specifically the theme toggle.
*   **Textarea**: For multi-line text input (e.g., description, comments).

### General Styling Approach:

Shadcn/ui components are configured to inherit the CSS variables defined in `src/app/globals.css` and `tailwind.config.js`. This ensures that properties like `border-radius`, `background`, `foreground`, and `border` automatically match the theme.

## 5. Custom Styling & Effects

Beyond shadcn/ui, several custom CSS classes and Tailwind configurations are used to achieve the unique visual style.

### 5.1. Glass Morphism (`.glass-card`)

Applied to cards and panels to give them a translucent, frosted glass appearance.

```css
.glass-card {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.08) 0%, rgba(255, 255, 255, 0.02) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  position: relative;
}

.glass-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(174, 126, 246, 0.03) 0%, rgba(247, 142, 189, 0.02) 50%, rgba(255, 172, 118, 0.01) 100%);
  border-radius: inherit;
  pointer-events: none;
}
```

### 5.2. Gradient Text (`.gradient-text`)

Used for prominent text elements, like the application title, to apply a vibrant multi-color gradient.

```css
.gradient-text {
  background: linear-gradient(142deg, rgba(174, 126, 246, 1) 0%, rgba(247, 142, 189, 1) 37%, rgba(255, 172, 118, 1) 66%, rgba(247, 224, 89, 1) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

### 5.3. Gradient Buttons (`.btn-gradient`)

Applied to primary action buttons, providing a visually appealing gradient background with hover effects.

```css
.btn-gradient {
  background: linear-gradient(142deg, rgba(174, 126, 246, 1) 0%, rgba(247, 142, 189, 1) 37%, rgba(255, 172, 118, 1) 66%, rgba(247, 224, 89, 1) 100%);
  transition: all 0.3s ease;
}

.btn-gradient:hover {
  transform: scale(1.05);
  box-shadow: 0 10px 25px rgba(174, 126, 246, 0.4);
}
```

### 5.4. Hover Effects (`.hover-card`)

A general utility class for subtle lift and shadow effects on hover, enhancing interactivity.

```css
.hover-card {
  transition: all 0.3s ease;
}

.hover-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 20px 25px -5px rgba(174, 126, 246, 0.2), 0 10px 10px -5px rgba(174, 126, 246, 0.1);
}
```

### 5.5. Animated Particles Background (`.particles`)

A subtle, animated background effect on the main canvas to add dynamism.

```css
.particles {
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(circle at 20% 50%, rgba(174, 126, 246, 0.1) 1px, transparent 1px),
    radial-gradient(circle at 80% 50%, rgba(247, 142, 189, 0.1) 1px, transparent 1px),
    radial-gradient(circle at 40% 80%, rgba(255, 172, 118, 0.08) 1px, transparent 1px);
  background-size: 100px 100px, 80px 80px, 120px 120px;
  animation: float 20s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { 
    transform: translateY(0px) rotate(0deg); 
  }
  50% { 
    transform: translateY(-20px) rotate(180deg); 
  }
}
```
## 6. Icons (Lucide React)

All icons used throughout the application are sourced from [Lucide React](https://lucide.dev/). This ensures a consistent, lightweight, and scalable icon set.

### Commonly Used Icons:

*   `Plus`: Add new items (e.g., "Add" buttons).
*   `Search`: Search input field.
*   `Filter`: (Future use for filter dropdowns).
*   `Calendar`: Date indicators.
*   `X`: Close buttons, cancel actions.
*   `Edit3`: Edit actions.
*   `Trash2`: Delete actions.
*   `Target`: Connection mode indicator.
*   `ArrowRight`: (Future use for navigation).
*   `Zap`: Zoom indicator.
*   `Users`: Users count indicator.
*   `Sun`, `Moon`: Theme toggle.

## 7. Responsiveness

The application is designed to be fully responsive, adapting its layout and component sizing to provide an optimal experience on various screen sizes.

*   **Mobile-First Approach**: Layouts are initially designed for smaller screens and then progressively enhanced for larger viewports using Tailwind CSS utility classes (e.g., `md:`, `lg:`).
*   **Flexible Grids & Stacks**: Elements like the header controls transition from stacked (`flex-col`) on mobile to horizontal (`md:flex-row`) on larger screens.
*   **Dynamic Sizing**: Elements dynamically adjust their size based on content and priority, ensuring readability without excessive scrolling.
*   **Padding & Margins**: Responsive padding and margins are used to maintain appropriate spacing (e.g., `p-6 pb-0 md:p-8 md:pb-0` in the `Header`).
*   **Canvas Behavior**: The React Flow canvas handles its own responsiveness for zooming and panning, ensuring the interactive area scales correctly.

## 8. Animations & Transitions

Subtle animations and transitions are used to enhance the user experience, providing visual feedback and a polished feel.

*   **Hover Effects**: Most interactive elements (buttons, nodes, connection delete icons) have `transition-all duration-300` for smooth visual feedback.
*   **Node Transitions**:  Nodes have `transition-all duration-300` for smooth movement during dragging and scaling when selected.
*   **Particle Animation**: The `.particles` background uses a `float` keyframe animation for a continuous, subtle movement.
*   **Shadcn/ui Animations**: Components like Dialogs and Selects inherit their default animations for opening/closing and transitions.

## Conclusion

This **General Style Guide** serves as a comprehensive reference for the visual and interactive aspects of any application. By adhering to these guidelines, we ensure a consistent, aesthetically pleasing, and highly functional user interface that delivers an exceptional user experience.
