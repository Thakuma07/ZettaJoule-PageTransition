# Grid Shutter Page Transition 🚀

A sleek Next.js web application demonstrating a "Grid Shutter" style page transition. This project leverages `next-transition-router` and `gsap` to create stunning, dynamic block-based page transition animations. 

## 🛠️ Tech Stack
- **Framework:** [Next.js](https://nextjs.org) (App Router)
- **Animations:** [GSAP](https://gsap.com/)
- **Transitions:** [`next-transition-router`](https://github.com/vantezzen/next-transition-router)
- **Styling:** Vanilla CSS

## ✨ Features
- **Custom Page Transitions**: Uses an intricate grid-shutter effect during route changes.
- **Client Components**: Custom `<TransitionProvider>` for wrapping the app router.
- **Responsive Animations**: The grid automatically resizes to fit the screen dimensions.

## 🚀 Getting Started

First, install the dependencies (if you haven't already):
```bash
npm install
```

Then, run the development server:
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the smooth transitions in action.

## 📁 Project Structure
- `src/providers/TransitionProvider.jsx`: Core GSAP animation logic and the `TransitionRouter` wrapper.
- `src/app/`: The Next.js App Router pages (Genesis, Cascade, Orbit).
- `src/components/Navbar.js`: Navigation to test the transitions.
- `src/app/globals.css`: Contains CSS necessary for the `.transition-grid` and blocks.
