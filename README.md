# SvelteKit Snapshot Flash Bug

Minimal reproduction for a SvelteKit bug where snapshot restore causes a brief UI flash with the initial state value.

## Steps to reproduce

1. Clone the repo and run `npm install && npm run dev`
2. Edit the textarea (change "hello" to something else)
3. Click the link to navigate to another page
4. Press the browser back button
5. Open the console and observe the `$inspect` output

## Expected behavior

The restored snapshot value should be applied before the first render, without showing the default state value.

## Actual behavior

The default value ("hello") briefly flashes in the UI and appears in `$inspect` before being replaced by the restored snapshot value.
