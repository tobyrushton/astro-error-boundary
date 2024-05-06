# astro-error-boundary

A reusable error boundary for SSR with [Astro](https://astro.build)

> :warning: This only catches errors during rendering, if an error is thrown during a components lifetime it will not be caught.

## Getting started
```bash
# npm
npm install astro-error-boundary

# pnpm
pnpm add astro-error-boundary

# yarn
yarn add astro-error-boundary
```

## Usage
```astro
<ErrorBoundary>
  <!-- SRR Component -->
  <Fragment slot="error">
    <!-- Error fallback here -->
    <p>Something went wrong</p>
  </Fragment>
</ErrorBoundary>
```
The error itself can also be accessed by rendering a callback function
> **Note:** When rendering a callback as a slot you cannot use the Astro Fragment component.
```astro
<ErrorBoundary>
  <!-- SRR Component -->
  <div slot="error">
    <!-- Error fallback here -->
    {(error: Error) => <p>Error: {error.message}</p>}
  </div>
</ErrorBoundary>
```
