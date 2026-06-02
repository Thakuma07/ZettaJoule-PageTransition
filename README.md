
# Grid Shutter Page Transition 🚀

A sleek and modern Next.js web application demonstrating a "Grid Shutter" style page transition. This project leverages `next-transition-router` and `gsap` to create stunning, dynamic block-based page transition animations that elevate the user experience.

<img width="1920" height="1080" alt="Screenshot 2026-06-02 120415" src="https://github.com/user-attachments/assets/c9331155-1e79-4747-be9f-8f53a1b73756" />

## 🙏 Inspiration

This project took inspiration from the beautiful transitions and state-of-the-art design on [Zetta Joule](https://zetta-joule.com/).

---

## 🛠️ Tech Stack

- **Framework:** [Next.js](https://nextjs.org) 14+ (App Router)
- **Animations:** [GSAP (GreenSock Animation Platform)](https://gsap.com/)
- **Transitions:** [`next-transition-router`](https://github.com/vantezzen/next-transition-router)
- **Styling:** Vanilla CSS for maximum control and performance

---

## ✨ Key Features

- **Custom Grid Shutter Transitions**: The page transitions are built by generating a grid of `div` blocks that dynamically scale in and out across the screen during route changes, giving a mechanical "shutter" effect.
- **Seamless Next.js Integration**: Uses `next-transition-router` to intercept Next.js routing, allowing complex GSAP timelines to complete before the DOM changes.
- **Client-Side Providers**: Built with a custom `<TransitionProvider>` client component that cleanly wraps the App Router `children`.
- **Responsive and Adaptive**: The transition grid automatically calculates window size and resizes its blocks dynamically on window resize events to ensure the animation is pixel-perfect on any screen size.
- **Staggered Animations**: Implements GSAP staggers alternating from left-to-right and right-to-left across different rows for an organic, complex feel.

---

## 🚀 Getting Started

### Prerequisites
Make sure you have Node.js installed on your machine.

### Installation & Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Run the development server:**
   ```bash
   npm run dev
   ```

3. **View the Application:**
   Open [http://localhost:3000](http://localhost:3000) in your browser. Click on the navigation links (Genesis, Cascade, Orbit) to see the transition effect in action!

---

## 🎨 How It Works (Under the Hood)

The core logic of the transition lives in `src/providers/TransitionProvider.jsx`:

1. **Grid Generation:** When the app mounts, it calculates the screen's width and height. It divides the screen into 4 rows and 16 columns (configurable), and generates `div` elements absolute-positioned to cover the screen.
2. **Animation Out (Leave):** When a user clicks a link, `next-transition-router` pauses the navigation. GSAP triggers an `animateIn` timeline, scaling the shutter blocks up (`scaleX: 1`) to cover the old page.
3. **DOM Swap:** Once the grid covers the screen, Next.js swaps out the old page's DOM for the new page's DOM behind the scenes.
4. **Animation In (Enter):** GSAP triggers the `animateOut` timeline, scaling the shutter blocks down (`scaleX: 0`), revealing the new page.

---

## 🛠️ Customizing the Transition

You can easily tweak the transition effect by modifying constants in `src/providers/TransitionProvider.jsx`:

- **Change Grid Size**: Adjust the `ROWS` and `COLS` constants at the top of the file. (e.g., `ROWS = 8`, `COLS = 10`).
- **Change Animation Speed**: Modify the `duration` property in the GSAP `animateIn` and `animateOut` functions.
- **Change Stagger Direction**: Modify the `stagger` property in the GSAP timelines to change how the blocks reveal (e.g., from `"center"`, `"edges"`, or random).

---

## 📁 Detailed Project Structure

```text
├── public/                 # Static assets (images, fonts, SVGs)
│   ├── img1.jpg
│   ├── img2.jpg
│   └── img3.jpg
├── src/
│   ├── app/                # Next.js App Router (Pages & Layout)
│   │   ├── cascade/        # Cascade Page (/cascade)
│   │   ├── orbit/          # Orbit Page (/orbit)
│   │   ├── globals.css     # Global styles including .transition-grid classes
│   │   ├── layout.js       # Root layout wrapping the app in TransitionProvider
│   │   └── page.js         # Genesis (Home) Page (/)
│   ├── components/         # Reusable UI Components
│   │   └── Navbar.js       # Navigation bar to trigger transitions
│   └── providers/          # Context Providers and Wrappers
│       └── TransitionProvider.jsx  # The GSAP logic and TransitionRouter setup
├── package.json            # Project dependencies and scripts
└── README.md               # You are here!
```
