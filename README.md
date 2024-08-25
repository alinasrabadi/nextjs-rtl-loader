
<h1>NextJs RTL Loader</h1>

https://github.com/user-attachments/assets/567058b8-fe78-4cb0-b4b3-82d61b1c4263


<br>

> NextJs RTL Loader is a sleek, customizable top-loading progress bar for Next.js and React applications, designed with built-in RTL support.

## Features

- RTL Support: Designed with built-in RTL (right-to-left) support for seamless integration in RTL layouts.
- Seamless Integration: Easily integrates with any React application.
- Highly Customizable: Offers extensive customization with sensible defaults.
- Smooth Animation: Features a custom implementation for smooth, visually appealing progress indications.
- Dynamic Configuration: Configure color, height, speed, easing, and more to fit your needs.

## Installation

To install NextJs RTL Loader, run the following command in your project directory:

```bash
npm install nextjs-rtl-loader
```

OR

```bash
yarn add nextjs-rtl-loader
```

## Usage

To use NextJs RTL Loader in your Next.js application using the app router:

```typescript
// app/layout.tsx
import NextLoader from "nextjs-rtl-loader";

export default function RootLayout({ children }) {
  return (
    <html>
      <NextLoader />
      {children}
    </html>
  );
}
```

To use NextJs RTL Loader in your Next.js application using the pages router:

```typescript
import NextLoader from "nextjs-rtl-loader";

export default function App({ Component, pageProps }) {
  return (
    <>
      <NextLoader />
      <Component {...pageProps} />;
    </>
  );
}
```

### Custom Configuration

```typescript
import NextLoader from "nextjs-rtl-loader";

export default function RootLayout({ children }) {
  return (
    <html>
      <NextLoader
        color="#ff4500"
        height="1.5rem"
        speed={300}
        easing="linear"
        showSpinner
      />
      {children}
    </html>
  );
}
```

### Prevent Trigger Loader

Prevent triggering the loader when clicking a button inside a Next.js <Link>:

To ensure that clicking a button within a Next.js <Link> does not inadvertently trigger the loader, use the following code to prevent default behavior and stop event propagation:

```typescript
onClick={(e) => {
  e.preventDefault();
  e.nativeEvent.stopImmediatePropagation();
}}
```

## API

`<NextLoader />` accepts the following props for customization:

- `color` (string): Specifies the color of the top-loading bar. Default: "#59a2ff" (a shade of blue).
- `initialPosition` (number): Sets the initial position of the top-loading bar as a percentage of the total width. Default: 0.08 (8% of the total width).
- `height` (number | string): Defines the height of the top-loading bar in pixels or css unit. Default: 4 pixels.
- `easing` (string): Specifies the easing function to use for the loading animation. Accepts any valid CSS easing string. Default: "ease".
- `speed` (number): Sets the animation speed of the top-loading bar in milliseconds. Default: 200 milliseconds.
- `zIndex` (number): Defines the z-index property of the top-loading bar, controlling its stacking order. Default: 2147483647.
- `boxShadow` (string): Sets the box-shadow property of the top-loading bar. Turned off by default.
- `showSpinner` (boolean): Determines whether to accompany the loading bar with a spinner. Turned off by default.
